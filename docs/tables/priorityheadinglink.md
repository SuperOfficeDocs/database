---
uid: table-PriorityHeadingLink
title: PriorityHeadingLink table
description: Heading link table for Priority, for MDO headers
so.generated: true
keywords:
  - "database"
  - "PriorityHeadingLink"
so.date: 11.04.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# PriorityHeadingLink Table (81)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|priorityheadinglink\_id|Primary key|PK| |
|priority\_id|Link to Priority list table|FK [Priority](priority.md)| |
|heading\_id|Link to Heading table|FK [Heading](heading.md)| |
|registered|Registered when|UtcDateTime| |
|registered\_associate\_id|Registered by whom|FK [associate](associate.md)| |
|updated|Last updated when|UtcDateTime| |
|updated\_associate\_id|Last updated by whom|FK [associate](associate.md)| |
|updatedCount|Number of updates made to this record|UShort| |


![PriorityHeadingLink table relationship diagram](./media/PriorityHeadingLink.png)

[!include[details](./includes/priorityheadinglink.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|priorityheadinglink\_id |PK |Clustered, Unique |
|priority\_id |FK |Index |
|heading\_id |FK |Index |

## Replication Flags

* Replicate changes DOWN from central to satellites and travellers.
* Replicate changes UP from satellites and travellers back to central.
* Copy to satellite and travel prototypes.

## Security Flags

* No access control via user's Role.

