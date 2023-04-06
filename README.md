# Comp 3040 Assignment 3 (# Group 15).
# Manitoba Transit API Documentation

## API Overview

* Manitoba Transit API provides a method for people to get information of transit services. This API is designed to provide real-time schedules for busses at a stop and bus routes. Our API is designed to be fast, reliable and easy to use. The API has two filter queries and one identity query that can be used to find and create resources such as bus routes, stop info and bus schedules.
  
## Resources

1. Bus routes: Gets a list of bus stops that the requested bus can stop at and provides info such as route name, and list of stops on route.
   ```
    {
        "route":[
            "U of M", //string
            "defoe"
        ]
    }
   ```
2. Stop info: Gets a list of buses that can arrive at the requested bus stop.
    ```
    {
        "buses":[
            60, //int64 integer
            74
        ]
    }
    ```
3. Bus schedule: Get the next bus information that will arrive at the requested bus stop.
    ```
    {
        busID: 60, //integer
        time: 17:00 //string
    }
    ```
Data requested is returned as json format by default.


## API Endpoint Example

### This API exposes data of buses and stops.
1. To request a list of bus stops that a specific bus stops at, you can do so with the URL below： 
```https://api.transitinmanitoba.com/buses/{bus_id}/stops``` 

2. To request a list of buses that can arrive at a specific bus stop, use the URL below：   
```https://api.transitinmanitoba.com/stops/{stop_id}/buses```.

1. To request a real-time update of the next bus that will arrive at the specific bus stop, use the URL below: ```https://api.transitinmanitoba.com/stops/{stop_id}/nextbus```.

## Query parameters
| Name |Type| Description |
| --- | ---|----------- |
| bus_id| integer| An unique identifier of a bus. By passing this parameter, you can fetch the information of a specific bus.
| stop_id | integer| An unique identifier of a stop.. By passing this parameter, you can fetch the information of a specific stop.

## Response fields
| Name |Type| Description |
| --- | ---|----------- |
| buses| array | A list of buses. 
| stops | array |  A list of bus stops
| nextbus | object | The content of a bus

## Sample request and response

```
1. https://api.transitinmanitoba.com/buses/17/stops


```


