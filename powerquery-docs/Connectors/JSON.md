# JSON

## Summary

Release State: General Availability
Products: Power BI Desktop, Power BI Service (Enterprise Gateway), Dataflows in PowerBI.com (Enterprise Gateway), Dataflows in PowerApps.com (Enterprise Gateway), Excel

Authentication Types Supported:

Function Reference Documentation: [Json.Document](https://docs.microsoft.com/powerquery-m/json-document), [Xml.Document](https://docs.microsoft.com/en-us/powerquery-m/xml-document)

## Capabilities supported

* Import

## Load from JSON

### Load from file

Source: https://drill.apache.org/docs/sample-data-donuts/

To load a local JSON file, all you need to do is select the 'JSON' option in the connector selection. This will launch a local file browser and allow you to select your XML file. 

![XML file selection](../images/xmlbrowse.png)

This will automatically launch the Query Editor for you to transform the data if you want, or you can simply close and apply. JSON data is loaded in as a record, with the first column containing the names and the second column containing the values. The values are text, records, or lists. You are presented in the ribbon with the option to turn it into a table, and this may be what you want to do in some cases. This will preserve the initial structure you saw when you loaded it as a record.

If you want to drill down on a specific record or list, you can instead click on it. This can be done when you initially load the JSON, or after you convert it to Table. In either case the drill down will return a record or list of additional text, records, or lists.

Finally, if you want to transform your data such that you can easily expand records and lists in a way that keeps existing data in place (multiplying rows) rather than drilling down, you can either use the UI to convert to table (as in the first option), transpose the table, and then promote headers, or you can use the advanced editor.

If you want to use the advanced editor, the function you want to use is Table.FromRecords(). With the sample data, this is what the application would look like.

```
let
    Source = Json.Document(File.Contents(Path/donuts.json)),
    #"Converted to Table" = Table.FromRecords({Source})
in
    #"Converted to Table"
```

### Load from web

If you want to load an JSON file from the web, instead of selecting the JSON connector you can select the Web connector. Paste in the address of the desired file and you will be prompted with an authentication selection, since you're hitting a website rather than a static file. If there's no authentication, you can just select Anonymous. As in the local case, you will then be taken to the Query Editor.
