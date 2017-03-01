---
title: Sofar Sounds API Reference

language_tabs:
  - shell
  - ruby
  - javascript

toc_footers:
  - <a href="https://github.com/tripit/slate">Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

This documentation is the implementation details for the Sofar Sounds.  This is beta and is still in development and subject to change.



# Authentication

A user can be authenticated by sending an / password to the signin route.  If authentication succeeds a token will be returned along with the user details.  This token can then be sent in later requests as an X_SESSION_TOKEN header to authenticate the user. 

## Sign in a user

> A succesful command returns JSON structured like this:

```
{
  "token": "2pJr4k_9QQJUsxeVVviy",
  "user": {
    "first_name": "John",
    "last_name": "Doe",
    "email": "john@example.com",
    "birth_year": "1983",
    "mobile_notification_on": false,
    "mobile_country_code": "GB",
    "mobile_number": "7890123456",
    "gender": "male",
    "push_notification_gig_offers": false,
    "push_notification_gig_updates": false,
    "push_notification_gig_suggestions": false,
    "email_setting_unlucky": true,
    "email_setting_marketing": true,
    "email_setting_offers": true,
    "gig_preferences": {
      "day_of_week": {
        "monday": false,
        "friday": false,
        "sunday": false,
        "tuesday": false,
        "thursday": false,
        "saturday": false,
        "wednesday": false
      }
    }
  }
}
```

> An unsuccesful command returns JSON structured like this:

```json
{
  "error": "Sorry, the entered email may be incorrect. If this problem persists, please email website@sofarsounds.com"
}
```

This endpoint will return a token which can be used in subsequent requests to authenticate against a user or it will return error responses.

### HTTP Request

`GET http://www.sofarsounds.com/api/v1/signin`

Parameter | Description
--------- | -----------
email | An email address to authenticate with
password | A password to authenticate with

### Return Parameters

