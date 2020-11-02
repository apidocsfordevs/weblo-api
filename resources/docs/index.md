---
title: Weblo API Documentation

language_tabs:
- bash
- javascript

includes:
- "./prepend.md"
- "./authentication.md"
- "./groups/*"
- "./errors.md"
- "./append.md"

logo: 

toc_footers:
- <a href="./collection.json">View Postman collection</a>
- <a href="./openapi.yaml">View OpenAPI (Swagger) spec</a>
- <a href='http://github.com/knuckleswtf/scribe'>Documentation powered by Scribe ✍</a>

---

# Introduction



The Weblo API allows you to manage and view info about your Weblo blog as well as retrieve some public information about Weblo. The APi is largely REST-based. Most endpoints accept JSON input and return JSON responses. 

<aside class="warning">You must always set the `Accept` header to `application/json`, otherwise some requests may return invalid responses.</aside>

To use the API, you'll need to sign up for Weblo. You can do this on our homepage, or via the `POST /register` endpoint. Then retrieve a new token via `POST /login`.

For any enquiries, send us an email: api@weblo.blog.

<script src="https://cdn.jsdelivr.net/npm/lodash@4.17.10/lodash.min.js"></script>
<script>
    var baseUrl = "http://localhost:8000";
</script>
<script src="js/tryitout.js"></script>

> Base URL

```yaml
http://localhost:8000
```