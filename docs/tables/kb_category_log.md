---
uid: kb_category_log
title: kb_category_log table
description: Who and when, if somebody edits a knowledge base folder
so.generated: true
keywords:
  - "database"
  - "kb_category_log"
so.date: 19.03.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# KbCategoryLog Table (291)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|id|The primary key (auto-incremented)|PK| |
|kb\_category\_id|The id of the kb_category that triggered this action.|FK [kb_category](kb_category.md)| |
|user\_id|The id of the user that created this comment.|FK [ejuser](ejuser.md)| |
|log\_when|When the action occured.|DateTime|&#x25CF;|


![kb_category_log table relationship diagram](media\kb_category_log.png)

[!include[details](./includes/kb-category-log.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|id |PK |Clustered, Unique |
|kb\_category\_id |FK |Index |
|user\_id |FK |Index |

## Replication Flags

* None

## Security Flags

* No access control via user's Role.
