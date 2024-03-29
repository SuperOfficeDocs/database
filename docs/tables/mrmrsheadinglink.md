---
uid: table-MrMrsHeadingLink
title: MrMrsHeadingLink table
description: Heading link table for MrMrs, for MDO headers
so.generated: true
keywords:
  - "database"
  - "MrMrsHeadingLink"
so.date: 11.04.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# MrMrsHeadingLink Table (96)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|mrmrsheadinglink\_id|Primary key|PK| |
|mrmrs\_id|Link to MrMrs list table|FK [MrMrs](mrmrs.md)| |
|heading\_id|Link to Heading table|FK [Heading](heading.md)| |
|registered|Registered when|UtcDateTime| |
|registered\_associate\_id|Registered by whom|FK [associate](associate.md)| |
|updated|Last updated when|UtcDateTime| |
|updated\_associate\_id|Last updated by whom|FK [associate](associate.md)| |
|updatedCount|Number of updates made to this record|UShort| |


![MrMrsHeadingLink table relationship diagram](./media/MrMrsHeadingLink.png)

[!include[details](./includes/mrmrsheadinglink.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|mrmrsheadinglink\_id |PK |Clustered, Unique |
|mrmrs\_id |FK |Index |
|heading\_id |FK |Index |

## Replication Flags

* Replicate changes DOWN from central to satellites and travellers.
* Replicate changes UP from satellites and travellers back to central.
* Copy to satellite and travel prototypes.

## Security Flags

* No access control via user's Role.

