# Error Handling
Error responses will have the appropriate HTTP status code (400, 404, 500, etc) set. There will be a ` message` field containing the error message. For validation errors, there will also be an `errors` field describing the invalid data.

> An example of a validation error:

```json
{
  "message": "The given data was invalid.",
  "errors": {
    "title": [
      "The title field is required."
    ],
    "tags": [
      "The tags field is required."
    ]
  }
}
```

# Pagination
This API is paginated. Endpoints which return lists of items will have three fields in the response:
- `data`, which is an array of the items
- `links`, which contains direct URLs to fetch the previous, next, first or last pages of the results
- `meta`, which contains meta information about the result set:
  - `current_page` (1-indexed)
  - `total`: total number of items in the full result set
  - `per page`: number of items per page
  - `path`: address of this page 
  - `from` and `to`, which detail the indexes in the results that this page contains. For instance, if there are 30 results, with 25 `per_page`, on the second page, `from` will be 26 and `to` will be 30.

You can request a specific page by using the `page` query parameter.

> Here's an example:

```json
{
  "data": [],
  "links": {
    "first": "http:\/\/127.0.0.1:8000\/api\/posts?page=1",
    "last": "http:\/\/127.0.0.1:8000\/api\/posts?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": null,
    "last_page": 1,
    "path": "http:\/\/127.0.0.1:8000\/api\/posts",
    "per_page": 25,
    "to": null,
    "total": 0
  }
}
```