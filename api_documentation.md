# PizzaTime API

This is an API that conveniently provides contact information, menus, open hours, and delivery times of nearby local pizza joints, based on your given postal code.  
PizzaTime API is able to handle queries for single orders as well as bulk orders, provided the right parameters.


## Endpoint
We have a single endpoint: ```GET /restaurants``` will access all pizza joints in Manitoba, and can be further tuned using the parameters.


## Parameters
  * **postCode** (string): Postal code, formatted without spaces. Not case-sensitive. Required.
  * **maxMins** (int): Maximum acceptable waiting time in minutes. Optional
  * **maxPrice** (int):  Maximum acceptable price for a standard pizza. Optional.
 

## Sample requests
These are two sample requests for getting pizza joint information from our API from a given location.
```
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"&maxMins=10
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"&maxPrice=20
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"&maxPrice=20&maxMins=10
  
```
## Sample Responses

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
