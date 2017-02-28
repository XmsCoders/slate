---
title: API Reference

language_tabs:
  - shell
  - java
  - c#
  - php
  - javascript

#toc_footers:
#  - <a href='#'>Sign Up for a Developer Key</a>
#  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Contacts

## Get All Contacts

```shell
  curl -v -X GET http://api.multimediabs.com/v1/groups/4633a4fe-5544-4ac9-95ac-9e1ffc4751bc/contacts \
      -H "Content-Type:application/json" \
      -H "Authorization: Bearer [Access-Token]"
```

> The above command returns JSON structured like this:

```json
{
	"content":[
		{
			"id":"f12edd46-96b8-41d9-baa7-58f42daa9301",
			"name":"Boyer",
			"first-name":"Mael"
		},
		{
			"id":"54032d6f-19cd-4049-8cfe-bd80a563c911",
			"name":"Le gall",
			"first-name":"Ethan"
		},
		...
		{
			"id":"372c1ede-03d5-41d4-bd2c-0471a3c371be",
			"name":"Morel",
			"first-name":"Alexis"
		}
	],
	"last":false,
	"first":true,
	"totalPages":3,
	"totalElements":25,
	"numberOfElements":25,
	"size":10,
	"number":0
}
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

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
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

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

