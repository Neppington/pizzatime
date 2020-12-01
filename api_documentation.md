# PizzaTime API

This is an API that conveniently provides contact information, menus, open hours, and delivery times of nearby local pizza joints, based on your given postal code information, among other additional parameters.


## Endpoint
We have a single endpoint: 
```GET /restaurants``` will access pizza joints according to your provided postal code, and can be further tuned with the use of the additional provided parameters.


## Parameters
  * **postCode** (string): Postal code, formatted without spaces. Not case-sensitive. Required.
  * **maxMins** (int): Maximum acceptable waiting time in minutes. Optional
  * **maxPrice** (int):  Maximum acceptable price for a standard pizza. Optional.
 

## Sample requests
These are a handful of sample requests that you can use to query your results and find pizza joints near you:
```
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"&maxMins=10
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"&maxPrice=20
  https://www.pizzatime.org/restaurants?postCode="R3T3M2"&maxPrice=20&maxMins=10
```

## Sample Responses
The response of our API contains the restaurant name, it's ETA for delivering pizza, it's contact info, as well as it's closing time, all of which is taken from the pizza joints' hosted information.

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
