---
title: LunchBox - API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - javascript

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introducción

Bienvenido a la API de LunchBox, puedes usar esta API para acceder a nuestros endpoints,
los cuales te pueden dar información sobre los restaurantes Universitarios y sus almuerzos que se encuentran en nuestra base de datos.

Puedes encontrar en el area negra el código y puedes cambiar según el lenguaje de programación que estés utilizando.



<!-- # Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://lunchbox.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside> -->

# Almuerzos

## Get All Kittens

```ruby
require 'lunchbox'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.dishes.get
```

```shell
curl "http://lunchbox.com/api/dishes"
  -H "Authorization: meowmeowmeow"
```

```javascript
const lunchbox = require('lunchbox');

let api = kittn.authorize('meowmeowmeow');
let dishes = api.dishes.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Bandeja Paisa",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all dishes.

### HTTP Request

`GET http://lunchbox.com/api/dishes`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include dishes that have already been adopted.



## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.dishes.get(2)
```

```shell
curl "http://lunchbox.com/api/dishes/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.dishes.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

### HTTP Request

`GET http://lunchbox.com/dishes/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.dishes.delete(2)
```

```shell
curl "http://lunchbox.com/api/dishes/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.dishes.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://lunchbox.com/dishes/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
