---
uid: s_washing_list
title: s_washing_list table
description: Unused table that is ment to be used for active washing in spm v2
so.generated: true
keywords:
  - "database"
  - "s_washing_list"
so.date: 19.03.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# SWashingList Table (343)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|id|Primary key|PK| |
|list\_id|Reference to a list to wash|FK [s_list](s_list.md)| |
|address|Not known, probably usefull in the future :)|String(255)| |


![s_washing_list table relationship diagram](media\s_washing_list.png)

[!include[details](./includes/s-washing-list.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|id |PK |Clustered, Unique |
|list\_id |FK |Index |

## Replication Flags

* None

## Security Flags

* No access control via user's Role.
