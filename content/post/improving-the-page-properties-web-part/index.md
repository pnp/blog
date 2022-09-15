---
title: "Improving the Page Properties web part"
date: 2021-04-06T01:18:00-04:00
author: "mhomol"
githubname: mhomol
categories: ["Community post"]
images:
- images/diff-screencap.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

Ever get annoyed with the page properties web part put out by Microsoft?
If you've got some OCD issues (like me) then it may not take very long.
At [ThreeWill](https://threewill.com), we help clients with their
digital workplaces and improving the way their users can obtain
information and makes sense of it all. Oftentimes, the Page Properties
web part can be useful here, as we very often add valuable metadata to
pages in a digital workplace, which we often tie to page templates as
well. News might roll up based on these page properties, which can
assist in finding information in many ways. But its often handy to
display this metadata in a clean way on a page as well. The standard
Page Properties web part seeks to do just that. And, for the most part,
it does a fine job with it. But it has a few deficiencies. The most
annoying thing to me, when setting up digital workplaces was that it
only supports a white background. But there are other small things, like
the limitations with pretty standard field types. I like the idea of
taking advantage of metadata columns for pages, but being able to use it
visually is equally important. I finally decided to do something about
it and build a new version of this web part. So with this in mind,
let's lay out our goals with this new web part. We will call it the
Advanced Page Properties web part. 

## Feature Goals

Attempt to replicate the functionality of Page Properties with the
following improvements:

-   Support for theme variants
-   Updated to standard capsule look for list options
-   Support for image fields
-   Support for hyperlink fields
-   Support for currency
-   Improved support for dates

In other words, we're shooting for this:

![Screen Shot 2021-04-06 at 2.40.56 PM.png](images/Screen Shot 2021-04-06 at 2.40.56 PM.png)

## Property Pane

For a part like this, it's all about getting the property page figured
out first. We want this to feel familiar too and not stray too much from
the original design, unless it helps.

Let's start by recognizing our chief property that the web part needs:
selectedProperties. This array will hold the internal names of the
fields that a user has selected for display in our web part. We intend
on passing this property down to our React component. Here's a look at
our property object:

```javascript
export interface IAdvancedPagePropertiesWebPartProps {
title: string;
selectedProperties: string[];
}
```

In our AdvancedPagePropertiesWebPart, we want to hold all possible
properties for drop downs in a single array.

```javascript
private availableProperties: IPropertyPaneDropdownOption[] = [];
```

Next, we need the following method to obtain the right types of
properties for display:

```javascript
  private async getPageProperties(): Promise<void> {
    Log.Write("Getting Site Page fields...");
    const list = sp.web.lists.getByTitle("Site Pages");
    const fi = await list.fields();

    this.availableProperties = [];
    Log.Write(`${fi.length.toString()} fields retrieved!`);
    fi.forEach((f) => {
      if (!f.FromBaseType && !f.Hidden && !f.Sealed && f.SchemaXml.indexOf("ShowInListSettings="FALSE"") === -1
          && f.TypeAsString !== "Boolean" && f.TypeAsString !== "Note" && f.TypeAsString !== "User") {
        this.availableProperties.push({ key: f.InternalName, text: f.Title });
        Log.Write(f.TypeAsString);
      }
    });
  }
```

We are using the PnP JS library for gathering the fields in the Site
Pages library. Figuring out the right types of filters to gather was a
bit of trial-and-error. We are excluding anything that's inherited from
a base type or is hidden in any way. We are also excluding 3 standard
types so far: boolean, note and user. Note doesn't make sense to
display. Boolean can definitely work, but needs a good display
convention. User was the only tricky object, which is the reason it
isn't done yet.

We call the above method prior to loading up the property pane.

```javascript
  protected async onPropertyPaneConfigurationStart(): Promise<void> {
    Log.Write(`onPropertyPaneConfigurationStart`);
    await this.getPageProperties();
    this.context.propertyPane.refresh();
  }
```

We need handlers for adding and deleting a property and selecting a
property from a dropdown. These methods make necessary changes to the
selectedProperties array.

```javascript
  protected onAddButtonClick (value: any) {
    this.properties.selectedProperties.push(this.availableProperties[0].key.toString());
  }

  protected onDeleteButtonClick (value: any) {
    Log.Write(value.toString());
    var removed = this.properties.selectedProperties.splice(value, 1);
    Log.Write(`${removed[0]} removed.`);
  }

  protected onPropertyPaneFieldChanged(propertyPath: string, oldValue: any, newValue: any): void {
    if (propertyPath.indexOf("selectedProperty") >= 0) {
      Log.Write('Selected Property identified');
      let index: number = _.toInteger(propertyPath.replace("selectedProperty", ""));
      this.properties.selectedProperties[index] = newValue;
    }
  }
```

Finally, with all of our pieces in place, we can render our property
pane with all it's needed functionality.

```javascript
  protected getPropertyPaneConfiguration(): IPropertyPaneConfiguration {
    Log.Write(`getPropertyPaneConfiguration`);

    // Initialize with the Title entry
    var propDrops: IPropertyPaneField<any>[] = [];
    propDrops.push(PropertyPaneTextField('title', {
      label: strings.TitleFieldLabel
    }));
    propDrops.push(PropertyPaneHorizontalRule());
    // Determine how many page property dropdowns we currently have
    this.properties.selectedProperties.forEach((prop, index) => {
      propDrops.push(PropertyPaneDropdown(`selectedProperty${index.toString()}`,
        {
          label: strings.SelectedPropertiesFieldLabel,
          options: this.availableProperties,
          selectedKey: prop,
        }));
      // Every drop down gets its own delete button
      propDrops.push(PropertyPaneButton(`deleteButton${index.toString()}`,
      {
        text: strings.PropPaneDeleteButtonText,
        buttonType: PropertyPaneButtonType.Command,
        icon: "RecycleBin",
        onClick: this.onDeleteButtonClick.bind(this, index)
      }));
      propDrops.push(PropertyPaneHorizontalRule());
    });
    // Always have the Add button
    propDrops.push(PropertyPaneButton('addButton',
    {
      text: strings.PropPaneAddButtonText,
      buttonType: PropertyPaneButtonType.Command,
      icon: "CirclePlus",
      onClick: this.onAddButtonClick.bind(this)
    }));

    return {
      pages: [
        {
          header: {
            description: strings.PropertyPaneDescription
          },
          groups: [
            {
              groupName: strings.SelectionGroupName,
              groupFields: propDrops
            }
          ]
        }
      ]
    };
  }
```

## Our Component and Displaying our fields/values

Our React component needs to properly react to the list of selected
properties changing. It also needs to react to our theme changing. I
leveraged this [awesome post from Hugo
Bernier](https://tahoeninjas.blog/2020/07/28/adding-support-for-theme-variants-in-spfx-web-parts/)
for the theming, so I will not cover that in-depth, although you will
see how it's being leveraged in the code snippets below. Here are the
properties we plan to start with and respond to: 

```javascript
import { IReadonlyTheme } from '@microsoft/sp-component-base';
import { WebPartContext } from "@microsoft/sp-webpart-base";

export interface IAdvancedPagePropertiesProps {
  context: WebPartContext;
  title: string;
  selectedProperties: string[];
  themeVariant: IReadonlyTheme | undefined;
}
```

We will track the state of our selected properties and their values with
hooks. We want to trigger off of changes to our properties, so we will
setup a reference to their current state. We will also establish our
themeVariant and context at the start of our component.

```javascript
// Main state object for the life of this component - pagePropValues
  const [pagePropValues, setPagePropValues] = useState<PageProperty[]>([]);
  const propsRef = useRef(props);

  const { semanticColors }: IReadonlyTheme = props.themeVariant;

  propsRef.current = props;

  sp.setup({ spfxContext: props.context });
```

So we are tracking the state of pagePropValues, which is an array of
type PageProperty. What is PageProperty?

```javascript
import { IFieldInfo } from "@pnp/sp/fields";

export interface PageProperty {
  info: IFieldInfo;
  values: any[];
}
```

Our effect is looking to see when changes are made to the properties,
then is performing our core logic to refresh properties and values.

```javascript
  /**
   * @description Effects to fire whenever the properties change
   */
  useEffect(() => {
    refreshProperties();

    return () => {
      // No cleanup at this moment
    };
  }, [propsRef.current]);
```

The core method is refreshProperties. It has 2 main calls it needs to
make, whenever selected properties has changed: Establish any known
metadata for each property that will assist in display and obtain all
actual values for this property and the specific page id that we are
viewing.

```javascript
  /**
   * refreshProperties
   * @description Gets the actual values for any selected properties, along with critical field metadata and ultimately re-sets the pagePropValues state
   */
  async function refreshProperties () {
    var newSetOfValues: PageProperty[] = [];

    if (props.selectedProperties !== undefined && props.selectedProperties !== null) {
      Log.Write(`${props.selectedProperties.length.toString()} properties used.`);

      // Get the value(s) for the field from the list item itself
      var allValues: any = {};
      if (props.context.pageContext.listItem !== undefined && props.context.pageContext.listItem !== null) {
        allValues = await sp.web.lists.getByTitle("Site Pages").items.getById(props.context.pageContext.listItem.id).select(...props.selectedProperties).get();
        console.log(allValues);
      }

      for (let i = 0; i < props.selectedProperties.length; i++) {
        const prop = props.selectedProperties[i];

        Log.Write(`Selected Property: ${prop}`);

        // Get field information, in case anything is needed in conjunction with value types
        const field = await sp.web.lists.getByTitle("Site Pages").fields.getByInternalNameOrTitle(prop)();

        // Establish the values array
        var values: any[] = [];
        if (allValues.hasOwnProperty(prop)) {
          switch (field.TypeAsString) {
            case "TaxonomyFieldTypeMulti":
            case "MultiChoice":
              values = _.clone(allValues[prop]);
              break;
            case "Thumbnail":
              values.push(JSON.parse(allValues[prop]));
              break;

            default:
              // Default behavior is to treat it like a string
              values.push(allValues[prop]);
              break;
          }
        }

        // Push the final setup of a PageProperty object
        newSetOfValues.push({ info: field, values: [...values] });
      }

      setPagePropValues({...newSetOfValues});
    }
  }
```

As we loop through all of the properties that have been selected, we
make calls with PnP JS to get all of the metadata per field and all of
the values per field. The call to get all of the values can return with
any number of data types, so we need to be prepared for that. This is
why it is of type any\[\] to start. But this is also why we have a
switch statement for certain outlier situations, where the line to set
the array of any need to be done a little differently than the default.
Our 3 known cases of needing to do something different are
TaxonomyFieldTypeMulti, MultiChoice and Thumbnail.

## React and Display

Our function component returns the following:

```javascript
  return (
    <div className={`${styles.advancedPageProperties} ${styles.container}`} style={{backgroundColor: semanticColors.bodyBackground, color: semanticColors.bodyText}}>
      {RenderTitle()}
      {RenderPageProperties()}
    </div>
  );
```

RenderTitle is pretty straightforward.

```javascript
  /**
   * RenderTitle
   * @description Focuses on the 1 row layer, being the Title that has been chosen for the page
   * @returns
   */
  const RenderTitle = () => {
    if (props.title !== '') {
      return <div className={styles.title}>{props.title}</div>;
    } else {
      return null;
    }
  };
```

RenderPageProperties is the first of a 2-dimensional loop, where we want
to display a section for each page property that was select, just like
the original.

```javascript
  /**
   * RenderPageProperties
   * @description Focuses on the 2nd row layer, which is the property names that have been chosen to be displayed (uses Title as the display name)
   * @returns
   */
  const RenderPageProperties = () => {
    if (pagePropValues !== undefined && pagePropValues !== null) {
      var retVal = _.map(pagePropValues, (prop) => {
        return (
            <>
              <div className={styles.propNameRow}>{prop.info.Title}<span style={{display: 'none'}}> - {prop.info.TypeAsString}</span></div>
              <div className={styles.propValsRow}>
                {RenderPagePropValue(prop)}
              </div>
            </>
          );
      });
      return retVal;
    } else {
      return <i>Nothing to display</i>;
    }
  };
```

This method then calls our final display method, RenderPagePropValue,
which performs our 2nd layer of array display, mapping all of the values
and providing the correct display, based on the field type of the
selected property. This is the heart of the display, where various type
conversions and logic are done real-time as we display the values,
including trying to achieve a slightly more modern SharePoint look using
capsules for array labels.

```javascript
  /**
   * RenderPagePropValue
   * @description Focuses on the 3rd and final row layer, which is the actual values tied to any property displayed for the page
   * @param prop
   * @returns
   */
   const RenderPagePropValue = (prop: PageProperty) => {
    console.log(prop);
    var retVal = _.map(prop.values, (val) => {
      if (val !== null) {
        switch (prop.info.TypeAsString) {
          case "URL":
            return (
              <span className={styles.urlValue}><a href={val.Url} target="_blank" style={{color: semanticColors.link}}>{val.Description}</a></span>
            );
          case "Thumbnail":
            return (
              <span><img className={styles.imgValue} src={val.serverRelativeUrl} /></span>
            );
          case "Number":
            return (
              <span className={styles.plainValue}>{(prop.info["ShowAsPercentage"] === true ? Number(val).toLocaleString(undefined,{style: 'percent', minimumFractionDigits:0}) : (prop.info["CommaSeparator"] === true ? val.toLocaleString('en') : val.toString()))}</span>
            );
          case "Currency":
            return (
              <span className={styles.plainValue}>{(prop.info["CommaSeparator"] === true ? new Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD' }).format(val) : Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD', useGrouping: false }).format(val))}</span>
            );
          case "DateTime":
            //,"",,
            switch (prop.info["DateFormat"]) {
              case "StandardUS":
                return (
                  <span className={styles.plainValue}>{new Date(val).toLocaleDateString()}</span>
                );
              case "ISO8601":
                const d = new Date(val);
                return (
                  <span className={styles.plainValue}>{`${d.getFullYear().toString()}-${d.getMonth()}-${d.getDate()}`}</span>
                );
              case "DayOfWeek":
                return (
                  <span className={styles.plainValue}>{new Date(val).toLocaleDateString("en-US", { weekday: 'long', month: 'long', day: 'numeric', year: 'numeric' })}</span>
                );
              case "MonthSpelled":
                return (
                  <span className={styles.plainValue}>{new Date(val).toLocaleDateString("en-US", { month: 'long', day: 'numeric', year: 'numeric' })}</span>
                );
              default:
                return (
                  <span className={styles.plainValue}>{new Date(val).toLocaleDateString()}</span>
                );
            }
          case "TaxonomyFieldTypeMulti":
          case "TaxonomyFieldType":
            return (
              <span className={styles.standardCapsule} style={{backgroundColor: semanticColors.accentButtonBackground, color: semanticColors.accentButtonText}}>{val.Label}</span>
            );
          default:
            return (
              <span className={styles.standardCapsule} style={{backgroundColor: semanticColors.accentButtonBackground, color: semanticColors.accentButtonText}}>{val}</span>
            );
        }
      } else {
        return (<span className={styles.plainValue}>N/A</span>);
      }
    });
    return retVal;
  };
```

So that's all of the necessary code. Here's what the finished product
looks like, compared to the original page properties web part.

![diff-screencap](images/diff-screencap.png)
This web part is now officially apart of the [PnP Web Parts repository](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-advanced-page-properties).
I would love to hear about improvements you'd like to see and obviously
you are more than welcome to contribute. I already have a bit of a list
of things I'd love to see it do. 

## Other ideas for improvements

-   Capsules to be linkable to either a search result page or a filtered
    view of site pages (we always get client requests for this)
-   Support for People fields (this is the only thing lacking from the
    original)
-   Support for Boolean fields (just need the right idea for proper
    display, really)
-   Styling per property (i.e. colorizing per property or something to
    that effect)

## Conclusion

Hopefully, I've gotten you excited about Page Properties again and
you've learned a little along the way around how the current Page
Properties part might be doing what it does under the hood. Please
consider contributing and feel free to reach out to me anytime. Thanks
for your time!
