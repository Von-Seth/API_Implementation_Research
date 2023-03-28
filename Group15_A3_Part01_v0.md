# Winnipeg Transit API Documentation

## API Overview

* Winnipeg Transit API provides a method for people to get information of transit services. This API exposes data about buses and stops. This API has two filter queries and one identity queries that can be used to find and create a variety of different resources including the following:

1. Get a list of bus stops that a specific bus can arrive.
2. Get a list of buses that can arrive at the specific bus stop.
3. Get the next bus information that will arrive at the specific bus stop.

Data is returned as json format by default.


## API Endpoint Example
### This API exposes data of buses and stops.
1. If you would like to retrieve the information of a list of bus stops that a specific bus can arrive. To do this, you can have the URL： 
```https://api.transitinwinnipeg.com/buses/{bus_id}/stops``` 

2. Then if you would like to retrieve the information of a list of buses that can arrive at the specific bus stop. You can have the URL：   
```https://api.transitinwinnipeg.com/stops/{stop_id}/buses```.

3. Or say that you want to get the live information of the next bus that will arrive at the specific bus stop. In this case is by requesting from the endpoint ```https://api.transitinwinnipeg.com/stops/{stop_id}/nextbus```.

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



