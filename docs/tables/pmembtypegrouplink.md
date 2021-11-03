---
uid: table-PMembTypeGroupLink
title: PMembTypeGroupLink table
description: User group link table for PMembType, for MDO item hiding
so.generated: true
keywords:
  - "database"
  - "PMembTypeGroupLink"
so.date: 11.02.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# PMembTypeGroupLink Table (92)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|pmembtypegrouplink\_id|Primary key|PK| |
|pmembtype\_id|Link to PMembType list table|FK [PMembType](pmembtype.md)| |
|group\_id|Link to Group table|FK [UserGroup](usergroup.md)| |
|registered|Registered when|UtcDateTime| |
|registered\_associate\_id|Registered by whom|FK [associate](associate.md)| |
|updated|Last updated when|UtcDateTime| |
|updated\_associate\_id|Last updated by whom|FK [associate](associate.md)| |
|updatedCount|Number of updates made to this record|UShort| |


![PMembTypeGroupLink table relationship diagram](./media/PMembTypeGroupLink.png)

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|pmembtypegrouplink\_id |PK |Clustered, Unique |
|pmembtype\_id |FK |Index |
|group\_id |FK |Index |

## Replication Flags

* Replicate changes DOWN from central to satellites and travellers.
* Replicate changes UP from satellites and travellers back to central.
* Copy to satellite and travel prototypes.

## Security Flags

* No access control via user's Role.

