
Inspiration : [Rest API - Best Practices - Design](https://www.youtube.com/watch?v=1Wl-rtew1_E)


## Naming Routes

 **Good** : Use nouns for naming, and HTTP Method for defining the action

> portal.com/orders/{order_id}

 **Bad** : Actions name is bad, HTTP Method name the action

> portal.com/get-order/{order_id}

<br>

## Passing Parameters

 **Good** : For parameters, use route parameters for items and queries for filter, sort, etc...

> portal.com/orders/{order_id}?filterby=id&limit=10 

**Bad** : Don't pass item selectors as queries

> portal.com/orders?order_id={order_id}&filterby=id&limit=10

<br>

## Depth of a API

**Good** : Simple and easier

> portal.com/customers/{customer_id}
> portal.com/orders?customer_id={customer_id}
> portal.com/items?order_id={order_id}

 **Bad** : Too deep, too dificult to mantain

> portal.com/customers/{customer_id}/orders/{order_id}/items/{item_id}

<br>

## Stateless

Every Restful API should be stateless, that means that any instance of the API should handle ANY request, don't needing to save a state or a session to response a client


