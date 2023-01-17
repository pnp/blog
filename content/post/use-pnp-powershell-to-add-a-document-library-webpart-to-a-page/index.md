---
title: "Use PnP PowerShell to add a document library web part to a page (and only show a specific folder)"
date: 2021-06-10T08:40:00-04:00
author: "Marijn Somers"
githubname: Marijnsomers
categories: ["Community post"]
images:
- images/MS-list.png
tags: ["PnP PowerShell"]
type: "regular"
---
As a non-developer (please read this as a disclaimer) I still try to
make my life as easy as possible (yes, I am that lazy). PnP PowerShell
is a big component of that goal. A customer had the requirement to
create a page for each of their 86 folders in a document library so they
could add more information on those topics. That meant creating 86
pages, each with a document library web part on it that showed a specific
folder. No chance I was going to do that manually!

Creating the page wasn't really difficult. Showing the document library
and just the items in the folder was the hard part that I couldn't find
any examples of. The idea of this blog post is to help future people
like me to just copy/paste the code.
 

## The goal 

We started with a document library containing 86 folders, each having a
few documents. The goal was to create 86 pages, with each page showing a
block of text on the left and the document library web part showing only
the files from that folder.

## How to do this in the user interface 

Using the user interface, following steps were required:

-   Create a new page (with the same name as the folder)
-   Add a section to the page with 2 columns
-   Add a text web part to the left column
-   Add a document library web part to the right column
-   As a subrequirement, only show the files from the necessary folder.
    This can be set up from the web part properties


![Document library UI properties](images/MS-list.png)


That would definitely be a lot of work to do manually, so I decided that
PnP PowerShell needed to come to the rescue.

## The code 

Lets dig in to the code. I imagine that you have already dabbled with
PnP PowerShell and I will not explain how to install and configure it to
run.


```powershell
Connect-PnPOnline -Url https://yourtenant.sharepoint.com/sites/thesite/ -UseWebLogin
```


First we need to connect to the site. Replace the url with the correct
url of your site. I am using -UseWebLogin in this example because I am
using 2factor authentication.

### Create the page 

First thing to do is to create the page, using
the [Add-PnPPage ](https://pnp.github.io/powershell/cmdlets/Add-PnPPage.html)command.
I am using the \$name variable here to give it a name.


```powershell
Add-PnPPage -Name $name
  -LayoutType Article
  -HeaderLayoutType NoImage
  -CommentsEnabled:$false
```

Disabling the comments section on a modern SharePoint Page\
I couldn't figure out how to disable the comments section on the modern
client page. I tried setting it to false, or 0, but that didn't work.

The correct way to do is to use:

-CommentsEnabled:\$false

## Adding sections to the page 

To add a new section to the page, I am using
the [Add-PnPClientSidePageSection](https://pnp.github.io/powershell/cmdlets/Add-PnPPageSection.html) command.
I can just add a TwoColumn section on the page.


```powershell
Add-PnPPageSection -Page $name -SectionTemplate TwoColumn -Order 1
```

## Adding a text editor web part 

Adding a text editor is super easy, just use the Add-PnPClientSideText
command. Don't forget to add some text or it will fail.


```powershell
Add-PnPClientSideText -Page $name -Section 1 -Column 1 -Text " "
```


## The hard part: adding an existing document library as a web part to the page 

This was the easy bit, in my opinion. Adding a document library to a
page is surprisingly hard in PnP PowerShell (unless I am missing
something big.. in that case please call me out on this!)

What you need to do, is to use the[ Add-PnPClientSideWebPart
command](https://pnp.github.io/powershell/cmdlets/Add-PnPPageWebPart.html).
With this command you can add all kinds of webparts to the page.
Document library isn't one of them.

You need to add a List webparttype, and in the WebpartProperties you
need to mention that it is a document library AND what the ID is.


``` {.lia-code-sample .language-applescript}
Add-PnPPageWebPart -Page $name
  -DefaultWebPartType List -Section 1 -Column 2
  -WebPartProperties @{isDocumentLibrary="true";
                       selectedListId="1fa1fb45-e53b-4ea1-9325-ddca7afe986e";}
```

### Where can I find the SharePoint document library Id ? 

I didn't have a clue how to get this Id via code, so I resorted to the
UI: If you go to the library settings, the document library Id is shown
in the url:


![SharePoint document library ID in the url of the library settings page](images/documentlibrary-id.png)

Just cut out the %7B in the front, and the %7D on the back.
In this example, the document library Id is
4683b239-caf6-40a3-96c4-a02dedfa3418.

## Bonus: Only show a specific folder from the document library 

I couldn't figure out how to show only documents from a specific folder.
Doing this in the UI is supereasy. But there wasn't any example code out
there. So here it is:

In the WebPartProperties, add selectedFolderPath="/yourfoldername";

```powershell
Add-PnPPageWebPart -Page $name
  -DefaultWebPartType List -Section 1 -Column 2
  -WebPartProperties @{isDocumentLibrary="true";
                       selectedListId="1fa1fb45-e53b-4ea1-9325-ddca7afe986e";
                       selectedFolderPath="/$name";}
```


## Bonus 2: hide the command bar on the SharePoint Document Library Webpart 

In the UI, there is a way to simply hide the command bar. Because we are
showing this information in a nice looking page, there is no need for
all that extra fluff of "new", "upload" and so on.

In the same way as showing just files from a specific folder, you can
use the hideCommandBar="false"; in the WebPartProperties:


```powershell
Add-PnPPageWebPart -Page $name
  -DefaultWebPartType List -Section 1 -Column 2
  -WebPartProperties @{isDocumentLibrary="true";
                       selectedListId="1fa1fb45-e53b-4ea1-9325-ddca7afe986e";
                       selectedFolderPath="/$name";
                       hideCommandBar="false"}
```


## Publishing the page 

All the parts we need are now on the page. The only thing now is to
publish the page so it is visible to all visitors. For that, we need to
grab the page again and publish it.


```powershell
$page = Get-PnPPage -Identity $name
$page.Publish()
```


## Looping the code for all folders 

The last part of the code was to make this repeatable, for all 86
folders. There is probably a really nice way to , in code, get all
folders from the doclib and loop through them, but as stated a gazillion
times.. I am not a
developer.
So I exported the document library to Excel and copied the foldernames.
I added some quotes and a comma (in an Excel formula using =CHAR(34) & 
A2 & CHAR(34) &",") and added an array to store these.

The full code is:

```powershell
Connect-PnPOnline -Url https://yourtenant.sharepoint.com/sites/Yoursite/ -UseWebLogin
$ray = "folder1",
"folder2",
"folder3"
foreach ($name in $ray) {
#create page
Add-PnPPage -Name $name -LayoutType Article -HeaderLayoutType NoImage -CommentsEnabled:$false

#add sections
Add-PnPPageSection -Page $name -SectionTemplate TwoColumn -Order 1

#add text web part
Add-PnPPageTextPart -Page $name -Section 1 -Column 1 -Text " "

#add doclib
Add-PnPPageWebPart -Page $name -DefaultWebPartType List -Section 1 -Column 2 -WebPartProperties @{isDocumentLibrary="true";selectedListId="1fa1fb45-e53b-4ea1-9325-ddca7afe986e";selectedFolderPath="/$name";hideCommandBar="false"}
$page = Get-PnPPage -Identity $name
$page.Publish()
}
```
