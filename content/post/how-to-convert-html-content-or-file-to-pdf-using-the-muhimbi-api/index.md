---
title: "How to convert HTML content or file to PDF using the Muhimbi API?"
date: 2022-01-05T02:25:00-05:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/ChandaniPrajapati_0-1639758794000.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

## Introduction

This article is used whenever you are getting any content from
SharePoint List/Library or anything else and rendering it in any
component then it is difficult to get HTML from that component and
extract CSS as well so here we will create a dynamic HTML (List or Table
or anything else as per our requirement) and we can add some inline CSS
as well. So in this article, we will see step-by-step implementations.

## Implementation

**1. Register to Muhimbi API**
To get the trial version API key, Register to
[www.muhimbi.com](https://www.muhimbi.com/register?returnUrl=%2Flogin%20). After
registration, you have to activate a subscription and then you will get
an API key, Access token, and Subscription ID on the registered email
ID. 
To check API response, you can refer to
[https://api.muhimbi.com/api-docs/v1/index.html?url=/api-docs/v1/swagger.json#/Convert](https://api.muhimbi.com/api-docs/v1/index.html?url=/api-docs/v1/swagger.json#/Convert).
After this, we will use the API key in the SPFx web part while calling
an API.

**2. Create the SPFx web part**

-   Open a command prompt
-   Move to the path where you want to create a project
-   Create a project directory using:
    md muhimbi-export-html-content-to-pdf
Move to the above-created directory using:
    cd muhimbi-export-html-content-to-pdf

Now execute the below command to create an SPFx solution:
    yo @microsoft/sharepoint
It will ask some questions, as shown below,

![ChandaniPrajapati_0-1639758794000.png](images/ChandaniPrajapati_0-1639758794000.png)

After a successful installation, we can open a project in any source
code tool. Here, I am using the VS code, so I will execute the command:
    code .
Now go to the ***src \> webparts \> webpart \> components
\>** **I{webpartname}Props.ts*** file and at here we will create some
properties.

```javascript
import { WebPartContext } from "@microsoft/sp-webpart-base";
import { HttpClient } from "@microsoft/sp-http";

export interface IMuhimbiExportHtmlContentToPdfProps {
  description: string;
  context: WebPartContext;
  apiKey: string;
  apiUrl: string;
}
```
 

Create a file ***I{webpartname}State.ts** *inside ***src \> webparts \>
webpart \> components*** and create a state interface as below,

```javascript
export interface IMuhimbiExportHtmlContentToPdfState{
    showLoader: boolean;
}
```
 

Create a **service** folder inside the **src** folder and then in this
folder create a file called **ConvertFileService.ts**. And in this file,
we will create services to download a file, create a blob, and covert
file.
We need to convert content to base64 string as API needs based64 content
to convert a file.

1. Create a function to generate a blob as per the base64 string. 

2. Create a function to download a file. We will use API key and API URL
from the property pane so here we will pass it as an argument. and then
in the download file function, we will use the POST method of a
httpClient.

3. Now in the **convertToPDF** function, we will convert HTML content to
base64, create a body, and pass some required properties to the
**downlaodFile** function.
 

```javascript
import { HttpClient, IHttpClientOptions, HttpClientResponse } from '@microsoft/sp-http';
import { WebPartContext } from "@microsoft/sp-webpart-base";

declare global {
    interface Navigator {
        msSaveBlob?: (blob: any, defaultName?: string) => boolean;
        msSaveOrOpenBlob: (blob: Blob) => void
    }
}

export class ConvertFileService {

    constructor(private context: WebPartContext) {

    }

    public generateBlob(base64string) {
        var file_bytes = atob(base64string);
        var byte_numbers = new Array(file_bytes.length);
        for (var i = 0; i < file_bytes.length; i++) {
            byte_numbers[i] = file_bytes.charCodeAt(i);
        }
        var byte_array = new Uint8Array(byte_numbers);
        var file_blob = new Blob([byte_array], { type: "application/pdf" });
        return file_blob;
    }

    public async downloadFile(API_Key: string, url: string, fileName: string, request: any, extension: string) {
        if (API_Key == '')
            return;

        try {
            var input_data = JSON.stringify(request);
            const requestHeaders: Headers = new Headers();
            requestHeaders.append('Content-type', 'application/json');
            requestHeaders.append('API_key', API_Key);
            const httpClientOptions: IHttpClientOptions = {
                headers: requestHeaders,
                body: input_data
            };
            return this.context.httpClient.post(url, HttpClient.configurations.v1, httpClientOptions)
                .then(async (response: HttpClientResponse) => {
                    let data = await response.json();
                    if (data['result_code'] == "Success") {
                        var file_blob = this.generateBlob(data['processed_file_content']);
                        if ((window.navigator as any).msSaveBlob) {
                            (window.navigator as any).msSaveOrOpenBlob(file_blob, data['base_file_name'] + extension);
                        }
                        else {
                            var download_link = window.document.createElement("a");
                            download_link.href = window.URL.createObjectURL(file_blob);
                            download_link.download = fileName;
                            download_link.click();
                        }
                    }
                    return data;
                }).catch((error: any): Promise<any> => {
                    console.log("Getting error while dowloading file:", error);
                    return error;
                });
        }
        catch (error) {
            console.log(error.message);
        }
    }

    public convertToPDF(API_Key: string, apiUrl: string, htmlContent: string, fileName: string) {
        const base64data = btoa(htmlContent);
        const postURL = apiUrl;
        const body = {
            "use_async_pattern": false,
            "source_file_name": `${fileName}.html`,
            "source_file_content": base64data,
            "output_format": "PDF",
        };
        return this.downloadFile(API_Key, postURL, fileName, body, '.pdf');
    }
}
```
 

Now move to the **{WebpartName}WebPart.ts** file.

1.  Initialize service in onInit()

2.  Create an API key and API URL properties in property pane
configuration.

3.  Set properties value in render() so we can use it in the component.
 

```javascript
import * as React from 'react';
import * as ReactDom from 'react-dom';
import { Version } from '@microsoft/sp-core-library';
import {
  IPropertyPaneConfiguration,
  PropertyPaneTextField
} from '@microsoft/sp-property-pane';
import { BaseClientSideWebPart, WebPartContext } from '@microsoft/sp-webpart-base';

import * as strings from 'MuhimbiExportHtmlContentToPdfWebPartStrings';
import MuhimbiExportHtmlContentToPdf from './components/MuhimbiExportHtmlContentToPdf';
import { IMuhimbiExportHtmlContentToPdfProps } from './components/IMuhimbiExportHtmlContentToPdfProps';
import { HttpClient } from "@microsoft/sp-http";
import { ConvertFileService } from '../../services/ConvertFileService';

export interface IMuhimbiExportHtmlContentToPdfWebPartProps {
  description: string;
  context: WebPartContext;
  apiKey: string;
  apiUrl: string;
}

export default class MuhimbiExportHtmlContentToPdfWebPart extends BaseClientSideWebPart<IMuhimbiExportHtmlContentToPdfWebPartProps> {

  private _services: ConvertFileService = null;

  public onInit(): Promise<void> {
    return super.onInit().then(_ => {
      this._services = new ConvertFileService(this.context);
    });
  }

  public render(): void {
    const element: React.ReactElement<IMuhimbiExportHtmlContentToPdfProps> = React.createElement(
      MuhimbiExportHtmlContentToPdf,
      {
        description: this.properties.description,
        apiKey: this.properties.apiKey ? this.properties.apiKey : "8878a0cb-371f-4ff3-b223-af122514bd2a",
        apiUrl: this.properties.apiUrl ? this.properties.apiUrl : "https://api.muhimbi.com/api/v1/operations/convert", //"https://api.muhimbi.com/api/v1/operations/convert_html",
        context: this.context
      }
    );

    ReactDom.render(element, this.domElement);
  }

  protected onDispose(): void {
    ReactDom.unmountComponentAtNode(this.domElement);
  }

  protected get dataVersion(): Version {
    return Version.parse('1.0');
  }

  protected getPropertyPaneConfiguration(): IPropertyPaneConfiguration {
    return {
      pages: [
        {
          header: {
            description: strings.PropertyPaneDescription
          },
          groups: [
            {
              groupName: strings.BasicGroupName,
              groupFields: [
                PropertyPaneTextField('description', {
                  label: strings.DescriptionFieldLabel
                }),
                PropertyPaneTextField('apiKey', {
                  label: "API Key"
                }),
                PropertyPaneTextField('apiUrl', {
                  label: "API Url"
                })
              ]
            }
          ]
        }
      ]
    };
  }
}
```
 

Move to the **{webpartname}.tsx** file and then bind the service using
the current context.
At here for a demo purpose, I am using static HTML content with some
inline CSS. Apart from this, you can create your own HTML as per your
requirement or if you want to create dynamic HTML as per your content
then we can also create it.
Create a ***exportToPDF()*** to call service to convert from HTML to
PDF. So here we will update the **showLoader** state and as per state,
we will render data and spinner while the file is downloading.
 

```javascript
import * as React from 'react';
import styles from './MuhimbiExportHtmlContentToPdf.module.scss';
import { IMuhimbiExportHtmlContentToPdfProps } from './IMuhimbiExportHtmlContentToPdfProps';
import { IMuhimbiExportHtmlContentToPdfState } from './IMuhimbiExportHtmlContentToPdfState';
import { ConvertFileService } from '../../../services/ConvertFileService';
import { PrimaryButton, Stack } from 'office-ui-fabric-react';
import { Spinner, SpinnerSize } from 'office-ui-fabric-react/lib/Spinner';

export default class MuhimbiExportHtmlContentToPdf extends React.Component<IMuhimbiExportHtmlContentToPdfProps, IMuhimbiExportHtmlContentToPdfState> {

  private _services: ConvertFileService = null;

  private htmlContent = `<table style="width:100%;border: 1px solid black;border-collapse: collapse;"">
                          <tr>
                            <th style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Firstname</th>
                            <th style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Lastname</th>
                            <th style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Age</th>
                          </tr>
                          <tr>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Jill</td>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Smith</td>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">50</td>
                          </tr>
                          <tr>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Eve</td>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Jackson</td>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">94</td>
                          </tr>
                          <tr>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">John</td>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">Doe</td>
                            <td style="border: 1px solid black;border-collapse: collapse;padding: 5px;">80</td>
                          </tr>
                          </table>`;

  constructor(props: IMuhimbiExportHtmlContentToPdfProps) {
    super(props);
    this.state = {
      showLoader: false
    }
    this._services = new ConvertFileService(this.props.context);
  }

  public exportToPDF = () => {
    this.setState({ showLoader: true });
    this._services.convertToPDF(this.props.apiKey, this.props.apiUrl, this.htmlContent, 'test.pdf').then(result => {
      this.setState({ showLoader: false });
    }).catch(error => {
      console.log("Getting error in export to PDF:", error);
      this.setState({ showLoader: false });
    });
  }

  public render(): React.ReactElement<IMuhimbiExportHtmlContentToPdfProps> {

    const { description } = this.props;
    const { showLoader } = this.state;

    return (
      <div className={styles.muhimbiExportHtmlContentToPdf}>
        <h1>{description}</h1>
        <Stack>
          {showLoader &&
            <Spinner label="Wait, wait..., file is downloading" size={SpinnerSize.large} />
          }
          <PrimaryButton disabled={showLoader ? true : false} style={{ width: '200px', display: 'flex', alignSelf: 'end', marginBottom: '15px' }} text="Download as PDF" onClick={this.exportToPDF} allowDisabledFocus />
          <div dangerouslySetInnerHTML={{ __html: this.htmlContent }} />
        </Stack>

    );
  }
}
```
 
## Output 

![Muhimbi - Export to pdf.gif](images/Muhimbi - Export to pdf.gif)
 

Please find my  [source code](https://github.com/chandaniprajapati/muhimbi-export-html-content-to-pdf).



## Summary

In this article, we have seen the step-by-step implementation of Muhimbi
API in the SPFx Web part.
