---
title: Sofar Sounds API Reference

language_tabs:
  - shell
  - ruby
  - javascript

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

This documentation is the implementation details for the Sofar Sounds.  This is beta and is still in development and subject to change.


# Cities

## Get All Cities

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all cities.

### HTTP Request

`GET http://example.com/api/v1/cities`

## Get the nearest city

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a the closest city from latitude/longitude.


### HTTP Request

`GET http://example.com/api/v1/cities/nearest`

### URL Parameters

Parameter | Description
--------- | -----------
latitude | The latitude of the users current location
longitude | The longitude of the users current location

# Events

## Get all events

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a the closest city from latitude/longitude.


### HTTP Request

`GET http://example.com/api/v1/events`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

