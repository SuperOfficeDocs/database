---
uid: table-ReasonGroupLink
title: ReasonGroupLink table
description: User group link table for Reason, for MDO item hiding
so.generated: true
keywords:
  - "database"
  - "ReasonGroupLink"
so.date: 11.04.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# ReasonGroupLink Table (104)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|reasongrouplink\_id|Primary key|PK| |
|reason\_id|Link to Reason list table|FK [Reason](reason.md)| |
|group\_id|Link to Group table|FK [UserGroup](usergroup.md)| |
|registered|Registered when|UtcDateTime| |
|registered\_associate\_id|Registered by whom|FK [associate](associate.md)| |
|updated|Last updated when|UtcDateTime| |
|updated\_associate\_id|Last updated by whom|FK [associate](associate.md)| |
|updatedCount|Number of updates made to this record|UShort| |


![ReasonGroupLink table relationship diagram](./media/ReasonGroupLink.png)

[!include[details](./includes/reasongrouplink.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|reasongrouplink\_id |PK |Clustered, Unique |
|reason\_id |FK |Index |
|group\_id |FK |Index |

## Replication Flags

* Replicate changes DOWN from central to satellites and travellers.
* Replicate changes UP from satellites and travellers back to central.
* Copy to satellite and travel prototypes.

## Security Flags

* No access control via user's Role.

