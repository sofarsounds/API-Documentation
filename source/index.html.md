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
    "title": "London",
    "latitude": "-51.5074",
    "longitude": "-0.1278",
    "country": "United Kingdom",
    "currency": "GBP"
  },
  {
    "id": 1,
    "title": "New York",
    "latitude": "40.7128",
    "longitude": "74.0059",
    "country": "United States",
    "currency": "USD"
  }
]
```

This endpoint retrieves all cities.

### HTTP Request

`GET http://example.com/api/v1/cities`

Parameter | Description
--------- | -----------
id | Sofar Sounds unique city id
title | The title of the city
latitude | Latitude for this city
longitude | Longitude for this city
country | Country this city is in
currency | The currency the city takes payment in

## Get the nearest city

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "title": "London",
  "latitude": "-51.5074",
  "longitude": "-0.1278",
  "country": "United Kingdom",
  "currency": "GBP"
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

### Returned Parameters

Parameter | Description
--------- | -----------
id | Sofar Sounds unique city id
title | The title of the city
latitude | Latitude for this city
longitude | Longitude for this city
country | Country this city is in
currency | The currency the city takes payment in

# Events

## Get all events

> The above command returns JSON structured like this:

```json
[
  {
    "id": 2,
    "location_name": 'Shoreditch',
    "location_latitude": '-51.5285',
    "location_longitude": '-0.0847',,
    "closest_station": 'Old Street,
    "type": "Home",
    "image_url": 'http://cloudfront.com/url',
    "arrival_time": "2017-12-01 19:30",
    "start_time": "2017-12-01 20:00",
    "end_time": '2017-12-01 22:30',
    "ticket_price": '10.00'
  },
  {
    "id": 5,
    "location_name": 'Peckham',
    "location_latitude": '-51.4742',
    "location_longitude": '-0.0691',
    "closest_station": 'Old Street',
    "type": "Home",
    "image_url": 'http://cloudfront.com/url',
    "arrival_time": "2017-12-05 19:30",
    "start_time": "2017-12-05 20:00",
    "end_time": '2017-12-05 22:30',
    "ticket_price": '10.00',
    "closest_station": "Peckham Rye"
  }
```

This endpoint retrieves a list of all upcoming appliable events.


### HTTP Request

`GET http://example.com/api/v1/events`

### Returned Parameters

Parameter | Description
--------- | -----------
id | The unique event id
location_name | The neighbourhood of the event
location_latitude | The latitude for the neigbourhood
location_longitude | The longtiude for the beighbourhood
closest_station | The name of the closest station
type | The type of location either home/commercial
image_url | The url on the CDN for the event image
arrival_time | The arrival time including the date
start_time | The start time/date of the event
end_time | The end time/date of the event
ticket_price | The price of a ticket (charged in the cities currency)
