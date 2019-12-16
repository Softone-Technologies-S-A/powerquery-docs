Files (All)
Release State: General Availability
Products: Power BI Desktop, Power BI Service (Enterprise Gateway - Web.Page), Dataflows in PowerBI.com (Enterprise Gateway - Web.Page), Dataflows in PowerApps.com (Enterprise Gateway - Web.Page), Excel (minus PDF)

Authentication Types Supported:

Prerequisites: None

Capabilities supported:
Document per connector

Test
CSV
XML
JSON
PDF
Web.Page
Web.Contents

XML

Both XML functions don't do a good job of surfacing data in a consistent shape. Users are going to have to do extra data shaping to get it into the sort of shape they will want to see it in.

Xml.Tables (whatever the UI uses)
If you have similarly structured entries, and you have text nodes with a title entry for each, and one of those nodes has extra tags on the title, it drops everything outside the tag. It does text or nodes, not mixed.

Xml.Document
Returns mixed content as text, including nested tags, etc.
