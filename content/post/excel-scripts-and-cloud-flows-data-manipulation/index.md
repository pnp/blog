---
title: "Excel Scripts and Cloud Flows - Data Manipulation"
date: 2021-05-17T12:50:00-04:00
author: "Damien Bird"
githubname: DamoBird365
categories: ["Community post"]
images:
- images/Capture.PNG
tags: ["Power Automate"]
type: "regular"
---
 

Have you discovered that the existing Power Automate actions for Excel
are limited to Excel Tables?  Are you looking to take your cloud flow
interactions with Excel to the next level?  Maybe it's time to start
looking at [Excel
Scripts](https://support.microsoft.com/office/introduction-to-office-scripts-in-excel-9fbe283d-adb8-4f13-a75b-a81c6baf163a)
which are currently accessible to Power Automate as a Preview Feature.
 
What are Excel Scripts?  Using either the built in recording tool or
TypeScript programming language you can create a script to update cells,
rows or ranges of data or indeed insert formulas into cells.  You can
even use Excel to perform some of the features missing to Power Automate
like [sorting an
array](https://www.tachytelic.net/2021/04/power-automate-sort-array-objects/).
 
I have prepared a two part video series demo'ing how you can use Power
Automate and Excel Scripts to both send data to a plain excel file and
populate cells, rows and ranges but also in return, again using Excel
Scripts, how you can create a table in an Excel file and return the
available data either as a results array for your next action in your
Cloud Flow OR by using the list all rows action based on the newly
created table.  
 
**First Video** on Populating Excel from Cloud Flows is available here:
 
 
The below Cloud Flow is relatively straight forward for this first part
demo.  We have an array of Rows for our Excel Worksheet and this
demonstrates one of many ways to pass data to Excel via the Script
Action.  The real benefit of creating a bespoke function in Excel
Scripts is that the Script Action is dynamic.  It will return the fields
you have defined in the action window and ensure the datatype provided
is correct, i.e. string or number.
 
![DamoBird365_0-1621076762535.png](images/DamoBird365_0-1621076762535.png)
 

In the sample Typescript Excel Script built below, you can try this for
yourself.  The script will populate unique cells, columns and rows with
data based on the 4 variable types defined, examplevar1-4 as strings,
numbers, multivariables and arrays.
 
 
```javascript
function main(workbook: ExcelScript.Workbook,
  examplevar1: string,
  examplevar2: number,
  examplevar3: multivariable, //Header of Table
  examplevar4: arrayvar[] //Multiple rows in Table
) {
  let selectedSheet = workbook.getActiveWorksheet();
  
  // Set cells A1,B2,C3,D4 on selectedSheet
  selectedSheet.getRange("A1").setValue(examplevar1);
  selectedSheet.getRange("B2").setValue(examplevar2);
  selectedSheet.getRange("C3").setValue(examplevar1 + ' ' + examplevar2);
  selectedSheet.getRange("D4").setValue(examplevar2 + 1111);
  //An example function to reverse the strings
  function reverseString(str: string) {
    return str.split("").reverse().join("");
  }
  //Create Vertical Header Row with Multi Variables
  const formattedColumn = [
    [reverseString(examplevar3.multivar3var1)], 
    [reverseString(examplevar3.multivar3var2)],
    [reverseString(examplevar3.multivar3var3)],
    [reverseString(examplevar3.multivar3var4)],
    [reverseString(examplevar3.multivar3var5)],
    [reverseString(examplevar3.multivar3var6)]];
  selectedSheet.getRange("F1:F6").setValues(formattedColumn);
  //Create Horizontal Header Row with Multi Variables 
  const formattedHeader = [[examplevar3.multivar3var1, examplevar3.multivar3var2, examplevar3.multivar3var3, examplevar3.multivar3var4, examplevar3.multivar3var5, examplevar3.multivar3var6]];
    
  selectedSheet.getRange("A8:F8").setValues(formattedHeader);
  //Populate rows below Header Row with Array Variable 
  const starterrow = 9; //starting row for "table" data
  
  for (let i = 0; i < examplevar4.length; i++) {
    const currentObject = examplevar4[i];
    const formattedrow = [[currentObject.arr4var1, currentObject.arr4var2, currentObject.arr4var3, currentObject.arr4var4, currentObject.arr4var5, currentObject.arr4var6,]];
    const rowRange = `A${starterrow + i}:F${starterrow + i}`;
    selectedSheet.getRange(rowRange).setValues(formattedrow);
  }
  //Return a response to the Cloud Flow
  return "DamoBird365 Loaded " + examplevar4.length + " Records Loaded into Excel and Demo Completed OK"
}
//Defining Interfaces for MultiVar and Array
interface multivariable {
  multivar3var1: string,
  multivar3var2: string,
  multivar3var3: string,
  multivar3var4: string,
  multivar3var5: string,
  multivar3var6: string
}
interface arrayvar {
  arr4var1: number,
  arr4var2: string,
  arr4var3: string,
  arr4var4: string,
  arr4var5: string,
  arr4var6: string
}
```
 
 
**Second video** on retrieving data back from Excel files without a
table.  Identify the active cells, define and create a table via the
script and return the data to your cloud flow as either a result to the
script action or via the traditional list rows actions.
 
 
The Cloud flow on this occasion does not require any data input as its
purpose is to return data back to the flow.  Whilst the data could be
fully repurposed in Excel, as a **Power Automate enthusiast**, I have
used a select action to reformat the Array and rename the keys.  Both
the Select Action and the List Rows Action demonstrate the two methods
for retrieving data from Excel where no table was present previously.
 
![DamoBird365_1-1621076794170.png](images/DamoBird365_1-1621076794170.png)
 
Again, in the sample Typescript Excel Script built below, you can
quickly test out the functionality of creating a table and returning
data to your cloud flow.  The code is commented to help you understand
how the solution is built.  Please note I am not a coder but with the
available resources online, I was quickly able to understand how to put
this together.  The recording tool is also useful for getting an
understanding of some of the functions available.
 
 
```javascript
function main(workbook: ExcelScript.Workbook) {
  // Get the first worksheet 
  const selectedSheet = workbook.getFirstWorksheet();
  //get active range of WorkSheet
  let range = workbook.getActiveWorksheet().getUsedRange();
  // Get last used row of WorkSheet
  let lastrow = range.getRowCount();
  // Find first reference of ID in selectedSheet i.e. header row
  let IDCell = selectedSheet.getRange("A1").find("ID", { completeMatch: true, matchCase: true, searchDirection: ExcelScript.SearchDirection.forward });
  // Get the current active cell in the workbook.
  //and format current cell without Sheet1! reference
  let activeCell = IDCell.getAddress().replace("Sheet1!", "");
  //get table range  
  const TableRange = `${activeCell}:F${lastrow}`;
  // Create a table using the data range.
  let newTable = workbook.addTable(selectedSheet.getRange(TableRange), true);
  newTable.setName("NewTableInExcel");
  // Get the first (and only) table in the worksheet.
  let table = selectedSheet.getTables()[0];
  // Get the data from the table.
  let tableValues = table.getRange().getValues();
  //Return a response to the Cloud Flow
  return tableValues
}
```
 
 
**Where do you find Excel Scripts Functionality?**  It's an Excel
Online feature.  Load up Excel and select  the Automate Tab.  Here you
can view all scripts, record some actions and edit new or existing
scripts that have been built.
 

![DamoBird365_0-1621236507649.png](images/DamoBird365_0-1621236507649.png)

 
**Wondering where they live?**  Jump onto OneDrive and take a look at
Documents/Office Scripts where you can export/import and share.
 

![DamoBird365_1-1621236596024.png](images/DamoBird365_1-1621236596024.png)

 
Want to see a proof of concept ?  Take a look at my [Invoicing Demo](https://damobird365.birdhoose.co.uk/2021/03/24/power-automate-office-scripts-populate-an-excel-template-dynamically-using-type-script/)
where I show you how you could autocompete an excel invoice template
using scripts.  I recently covered this in a live demo with the Monthly
(12th May) Microsoft Office Scripts Dev Team and included a bonus
feature, converting the excel files to PDF using the same flow without
premium actions.  Look out for this video on
[Microsoft 365 Developer Youtube channel](https://www.youtube.com/c/Microsoft365Developer/videos) soon.
 
Please let me know if you found this useful and what you might use Excel
Scripts for next.
