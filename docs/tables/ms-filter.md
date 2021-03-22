---
uid: table-ms-filter
title: ms\_filter table
description: This table contains email filters. These are the filters allowing you to do advanced parsing of incomming emails.
so.generated: true
keywords:
  - "database"
  - "ms_filter"
so.date: 22.03.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# ms\_filter Table (310)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|id|The primary key (auto-incremented)|PK| |
|priority|A number indicating the priority for this filter (0..10).|Int| |
|description|A description for this filter.|String(255)|&#x25CF;|
|search\_string|The string to search for.|String(255)|&#x25CF;|
|search\_string2|A second string to search for. Only used if not empty.|String(255)|&#x25CF;|
|search\_location|Enum indicating where to search.|search-location| |
|action|A bitmask representing the actions that should be performed if this filter is executed.|Int| |
|action\_when|Enum indicating what should trigger this filter.|action-when| |
|new\_priority|The id of the priority to set for the ticket if specified by action.|FK [ticket-priority](ticket-priority.md)| |
|new\_category|The id of the category to set for the ticket if specified by action.|FK [ej-category](ej-category.md)| |
|new\_owner|The id of the owner to set for the ticket if specified by action.|FK [ejuser](ejuser.md)| |
|new\_slevel|The security level to set for the ticket if specified by action.|Int| |
|reply\_template|The id of the template to use as the reply template if specified by action.|FK [reply-template](reply-template.md)| |
|reply\_to|The email address to reply to.|String(255)|&#x25CF;|
|reply\_to\_sms|The SMS number to reply to.|String(255)|&#x25CF;|
|body\_template|The template to use for the body of the message.|FK [reply-template](reply-template.md)| |
|forward\_to|An email address to forward the ticket to.|String(255)|&#x25CF;|
|autofaq\_reply\_category|The root folder for the auto faq search.|FK [reply-template-folder](reply-template-folder.md)| |
|flags|Flags|Int|&#x25CF;|
|parse\_mode|If automatic parsing this column indicate mode|Short|&#x25CF;|
|ejscript|The reference to the ejscript to execute for this filter.|FK [ejscript](ejscript.md)|&#x25CF;|


![ms_filter table relationship diagram](./media/ms_filter.png)

[!include[details](./includes/ms-filter.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|id |PK |Clustered, Unique |
|new\_priority |FK |Index |
|new\_category |FK |Index |
|new\_owner |FK |Index |
|reply\_template |FK |Index |
|body\_template |FK |Index |
|autofaq\_reply\_category |FK |Index |
|ejscript |FK |Index |

## Replication Flags

* None

## Security Flags

* No access control via user's Role.
