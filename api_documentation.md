# PizzaTime API

This is an API that conveniently provides contact information, menus, open hours, and delivery times of nearby local pizza joints, based on your given postal code.  
PizzaTime API is able to handle queries for single orders as well as bulk orders, provided the right parameters.


## Endpoints
PizzaTime API has two simple GET requests: https://pizzatime.org/json will provide either **single order delivery information** or **bulk order delivery information** based on your given parameters.


## Parameters
For single orders:
  * **postCode** (string): Postal code, formatted without spaces. Not case-sensitive. Required.
  * **maxMins** (int): Maximum acceptible waiting time in minutes. Required.
  
For bulk orders:
  * **postCode** (string): Postal code, formatted without spaces. Not case-sensitive. Required.
  * **deliverDate** (string): Delivery date in YYYY-MM-DD. Required.

## Resources
The obtained JSON objects from the queries of PizzaTime API will be formatted the same, regardless of whether or not the query was for a single order or a bulk order.
```
"results":
    {
      "restaurantName": String. Name of restaurant.
      "eta": String. Estimated minutes to arrival.
      "contactInfo": String. Phone number details.
      "closingTime": String. Listed hours of the queried restaurant.
    }
```

## Sample requests
These are two sample requests for getting pizza joint information from our API from a given location.

Single order: 
```
https://pizzatime.org/json?postCode=r3t3m2&maxMins=20
```
Bulk order:
```
https://pizzatime.org/json?postCode=r3t3m2&deliverdate=2020-11-11
```

## Sample Responses

Results for single orders:

```
{
  "results":
    {
      "restaurantName":"Pizza Square"
      "eta":"25 mins"
      "contactInfo":"(204)-615-1991"
      "closingTime":"Till 11 PM on Weekdays and till Midnight on weekends"
    },
    {
      "restaurantName":"Bulldog Pizza"
      "eta":"30 mins"
      "contactInfo":"(204)-586-1234"
      "closingTime":"Till 2 AM on Weekdays and till 3 AM on weekends"
    }
}
```
Results for bulk orders:
```
{
  "results":
    {
      "restaurantName":'Pizzaland'
      "eta":"60-75 mins"
      "contactInfo":"(204)-336-3333"
      "closingTime":"Till Midnight on Weekdays and till 2 AM on weekends"
    }
}
```
