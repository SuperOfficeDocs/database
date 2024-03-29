---
uid: table-CurrencyGroupLink
title: CurrencyGroupLink table
description: User group link table for Currency, for MDO item hiding
so.generated: true
keywords:
  - "database"
  - "CurrencyGroupLink"
so.date: 11.04.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# CurrencyGroupLink Table (113)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|currencygrouplink\_id|Primary key|PK| |
|currency\_id|Link to Currency list table|FK [Currency](currency.md)| |
|group\_id|Link to Group table|FK [UserGroup](usergroup.md)| |
|registered|Registered when|UtcDateTime| |
|registered\_associate\_id|Registered by whom|FK [associate](associate.md)| |
|updated|Last updated when|UtcDateTime| |
|updated\_associate\_id|Last updated by whom|FK [associate](associate.md)| |
|updatedCount|Number of updates made to this record|UShort| |


![CurrencyGroupLink table relationship diagram](./media/CurrencyGroupLink.png)

[!include[details](./includes/currencygrouplink.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|currencygrouplink\_id |PK |Clustered, Unique |
|currency\_id |FK |Index |
|group\_id |FK |Index |

## Replication Flags

* Replicate changes DOWN from central to satellites and travellers.
* Replicate changes UP from satellites and travellers back to central.
* Copy to satellite and travel prototypes.

## Security Flags

* No access control via user's Role.

