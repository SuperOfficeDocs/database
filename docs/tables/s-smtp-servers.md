---
uid: table-s-smtp-servers
title: s\_smtp\_servers table
description: Contains the smtp server for a shipment
so.generated: true
keywords:
  - "database"
  - "s_smtp_servers"
so.date: 22.03.2021
so.topic: reference
so.envir:
  - "onsite"
  - "online"
---

# s\_smtp\_servers Table (390)

## Fields

| Name | Description | Type | Null |
|------|-------------|------|:----:|
|id|Primary key|PK| |
|shipment\_id|Reference to the shipment which this smtp server belongs to|FK [s-shipment](s-shipment.md)| |
|smtp\_server|The actual smtp server|String(255)|&#x25CF;|
|smtp\_port|The port of the SMTP server.|Int| |


![s_smtp_servers table relationship diagram](./media/s_smtp_servers.png)

[!include[details](./includes/s-smtp-servers.md)]

## Indexes

| Fields | Types | Description |
|--------|-------|-------------|
|id |PK |Clustered, Unique |
|shipment\_id |FK |Index |

## Replication Flags

* None

## Security Flags

* No access control via user's Role.
