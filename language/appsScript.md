**Author:** Duarte Matos
###### tags: `Language`, `App Script`

# Apps Script

![](https://i.imgur.com/ovUWux1.png)

## What is Apps Script?
Apps Script is a rapid application development platform that gives you the ability to automate, customize, and extend your G Suite experience. With Apps Script, you can automate and streamline onerous or complex work in G Suite, saving you and your team time and effort.

## Benefits
1. Apps Script's built-in services let you read, update, and manipulate your G Suite application data with scripts.
2. You can create scripts using Apps Script's in-browser code editor—there's no need to install or run code development software.
3. You can design user interfaces for G Suite editors that let you activate scripts directly from those editors with menu items, dialogs, and sidebars.

## Apps Script Power Example
Create a simple document on **Docs**
```
function myFunction() {
    var doc = DocumentApp.create('New Doc')
}
```
If we want to write some text on some document
```
function myFunction() {
    var doc = DocumentApp.create('New Doc 2')
    var body = doc.getBody()
    var helloWorld = body.appendParagraph('Hello World')
}
```
If you want to send a email with this attached document
```
function myFunction() {
    var doc = DocumentApp.create('New Doc 3')
    var body = doc.getBody()
    var helloWorld = body.appendParagraph('Hello World')
    var email = Session.getActiveUser().getEmail()
    var subject = doc.getName()
    var bodyEmail = 'This is the new doc =' + doc.getUrl()
    var gmail = gmailApp.sendEmail(email, subject, bodyEmail)
    }
```


# Google Sheets #1:Macros & Custom Functions
## The Spreadsheet service
You can use Apps Script to extend Google Sheets in order to save you time and effort. Apps Script provides the Spreadsheet service which allows scripts to interact with your Google Sheet files and the data they contain. You can use this service to automate the following common spreadsheet tasks:

- Create or modify a spreadsheet.
- Read and update cell data, formula, and formatting.
- Create custom buttons and menus.
- Import and export data from other Google applications or third-party sources.
- Share and control access to spreadsheets
- ...and much more.

## Introduction
A macro is a series of recorded actions within Google Sheets. Once recorded, you can activate a macro to repeat those actions later with a menu item or shortcut key. You can both create and update your own macros in both Google Sheets and the Apps Script code editor.

In the Apps Script code editor, you can also create custom functions. Similar to the built-in functions Sheets offers (such as **SUM** or **AVERAGE**), you can use Google Apps Script to write your own custom functions for simple and niche operations (such as conversions or string concatenation). Once created, you can call these functions in Sheets as you would a built-in function. Custom functions can also be used in cell formulas you write, combining them with other functions as needed.

## What you'll learn
- How to create a script for Google Sheets.
- How to navigate the Apps Script editor.
- How to create and update macros.
- How to create your first Sheets custom function.

## What you'll need
- Basic familiarity with JavaScript
- Basic familiarity with Google Sheets
- Ability to read Sheets A1 Notation

https://codelabs.developers.google.com/codelabs/apps-script-fundamentals-1/#2







