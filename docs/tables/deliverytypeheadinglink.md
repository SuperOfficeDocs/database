---
uid: table-DeliveryTypeHeadingLink
title: DeliveryTypeHeadingLink table
description: Heading link table for DeliveryType, for MDO item headings
so.generated: true
keywords:
  - "database"
  - "DeliveryTypeHeadingLink"
so.date: 11.04.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# DeliveryTypeHeadingLink Table (438)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|deliverytypeheadinglink\_id|Primary key|PK| |
|deliverytype\_id|Link to DeliveryType list table|FK [DeliveryType](deliverytype.md)| |
|heading\_id|Link to Heading table|FK [Heading](heading.md)| |
|registered|Registered when|UtcDateTime| |
|registered\_associate\_id|Registered by whom|FK [associate](associate.md)| |
|updated|Last updated when|UtcDateTime| |
|updated\_associate\_id|Last updated by whom|FK [associate](associate.md)| |
|updatedCount|Number of updates made to this record|UShort| |


![DeliveryTypeHeadingLink table relationship diagram](./media/DeliveryTypeHeadingLink.png)

[!include[details](./includes/deliverytypeheadinglink.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|deliverytypeheadinglink\_id |PK |Clustered, Unique |
|deliverytype\_id |FK |Index |
|heading\_id |FK |Index |

## Replication Flags

* Replicate changes DOWN from central to satellites and travellers.
* Replicate changes UP from satellites and travellers back to central.
* Copy to satellite and travel prototypes.

## Security Flags

* No access control via user's Role.

