# Winnipeg Transit API Documentation

## API Overview

* Winnipeg Transit API provides a method for people to get information of transit services. This API is designed to provide real-time schedules for busses at a stop and bus routes. Our API is designed to be fast, reliable and easy to use. The API has two filter queries and one identity query that can be used to find and create a variety of different resources including the following:

1. Bus routes: Get a list of bus stops that the requested bus can stop at .
2. Stop info: Get a list of buses that can arrive at the requested bus stop.
3. Bus schedule: Get the next bus information that will arrive at the requested bus stop.

Data requested is returned as json format by default.


## API Endpoint Example

### This API exposes data of buses and stops.
1. To request a list of bus stops that a specific bus stops at, you can do so with the URL below： 
```https://api.transitinwinnipeg.com/buses/{bus_id}/stops``` 

2. To request a list of buses that can arrive at a specific bus stop, use the URL below：   
```https://api.transitinwinnipeg.com/stops/{stop_id}/buses```.

1. To request a real-time update of the next bus that will arrive at the specific bus stop, use the URL below: ```https://api.transitinwinnipeg.com/stops/{stop_id}/nextbus```.

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

## Example of response

```
1. buses
[
    {
        "bus_id": 17,
        "stops":[
            {
                "stop_id":88,
                "address":"Westbound Dafoe at U of M Station"
            },{
                "stop_id":78,
                "address":"North bound Polo Park Terminal at Polo Park"
            }
        ]
    }, {
        "bus_id": 60,
        "stops":[
            {
                "stop_id":18,
                "address":"Westbound Chancellor Matheson at Pembina"
            },{
                "stop_id":28,
                "address":"Northbound Pembina at Dartmouth"
            }
        ]
    }
]

```


