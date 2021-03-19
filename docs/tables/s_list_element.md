---
uid: s_list_element
title: s_list_element table
description: Elements in a static list.
so.generated: true
keywords:
  - "database"
  - "s_list_element"
so.date: 19.03.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# SListElement Table (345)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|id|Primary key|PK| |
|list\_id|Which list this element belongs to|FK [s_list](s_list.md)| |
|address|The email address of this element|String(255)| |
|name|The name of the recipient|String(255)|&#x25CF;|
|sms|The sms number for this element|String(255)| |
|status|Status for the statical list element|Enum [ElementStatus](enums\EnumElementStatus.md)| |


![s_list_element table relationship diagram](media\s_list_element.png)

[!include[details](./includes/s-list-element.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|id |PK |Clustered, Unique |
|list\_id |FK |Index |
|address |String(255) |Index |
|sms |String(255) |Index |

## Replication Flags

* None

## Security Flags

* No access control via user's Role.
