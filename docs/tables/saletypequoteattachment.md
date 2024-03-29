---
uid: table-SaleTypeQuoteAttachment
title: SaleTypeQuoteAttachment table
description: Default attachments to quotes linked to sales of this type
so.generated: true
keywords:
  - "database"
  - "SaleTypeQuoteAttachment"
so.date: 11.04.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# SaleTypeQuoteAttachment Table (446)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|saletypequoteattachment\_id|Primary key|PK| |
|SaleTypeId|Link to sale type|FK [SaleType](saletype.md)| |
|DocumentId|Link to document|FK [document](document.md)| |
|DefaultIncluded|Should this be a standard attachment (default state is &apos;include&apos;)|Bool|&#x25CF;|
|registered|Registered when|UtcDateTime| |
|registered\_associate\_id|Registered by whom|FK [associate](associate.md)| |
|updated|Last updated when|UtcDateTime| |
|updated\_associate\_id|Last updated by whom|FK [associate](associate.md)| |
|updatedCount|Number of updates made to this record|UShort| |


![SaleTypeQuoteAttachment table relationship diagram](./media/SaleTypeQuoteAttachment.png)

[!include[details](./includes/saletypequoteattachment.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|saletypequoteattachment\_id |PK |Clustered, Unique |

## Replication Flags

* None

## Security Flags

* No access control via user's Role.