Parameter | Description
----------|------------
token | A token that can be used to authenticate on later requests
user | An additional structure of users details. [Find out more about the user object](#user)

# Account

## Request a password reset

> Will return JSON:

```json
{
  "success": "Password reset request created"
}
```

This will trigger an email to be sent with password reset instructions, which will direct to the website not the app. This will return success wether we send a password reset request or not.

### HTTP request

`POST http://www.sofarsounds.com/api/v1/reset_password_request`

Parameter | Description
----------|-----------
email | An email address to reset the password on







# Users


## Create an account

> A succesful command returns JSON structured like this:

```
{
  "token": "2pJr4k_9QQJUsxeVVviy",
  "user": {
    "first_name": "John",
    "last_name": "Doe",
    "email": "john@example.com",
    "birth_year": "1983",
    "mobile_notification_on": false,
    "mobile_country_code": "GB",
    "mobile_number": "7890123456",
    "gender": "male",
    "push_notification_gig_offers": false,
    "push_notification_gig_updates": false,
    "push_notification_gig_suggestions": false,
    "email_setting_unlucky": true,
    "email_setting_marketing": true,
    "email_setting_offers": true,
    "gig_preferences": {
      "day_of_week": {
        "monday": false,
        "friday": false,
        "sunday": false,
        "tuesday": false,
        "thursday": false,
        "saturday": false,
        "wednesday": false
      }
    }
  }
}
```

Creates an account on the platform

###HTTP Request

`POST http://www.sofarsounds.com/api/v1/user`

Parameter | Description
----------|------------
first_name | First name for accout
last_name | Last name for account
email | Email for account
password | Password for account

### Return Parameters

Parameter | Description
----------|------------
token | Can be used for later authentication
user | An additional structure of users details. [Find out more about the user object](#user)

## Get account details

> A succesful command returns JSON structured like this:

```
{
  "first_name": "John",
  "last_name": "Doe",
  "email": "john@example.com",
  "birth_year": "1983",
  "mobile_notification_on": false,
  "mobile_country_code": "GB",
  "mobile_number": "7890123456",
  "gender": "male",
  "push_notification_gig_offers": false,
  "push_notification_gig_updates": false,
  "push_notification_gig_suggestions": false,
  "email_setting_unlucky": true,
  "email_setting_marketing": true,
  "email_setting_offers": true,
  "gig_preferences": {
    "day_of_week": {
      "monday": false,
      "friday": false,
      "sunday": false,
      "tuesday": false,
      "thursday": false,
      "saturday": false,
      "wednesday": false
    }
  }
}
```

Returns the details for the user who is authenticated

###HTTP Request

`GET http://www.sofarsounds.com/api/v1/user`

### Return Parameters

Parameter | Description
----------|------------
user | An structure of users details. [Find out more about the user object](#user)

## Update account details

> A succesful command returns JSON structured like this:

```
{
  "first_name": "John",
  "last_name": "Doe",
  "email": "john@example.com",
  "birth_year": "1983",
  "mobile_notification_on": false,
  "mobile_country_code": "GB",
  "mobile_number": "7890123456",
  "gender": "male",
  "push_notification_gig_offers": false,
  "push_notification_gig_updates": false,
  "push_notification_gig_suggestions": false,
  "email_setting_unlucky": true,
  "email_setting_marketing": true,
  "email_setting_offers": true,
  "gig_preferences": {
    "day_of_week": {
      "monday": false,
      "friday": false,
      "sunday": false,
      "tuesday": false,
      "thursday": false,
      "saturday": false,
      "wednesday": false
    }
  }
}
```


Updates the details for the user who is authenticated

###HTTP Request

`PUT http://www.sofarsounds.com/api/v1/user`

Parameter | Description
--------- | -----------
first_name |
last_name |
email |
password |
gender |
birth_year |
email_setting_marketing |
email_setting_offers |
email_setting_unlucky |
push_notification_gig_updates |
push_notification_gig_suggestions |
push_notification_gig_offers |
mobile_notification_on |
mobile_country_code |
mobile_number_body |

## Register a push token

Registers a new push token for the authenticated user

###HTTP Request

`POST http://www.sofarsounds.com/api/v1/user/push_tokens`

Parameter | Description
--------- | -----------
token | The token provided for push notfications
os | either ios or android




# Gig Preferences

## Day of the week

> A succesful command returns JSON structured like this:

```
{
  "first_name": "John",
  "last_name": "Doe",
  "email": "john@example.com",
  "birth_year": "1983",
  "mobile_notification_on": false,
  "mobile_country_code": "GB",
  "mobile_number": "7890123456",
  "gender": "male",
  "push_notification_gig_offers": false,
  "push_notification_gig_updates": false,
  "push_notification_gig_suggestions": false,
  "email_setting_unlucky": true,
  "email_setting_marketing": true,
  "email_setting_offers": true,
  "gig_preferences": {
    "day_of_week": {
      "monday": "true",
      "friday": "true",
      "sunday": "true",
      "tuesday": "true",
      "thursday": "true",
      "saturday": "true",
      "wednesday": "true"
    }
  }
}
```

Update the users preference for days of the week they would like to attend

###HTTP Request

`PUT http://www.sofarsounds.com/api/v1/user/gig_preferences/day_of_week`

Parameter | Description
----------|------------
monday | true/false if they want to attend an event on this day
tuesday | true/false if they want to attend an event on this day
wednesday | true/false if they want to attend an event on this day
thursday | true/false if they want to attend an event on this day
friday | true/false if they want to attend an event on this day
saturday | true/false if they want to attend an event on this day
sunday | true/false if they want to attend an event on this day

### Return Parameters

Parameter | Description
----------|------------
user | An additional structure of users details. [Find out more about the user object](#user)





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

`GET http://www.sofarsounds.com/api/v1/cities`

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

`GET http://www.sofarsounds.com/api/v1/cities/nearest`

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
    "location_name": "Shoreditch",
    "location_latitude": "-51.5285",
    "location_longitude": "-0.0847",
    "closest_station": "Old Street",
    "type": "Home",
    "image_url": "http://cloudfront.com/url",
    "arrival_time": "2017-12-01 19:30",
    "start_time": "2017-12-01 20:00",
    "end_time": "2017-12-01 22:30",
    "ticket_price": "10.00",
    "event_url": "https://www.sofarsounds.com/cities/london/events/2"
  },
  {
    "id": 5,
    "location_name": "Peckham",
    "location_latitude": "-51.4742",
    "location_longitude": "-0.0691",
    "closest_station": "Old Street",
    "type": "Home",
    "image_url": "http://cloudfront.com/url",
    "arrival_time": "2017-12-05 19:30",
    "start_time": "2017-12-05 20:00",
    "end_time": "2017-12-05 22:30",
    "ticket_price": "10.00",
    "closest_station": "Peckham Rye",
    "event_url": "https://www.sofarsounds.com/cities/london/events/5"
  }
```

This endpoint retrieves a list of all upcoming appliable events.


### HTTP Request

`GET http://www.sofarsounds.com/api/v1/events`

### Returned Parameters

Parameter | Description
--------- | -----------
events | A list of event structures. [Find out more about the event object](#event)


## Get all events for a city

> The above command returns JSON structured like this:

```json
[
  {
    "id": 2,
    "location_name": "Shoreditch",
    "location_latitude": "-51.5285",
    "location_longitude": "-0.0847",
    "closest_station": "Old Street",
    "type": "Home",
    "image_url": "http://cloudfront.com/url",
    "arrival_time": "2017-12-01 19:30",
    "start_time": "2017-12-01 20:00",
    "end_time": "2017-12-01 22:30",
    "ticket_price": "10.00",
    "event_url": "https://www.sofarsounds.com/cities/london/events/2"
  },
  {
    "id": 5,
    "location_name": "Peckham",
    "location_latitude": "-51.4742",
    "location_longitude": "-0.0691",
    "closest_station": "Old Street",
    "type": "Home",
    "image_url": "http://cloudfront.com/url",
    "arrival_time": "2017-12-05 19:30",
    "start_time": "2017-12-05 20:00",
    "end_time": "2017-12-05 22:30",
    "ticket_price": "10.00",
    "closest_station": "Peckham Rye",
    "event_url": "https://www.sofarsounds.com/cities/london/events/5"
  }
```

This endpoint retrieves a list of all upcoming appliable events for a particular city.

### HTTP Request

`GET http://www.sofarsounds.com/api/v1/cities/:city_id/events`

### URL paramaeters

Parameter | Description
--------- | -----------
city_id | The unique numerical id for a city

### Returned Parameters

Parameter | Description
--------- | -----------
events | A list of event structures. [Find out more about the event object](#event)

## Get users invited events

> The above command returns JSON structured like this:

```json
[
  {
    "id": 2,
    "location_name": "Shoreditch",
    "location_latitude": "-51.5285",
    "location_longitude": "-0.0847",
    "closest_station": "Old Street",
    "type": "Home",
    "image_url": "http://cloudfront.com/url",
    "arrival_time": "2017-12-01 19:30",
    "start_time": "2017-12-01 20:00",
    "end_time": "2017-12-01 22:30",
    "ticket_price": "10.00",
    "event_url": "https://www.sofarsounds.com/cities/london/events/2"
  },
  {
    "id": 5,
    "location_name": "Peckham",
    "location_latitude": "-51.4742",
    "location_longitude": "-0.0691",
    "closest_station": "Old Street",
    "type": "Home",
    "image_url": "http://cloudfront.com/url",
    "arrival_time": "2017-12-05 19:30",
    "start_time": "2017-12-05 20:00",
    "end_time": "2017-12-05 22:30",
    "ticket_price": "10.00",
    "closest_station": "Peckham Rye",
    "event_url": "https://www.sofarsounds.com/cities/london/events/5"
  }
```

Get a list of all upcoming events a user has been invited to where they are unconfirmed (not marked as can go/cant go)

###HTTP Request

`POST http://www.sofarsounds.com/api/v1/user/push_tokens`

### Returned Parameters

Parameter | Description
--------- | -----------
events | A list of event structures. [Find out more about the event object](#event)

## Mark as cant make it

```
{
  "success": "Attendee has been invited"
}
```

Mark a user as cant make it to an event

###HTTP Request

`POST http://www.sofarsounds.com/api/v1/events/:event_id/cant_make_it`

### URL paramaeters

Parameter | Description
--------- | -----------
reason | (optional) A reason the user is unable to attend

# Objects

## User

Parameter | Description
----------|------------
token | A token that can be used to authenticate on later requests
first_name |
last_name |
email |
birth_year | The year they selected as when they were born
mobile_notification_on | Wether they have opted into SMS notifications
mobile_country_code | The ISO 2 letter country code which can be used to find the international dialling code
mobile_number | There mobile number minus any additional country specific calling codes
gender |
push_notification_gig_offers |
push_notification_gig_updates |
push_notification_gig_suggestions |
email_setting_unlucky | Wether they have opted in to receive unlucky emails
email_setting_marketing | Wether they receive the monthly newsletter
email_setting_offers | Wether they receive any additional emails of offers
gig_preferences day_of_week | A hash of days of the week they would like to attend shows

## Event

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
event_url | The full url that leads to the event page
