# Sheetrock Raw Data fork


Sheetrock is a JavaScript library for querying, retrieving, and displaying data
from Google Sheets. In other words, use a Google spreadsheet as your database!
Load entire worksheets or leverage SQL-like queries to sort, group, and filter
data. All you need is the URL of a public Google Sheet.

This fork is intended to retrieve raw cell data from sheets into 2D array.

## Usage

```javascript

sheetrock({
  url: "https://docs.google.com/spreadsheets/d/1qT1LyvoAcb0HTsi2rHBltBVpUBumAUzT__rhMvrz5Rk/edit#gid=0",
  query: "select A,B,C,D,E,L where E = 'Both' order by L desc", //optional
  raw: true,
  callback: callback
});
```
### callback for options.raw=true

callback(error, options, response)

* error (object): If the request failed, this parameter will be a JavaScript
  error; otherwise, it will be `null`. Always test for an error before using
  the other parameters.

* options (object): An object representing the options of the request. The
  `user` property will contain the options you originally provided (useful for
  identifying which request the callback is for) and a `request` property with
  information about the HTTP request to Google’s API.

* response (object): An object containing response data properties:

  * `.raw` (object): This is the raw response data from Google’s API.

  * `.data` (2D array): An array of row objects (which are also passed individually to
    the `rowTemplate`, if one is provided).

##Original documentation

For the original project documentation, please visit

**[chriszarate.github.io/sheetrock][gh-pages]**.




