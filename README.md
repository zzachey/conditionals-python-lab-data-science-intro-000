
# Conditionals in Python Lab

### Introduction

In our earlier lab on functional arguments, we found ways to work with Yelp to find and compare restaurants. In this lesson, we'll add more complex methods now that we know about conditionals.

### Again, our two restuarants in Albuquerque

Let's take another look at our data for a single restaurant.  Once again, we have data regarding the Fork and Fig restaurant.


```python
fork_fig = {'categories': [{'alias': 'burgers', 'title': 'Burgers'},
  {'alias': 'sandwiches', 'title': 'Sandwiches'},
  {'alias': 'salad', 'title': 'Salad'}],
 'coordinates': {'latitude': 35.10871, 'longitude': -106.56739},
 'display_phone': '(505) 881-5293',
 'distance': 3571.724649307866,
 'id': 'fork-and-fig-albuquerque',
 'image_url': 'https://s3-media1.fl.yelpcdn.com/bphoto/_-DpXKfS3jv6DyA47g6Fxg/o.jpg',
 'is_closed': False,
 'location': {'address1': '6904 Menaul Blvd NE',
  'address2': 'Ste C',
  'address3': '',
  'city': 'Albuquerque',
  'country': 'US',
  'display_address': ['6904 Menaul Blvd NE', 'Ste C', 'Albuquerque, NM 87110'],
  'state': 'NM',
  'zip_code': '87110'},
 'name': 'Fork & Fig',
 'phone': '+15058815293',
 'price': '$$',
 'rating': 4.5,
 'review_count': 604,
 'transactions': [],
 'url': 'https://www.yelp.com/biz/fork-and-fig-albuquerque?adjust_creative=SYc8R4Gowqru5h4SBKZXsQ&utm_campaign=yelp_api_v3&utm_medium=api_v3_business_search&utm_source=SYc8R4Gowqru5h4SBKZXsQ'}
```

And here is the data representing Frontier Restaurant.


```python
frontier_restaurant = {'categories': [{'alias': 'mexican', 'title': 'Mexican'},
  {'alias': 'diners', 'title': 'Diners'},
  {'alias': 'tradamerican', 'title': 'American (Traditional)'}],
 'coordinates': {'latitude': 35.0808088832532, 'longitude': -106.619402244687},
 'display_phone': '(505) 266-0550',
 'distance': 4033.6583235266075,
 'id': 'frontier-restaurant-albuquerque-2',
 'image_url': 'https://s3-media4.fl.yelpcdn.com/bphoto/M9L2z6-G0NobuDJ6YTh6VA/o.jpg',
 'is_closed': True,
 'location': {'address1': '2400 Central Ave SE',
  'address2': '',
  'address3': '',
  'city': 'Albuquerque',
  'country': 'US',
  'display_address': ['2400 Central Ave SE', 'Albuquerque, NM 87106'],
  'state': 'NM',
  'zip_code': '87106'},
 'name': 'Frontier Restaurant',
 'phone': '+15052660550',
 'price': '$',
 'rating': 4.0,
 'review_count': 1369,
 'transactions': [],
 'url': 'https://www.yelp.com/biz/frontier-restaurant-albuquerque-2?adjust_creative=SYc8R4Gowqru5h4SBKZXsQ&utm_campaign=yelp_api_v3&utm_medium=api_v3_business_search&utm_source=SYc8R4Gowqru5h4SBKZXsQ'}
```

And once again, the attributes of the dictionaries above look like the following.


```python
fork_fig.keys()
```




    dict_keys(['categories', 'coordinates', 'display_phone', 'distance', 'id', 'image_url', 'is_closed', 'location', 'name', 'phone', 'price', 'rating', 'review_count', 'transactions', 'url'])



### Writing functions with conditionals

Let's write a function called `better_restaurant` that provided two restaurants, returns the restaurant with the better rating.  The first argument is `restaurant` and the second argument is `alternative`.  


```python
def better_restaurant(restaurant, alternative):
    pass
```


```python
print(better_restaurant(frontier_restaurant, fork_fig)['name']) # 'Fork & Fig'
print(better_restaurant(fork_fig, frontier_restaurant)['name']) # 'Fork & Fig'
```

Let's write a function called `cheaper_restaurant` that returns the restaurant with the lower price, that is the restaurant that has fewer `'$'` signs.  The first argument should be named `restaurant` and the second argument should be named `alternative`.


```python
def cheaper_restaurant(restaurant, alternative):
    pass
```


```python
print(cheaper_restaurant(fork_fig, frontier_restaurant)['name']) # 'Frontier Restaurant'
print(cheaper_restaurant(frontier_restaurant, fork_fig)['name']) # 'Frontier Restaurant'
```

### Conditionals and Loops

Let's continue our work of conditionals by seeing how they can be combined with loops. Let's write a function called `open_restaurants` that takes in a list of restaurants as an argument and returns a list of only the restaurants that are not closed.


```python
fork_fig['is_closed'] # False
```


```python
frontier_restaurant['is_closed'] # True
```


```python
restaurants = [fork_fig, frontier_restaurant]
```


```python
def open_restaurants(restaurants):
    pass
```


```python
len(open_restaurants(restaurants)) # 1
```


```python
open_restaurants(restaurants)[0]['name'] # 'Fork & Fig'
```

### Summary

Great! In this lab we saw how to use functions with multiple arguments and conditionals to return the restaurant we want based on the questions we are trying to answer. We also saw how to use conditionals to select only certain elements of an array based on a condition we want our elements to meet.
