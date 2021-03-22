---
uid: table-reply-template-folder
title: reply\_template\_folder table
description: This table contains entries for folders for reply templates.
so.generated: true
keywords:
  - "database"
  - "reply_template_folder"
so.date: 22.03.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# reply\_template\_folder Table (276)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|id|The primary key (auto-incremented)|PK| |
|parent\_id|The id of the parent folder of this folder. NULL or -1 of this is a toplevel folder.|FK [reply-template-folder](reply-template-folder.md)| |
|name|The name of this folder.|String(64)| |
|description|The description of this folder.|String(255)|&#x25CF;|
|flags|A bitmap for this folder.|Int|&#x25CF;|
|fullname|The full name of this folder , i.e. Foo/bar/test.|Clob|&#x25CF;|


![reply_template_folder table relationship diagram](./media/reply_template_folder.png)

[!include[details](./includes/reply-template-folder.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|id |PK |Clustered, Unique |
|parent\_id |FK |Index |
|name |String(64) |Index |

## Replication Flags

* None

## Security Flags

* No access control via user's Role.
