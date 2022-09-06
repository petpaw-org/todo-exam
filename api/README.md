# RESTFul API Specification

### get list data

```http
GET /api/todos
```
Query String

| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `archive` | `string` | false | true, false | not required |

### get specific list data by `:id`

```http
GET /api/todos/:id
```
Path Parameter
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `id` | `number` |  | any number | **required** |

### create new list

```http
POST /api/todos
```

Request Body
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `name` | `string` |  | any string | **required** |

### delete specific list by `:id`

```http
DELETE /api/todos/:id
```

Path Parameter
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `id` | `number` |  | any number | **required** |

Request Body
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `name` | `string` |  | any string | **required** |

### mark done specific list by `:id`

```http
POST /api/todos/:id/done
```

Path Parameter
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `id` | `number` |  | any number | **required** |


### get items data for each list

```http
GET /api/todos/:id/items
```

Path Parameter
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `id` | `number` |  | any number | the id of list is **required** |


Query String

| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `archive` | `string` | false | true, false | not required |

### create new list

```http
POST /api/todos/:id/items
```

Request Body
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `content` | `string` |  | any string | **required** |

### delete specific list item by `:id`

```http
DELETE /api/todos/:listId/items/:itemId
```

Path Parameter
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `listId` | `number` |  | any number | **required** |
| `itemId` | `number` |  | any number | **required** |

### archive specific list item by `:id`

```http
POST /api/todos/:listId/items/:itemId/archive
```

Path Parameter
| Parameter | Type | Default | Posible Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `listId` | `number` |  | any number | **required** |
| `itemId` | `number` |  | any number | **required** |

## Responses

```javascript
{
  "message" : string,
  "success" : bool,
  "data"    : []
}
```

The `message` attribute contains a message commonly used to indicate errors or, in the case of deleting a resource, success that the resource was properly deleted.

The `success` attribute describes if the transaction was successful or not.

The `data` attribute contains any other metadata associated with the response. This will be an escaped string containing JSON data.

## Status Codes

Gophish returns the following status codes in its API:

| Status Code | Description |
| :--- | :--- |
| 200 | `OK` |
| 201 | `CREATED` |
| 400 | `BAD REQUEST` |
| 404 | `NOT FOUND` |
| 500 | `INTERNAL SERVER ERROR` |

