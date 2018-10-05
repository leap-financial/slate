---
title: API Reference

language_tabs: 
  - shell

toc_footers:

search: true
---

# Authentication

We expect the API key to be included in all API requests to the server in a header that looks like the following:

`X-Api-Key: abrakadabra`

All requests should be submitted with a content-type `application/json`:

`Content-Type: application/json`

<aside class="notice">
You must replace <code>abrakadabra</code> with your personal API key.
</aside>

# Limits

- Do not send more than 1000 objects in any request.
- Do not simultaneously submit more than one request.

# Data Ingestion

## Shipments

```shell
curl https://leapfin.com/v1/data/shipment
  -H "X-Api-Key: abrakadabra" 
  -H "Content-Type: application/json"
  -X POST
  --data '[{"flex_id": "test"}]'
```

The request body must be a non-empty JSON array of objects, where each object has a unique `flex_id`. In cases where the object already exists in our system, the data will be appended (instead of updated).

### HTTP Request

`POST https://leapfin.com/v1/data/shipment`

### Object properties 

Property | Required | Description
--------- | ------- | -----------
flex_id | Yes | External ID

## Non-shipments

```shell
curl https://leapfin.com/v1/data/non-shipment
  -H "X-Api-Key: abrakadabra" 
  -H "Content-Type: application/json"
  -X POST
  --data '[{"invoice_id": "test"}]'
```

The request body must be a non-empty JSON array of objects, where each object has a unique `invoice_id`. In cases where the object already exists in our system, the data will be appended (instead of updated).

### HTTP Request

`POST https://leapfin.com/v1/data/non-shipment`

### Object properties

Property | Required | Description
--------- | ------- | -----------
invoice_id | Yes | External ID
