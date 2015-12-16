---
title: API Reference

language_tabs:
  - javascript

toc_footers:
  - <a href='https://github.paypal.com/chemical/chemical/'>Get Source</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to Chemical. Chemical is a UI framework that lets you take as little, or as much as you would like.

Chemical provides CSS if all you want is some styles to get you moving. We also provide Stylus files, to preprocess with your project.

For those who want more control, we provide isomorphic vanilla javascript objects, that help you draw server side views, and quickly paint those views to the screen.

Chemical providers a number of UI widgets, drawing components, a client side router, and ajax. There is no data binding here, or cruft. Emphasis is on building ultra fast and beautiful applications.

# Base

> Create a Base object

```javascript
var Base = require('chemical/base');


var base = new Base(function (data){
    return '<span>' + data.foo + '</span>'
},{
    foo: 'bar'
});

base.renderInto(document.body);
```

Chemical's main theme, is to stay away from getting in the way of your code, and the browser. We want you to make ultra fast applications, and understand what you are doing.

In Chemical, `Base` is a constructor, that holds some information and has some helper functions about what you want to render.

We provide `Base`, so you can start drawing to the DOM and rendering in NodeJS out of the box.

`Base` accepts two arguments. A `templating Function` and some `data`.

You can provide any kind of template function, Chemical recommends you use `Underscore` to `JavaScript Templates`, or compiling your `Dust` templates, if you want to make your own widgets using clean HTML seperation.

<aside class="notice">
    You can use base, to create your own reusable widgets!
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

