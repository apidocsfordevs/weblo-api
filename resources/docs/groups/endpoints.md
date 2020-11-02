# Endpoints


## Create a Weblo account.




> Example request:

```bash
curl -X POST \
    "http://localhost:8000/api/register" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/register"
);

let headers = {
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "POST",
    headers,
}).then(response => response.json());
```


> Example response (422):

```json
{
    "message": "The given data was invalid.",
    "errors": {
        "name": [
            "The name field is required."
        ],
        "email": [
            "The email field is required."
        ],
        "password": [
            "The password field is required."
        ]
    }
}
```
<div id="execution-results-POSTapi-register" hidden>
    <blockquote>Received response<span id="execution-response-status-POSTapi-register"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-POSTapi-register"></code></pre>
</div>
<div id="execution-error-POSTapi-register" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-POSTapi-register"></code></pre>
</div>
<form id="form-POSTapi-register" data-method="POST" data-path="api/register" data-authed="0" data-hasfiles="0" data-headers='{"Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('POSTapi-register', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-POSTapi-register" onclick="tryItOut('POSTapi-register');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-POSTapi-register" onclick="cancelTryOut('POSTapi-register');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-POSTapi-register" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-black">POST</small>
 <b><code>api/register</code></b>
</p>
</form>


## Generate an access token.




> Example request:

```bash
curl -X POST \
    "http://localhost:8000/api/login" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/login"
);

let headers = {
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "POST",
    headers,
}).then(response => response.json());
```


> Example response (401):

```json
{
    "error": "Unauthorized"
}
```
<div id="execution-results-POSTapi-login" hidden>
    <blockquote>Received response<span id="execution-response-status-POSTapi-login"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-POSTapi-login"></code></pre>
</div>
<div id="execution-error-POSTapi-login" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-POSTapi-login"></code></pre>
</div>
<form id="form-POSTapi-login" data-method="POST" data-path="api/login" data-authed="0" data-hasfiles="0" data-headers='{"Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('POSTapi-login', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-POSTapi-login" onclick="tryItOut('POSTapi-login');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-POSTapi-login" onclick="cancelTryOut('POSTapi-login');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-POSTapi-login" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-black">POST</small>
 <b><code>api/login</code></b>
</p>
</form>


## Display a list of tags.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X GET \
    -G "http://localhost:8000/api/tags" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/tags"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "GET",
    headers,
}).then(response => response.json());
```


> Example response (200):

```json
{
    "data": [
        {
            "id": 1,
            "name": "things",
            "slug": "things",
            "description": "About things",
            "created_at": "2020-11-02 18:23:39",
            "updated_at": "2020-11-02 18:23:39",
            "posts": [
                {
                    "id": 3,
                    "user_id": 1,
                    "title": "How My Night Came",
                    "slug": "how-my-night-came",
                    "content": "Another Thing",
                    "status": 0,
                    "created_at": "2020-11-02 18:25:03",
                    "updated_at": "2020-11-02 18:25:03",
                    "pivot": {
                        "tag_id": 1,
                        "post_id": 3
                    }
                },
                {
                    "id": 4,
                    "user_id": 1,
                    "title": "How My Day Did Go",
                    "slug": "how-my-day-did-go",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:33:13",
                    "updated_at": "2020-11-02 18:33:13",
                    "pivot": {
                        "tag_id": 1,
                        "post_id": 4
                    }
                }
            ]
        },
        {
            "id": 2,
            "name": "more things",
            "slug": "more-things",
            "description": "About even more things",
            "created_at": "2020-11-02 18:23:53",
            "updated_at": "2020-11-02 18:23:53",
            "posts": [
                {
                    "id": 1,
                    "user_id": 1,
                    "title": "How My Day Went",
                    "slug": "how-my-day-went",
                    "content": "Something",
                    "status": 0,
                    "created_at": "2020-11-02 18:24:27",
                    "updated_at": "2020-11-02 18:24:27",
                    "pivot": {
                        "tag_id": 2,
                        "post_id": 1
                    }
                },
                {
                    "id": 2,
                    "user_id": 1,
                    "title": "How My Night Went",
                    "slug": "how-my-night-went",
                    "content": "Another Thing",
                    "status": 0,
                    "created_at": "2020-11-02 18:24:52",
                    "updated_at": "2020-11-02 18:24:52",
                    "pivot": {
                        "tag_id": 2,
                        "post_id": 2
                    }
                },
                {
                    "id": 5,
                    "user_id": 1,
                    "title": "How I'm doing",
                    "slug": "how-im-doing",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:33:27",
                    "updated_at": "2020-11-02 18:33:27",
                    "pivot": {
                        "tag_id": 2,
                        "post_id": 5
                    }
                },
                {
                    "id": 6,
                    "user_id": 1,
                    "title": "How I Did It",
                    "slug": "how-i-did-it",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:34:19",
                    "updated_at": "2020-11-02 18:34:19",
                    "pivot": {
                        "tag_id": 2,
                        "post_id": 6
                    }
                },
                {
                    "id": 7,
                    "user_id": 1,
                    "title": "How I Did It Again",
                    "slug": "how-i-did-it-again",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:39:22",
                    "updated_at": "2020-11-02 18:39:22",
                    "pivot": {
                        "tag_id": 2,
                        "post_id": 7
                    }
                }
            ]
        },
        {
            "id": 3,
            "name": "more more things",
            "slug": "more-more-things",
            "description": "About some more things",
            "created_at": "2020-11-02 18:24:01",
            "updated_at": "2020-11-02 18:24:01",
            "posts": [
                {
                    "id": 4,
                    "user_id": 1,
                    "title": "How My Day Did Go",
                    "slug": "how-my-day-did-go",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:33:13",
                    "updated_at": "2020-11-02 18:33:13",
                    "pivot": {
                        "tag_id": 3,
                        "post_id": 4
                    }
                },
                {
                    "id": 5,
                    "user_id": 1,
                    "title": "How I'm doing",
                    "slug": "how-im-doing",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:33:27",
                    "updated_at": "2020-11-02 18:33:27",
                    "pivot": {
                        "tag_id": 3,
                        "post_id": 5
                    }
                },
                {
                    "id": 6,
                    "user_id": 1,
                    "title": "How I Did It",
                    "slug": "how-i-did-it",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:34:19",
                    "updated_at": "2020-11-02 18:34:19",
                    "pivot": {
                        "tag_id": 3,
                        "post_id": 6
                    }
                },
                {
                    "id": 7,
                    "user_id": 1,
                    "title": "How I Did It Again",
                    "slug": "how-i-did-it-again",
                    "content": "No big deal",
                    "status": 1,
                    "created_at": "2020-11-02 18:39:22",
                    "updated_at": "2020-11-02 18:39:22",
                    "pivot": {
                        "tag_id": 3,
                        "post_id": 7
                    }
                }
            ]
        },
        {
            "id": 4,
            "name": "dumb things",
            "slug": "dumb-things",
            "description": "DUMB things",
            "created_at": "2020-11-02 18:24:17",
            "updated_at": "2020-11-02 18:24:17",
            "posts": [
                {
                    "id": 1,
                    "user_id": 1,
                    "title": "How My Day Went",
                    "slug": "how-my-day-went",
                    "content": "Something",
                    "status": 0,
                    "created_at": "2020-11-02 18:24:27",
                    "updated_at": "2020-11-02 18:24:27",
                    "pivot": {
                        "tag_id": 4,
                        "post_id": 1
                    }
                },
                {
                    "id": 2,
                    "user_id": 1,
                    "title": "How My Night Went",
                    "slug": "how-my-night-went",
                    "content": "Another Thing",
                    "status": 0,
                    "created_at": "2020-11-02 18:24:52",
                    "updated_at": "2020-11-02 18:24:52",
                    "pivot": {
                        "tag_id": 4,
                        "post_id": 2
                    }
                },
                {
                    "id": 3,
                    "user_id": 1,
                    "title": "How My Night Came",
                    "slug": "how-my-night-came",
                    "content": "Another Thing",
                    "status": 0,
                    "created_at": "2020-11-02 18:25:03",
                    "updated_at": "2020-11-02 18:25:03",
                    "pivot": {
                        "tag_id": 4,
                        "post_id": 3
                    }
                }
            ]
        }
    ],
    "links": {
        "first": "http:\/\/localhost\/api\/tags?page=1",
        "last": "http:\/\/localhost\/api\/tags?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http:\/\/localhost\/api\/tags",
        "per_page": 25,
        "to": 4,
        "total": 4
    }
}
```
<div id="execution-results-GETapi-tags" hidden>
    <blockquote>Received response<span id="execution-response-status-GETapi-tags"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-GETapi-tags"></code></pre>
</div>
<div id="execution-error-GETapi-tags" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-GETapi-tags"></code></pre>
</div>
<form id="form-GETapi-tags" data-method="GET" data-path="api/tags" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('GETapi-tags', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-GETapi-tags" onclick="tryItOut('GETapi-tags');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-GETapi-tags" onclick="cancelTryOut('GETapi-tags');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-GETapi-tags" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-green">GET</small>
 <b><code>api/tags</code></b>
</p>
<p>
<label id="auth-GETapi-tags" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="GETapi-tags" data-component="header"></label>
</p>
</form>


## Store a newly created tag in the database.

<small class="badge badge-darkred">requires authentication</small>

No two tags can have the same name.

> Example request:

```bash
curl -X POST \
    "http://localhost:8000/api/tags" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/tags"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "POST",
    headers,
}).then(response => response.json());
```


> Example response (422):

```json
{
    "message": "The given data was invalid.",
    "errors": {
        "name": [
            "The name field is required."
        ],
        "description": [
            "The description field is required."
        ]
    }
}
```
<div id="execution-results-POSTapi-tags" hidden>
    <blockquote>Received response<span id="execution-response-status-POSTapi-tags"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-POSTapi-tags"></code></pre>
</div>
<div id="execution-error-POSTapi-tags" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-POSTapi-tags"></code></pre>
</div>
<form id="form-POSTapi-tags" data-method="POST" data-path="api/tags" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('POSTapi-tags', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-POSTapi-tags" onclick="tryItOut('POSTapi-tags');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-POSTapi-tags" onclick="cancelTryOut('POSTapi-tags');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-POSTapi-tags" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-black">POST</small>
 <b><code>api/tags</code></b>
</p>
<p>
<label id="auth-POSTapi-tags" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="POSTapi-tags" data-component="header"></label>
</p>
</form>


## Display the specified tag.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X GET \
    -G "http://localhost:8000/api/tags/enim" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/tags/enim"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "GET",
    headers,
}).then(response => response.json());
```


> Example response (404):

```json
{
    "error": "Resource not found"
}
```
<div id="execution-results-GETapi-tags--tag-" hidden>
    <blockquote>Received response<span id="execution-response-status-GETapi-tags--tag-"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-GETapi-tags--tag-"></code></pre>
</div>
<div id="execution-error-GETapi-tags--tag-" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-GETapi-tags--tag-"></code></pre>
</div>
<form id="form-GETapi-tags--tag-" data-method="GET" data-path="api/tags/{tag}" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('GETapi-tags--tag-', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-GETapi-tags--tag-" onclick="tryItOut('GETapi-tags--tag-');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-GETapi-tags--tag-" onclick="cancelTryOut('GETapi-tags--tag-');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-GETapi-tags--tag-" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-green">GET</small>
 <b><code>api/tags/{tag}</code></b>
</p>
<p>
<label id="auth-GETapi-tags--tag-" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="GETapi-tags--tag-" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>tag</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="tag" data-endpoint="GETapi-tags--tag-" data-component="url" required  hidden>
<br>
</p>
</form>


## Update the specified tag in the database.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X PUT \
    "http://localhost:8000/api/tags/molestiae" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/tags/molestiae"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "PUT",
    headers,
}).then(response => response.json());
```


<div id="execution-results-PUTapi-tags--tag-" hidden>
    <blockquote>Received response<span id="execution-response-status-PUTapi-tags--tag-"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-PUTapi-tags--tag-"></code></pre>
</div>
<div id="execution-error-PUTapi-tags--tag-" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-PUTapi-tags--tag-"></code></pre>
</div>
<form id="form-PUTapi-tags--tag-" data-method="PUT" data-path="api/tags/{tag}" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('PUTapi-tags--tag-', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-PUTapi-tags--tag-" onclick="tryItOut('PUTapi-tags--tag-');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-PUTapi-tags--tag-" onclick="cancelTryOut('PUTapi-tags--tag-');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-PUTapi-tags--tag-" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-darkblue">PUT</small>
 <b><code>api/tags/{tag}</code></b>
</p>
<p>
<small class="badge badge-purple">PATCH</small>
 <b><code>api/tags/{tag}</code></b>
</p>
<p>
<label id="auth-PUTapi-tags--tag-" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="PUTapi-tags--tag-" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>tag</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="tag" data-endpoint="PUTapi-tags--tag-" data-component="url" required  hidden>
<br>
</p>
</form>


## Remove the specified tag from the database.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X DELETE \
    "http://localhost:8000/api/tags/tempore" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/tags/tempore"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "DELETE",
    headers,
}).then(response => response.json());
```


<div id="execution-results-DELETEapi-tags--tag-" hidden>
    <blockquote>Received response<span id="execution-response-status-DELETEapi-tags--tag-"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-DELETEapi-tags--tag-"></code></pre>
</div>
<div id="execution-error-DELETEapi-tags--tag-" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-DELETEapi-tags--tag-"></code></pre>
</div>
<form id="form-DELETEapi-tags--tag-" data-method="DELETE" data-path="api/tags/{tag}" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('DELETEapi-tags--tag-', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-DELETEapi-tags--tag-" onclick="tryItOut('DELETEapi-tags--tag-');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-DELETEapi-tags--tag-" onclick="cancelTryOut('DELETEapi-tags--tag-');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-DELETEapi-tags--tag-" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-red">DELETE</small>
 <b><code>api/tags/{tag}</code></b>
</p>
<p>
<label id="auth-DELETEapi-tags--tag-" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="DELETEapi-tags--tag-" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>tag</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="tag" data-endpoint="DELETEapi-tags--tag-" data-component="url" required  hidden>
<br>
</p>
</form>


## Display a list of posts.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X GET \
    -G "http://localhost:8000/api/posts?page=15" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts"
);

let params = {
    "page": "15",
};
Object.keys(params)
    .forEach(key => url.searchParams.append(key, params[key]));

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "GET",
    headers,
}).then(response => response.json());
```


> Example response (200):

```json
{
    "data": [],
    "links": {
        "first": "http:\/\/localhost\/api\/posts?page=1",
        "last": "http:\/\/localhost\/api\/posts?page=1",
        "prev": "http:\/\/localhost\/api\/posts?page=14",
        "next": null
    },
    "meta": {
        "current_page": 15,
        "from": null,
        "last_page": 1,
        "path": "http:\/\/localhost\/api\/posts",
        "per_page": 25,
        "to": null,
        "total": 7
    }
}
```
<div id="execution-results-GETapi-posts" hidden>
    <blockquote>Received response<span id="execution-response-status-GETapi-posts"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-GETapi-posts"></code></pre>
</div>
<div id="execution-error-GETapi-posts" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-GETapi-posts"></code></pre>
</div>
<form id="form-GETapi-posts" data-method="GET" data-path="api/posts" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('GETapi-posts', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-GETapi-posts" onclick="tryItOut('GETapi-posts');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-GETapi-posts" onclick="cancelTryOut('GETapi-posts');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-GETapi-posts" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-green">GET</small>
 <b><code>api/posts</code></b>
</p>
<p>
<label id="auth-GETapi-posts" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="GETapi-posts" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>Query Parameters</b></h4>
<p>
<b><code>page</code></b>&nbsp;&nbsp;<small>integer</small>     <i>optional</i> &nbsp;
<input type="number" name="page" data-endpoint="GETapi-posts" data-component="query"  hidden>
<br>
The page number of the result set to return.</p>
</form>


## Create a really good new post

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X POST \
    "http://localhost:8000/api/posts" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json" \
    -d '{"title":"repudiandae","content":"et","status":false,"tags":[16,19]}'

```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};

let body = {
    "title": "repudiandae",
    "content": "et",
    "status": false,
    "tags": [
        16,
        19
    ]
}

fetch(url, {
    method: "POST",
    headers,
    body: JSON.stringify(body),
}).then(response => response.json());
```


> Example response (201):

```json
{
    "data": {
        "id": 9,
        "title": "repudiandae",
        "slug": "repudiandae",
        "content": "et",
        "status": false,
        "created_at": "2020-11-02 18:49:21",
        "updated_at": "2020-11-02 18:49:21",
        "user": {
            "id": 1,
            "name": "Twix",
            "email": "sa@ax.com",
            "email_verified_at": null,
            "created_at": "2020-11-02 18:20:36",
            "updated_at": "2020-11-02 18:20:36"
        },
        "tags": [],
        "comments": []
    }
}
```
<div id="execution-results-POSTapi-posts" hidden>
    <blockquote>Received response<span id="execution-response-status-POSTapi-posts"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-POSTapi-posts"></code></pre>
</div>
<div id="execution-error-POSTapi-posts" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-POSTapi-posts"></code></pre>
</div>
<form id="form-POSTapi-posts" data-method="POST" data-path="api/posts" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('POSTapi-posts', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-POSTapi-posts" onclick="tryItOut('POSTapi-posts');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-POSTapi-posts" onclick="cancelTryOut('POSTapi-posts');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-POSTapi-posts" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-black">POST</small>
 <b><code>api/posts</code></b>
</p>
<p>
<label id="auth-POSTapi-posts" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="POSTapi-posts" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>Body Parameters</b></h4>
<p>
<b><code>title</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="title" data-endpoint="POSTapi-posts" data-component="body" required  hidden>
<br>
The title of the post</p>
<p>
<b><code>content</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="content" data-endpoint="POSTapi-posts" data-component="body" required  hidden>
<br>
</p>
<p>
<b><code>status</code></b>&nbsp;&nbsp;<small>boolean</small>     <i>optional</i> &nbsp;
<label data-endpoint="POSTapi-posts" hidden><input type="radio" name="status" value="true" data-endpoint="POSTapi-posts" data-component="body" ><code>true</code></label>
<label data-endpoint="POSTapi-posts" hidden><input type="radio" name="status" value="false" data-endpoint="POSTapi-posts" data-component="body" ><code>false</code></label>
<br>
Set to true to publish.</p>
<p>
<b><code>tags</code></b>&nbsp;&nbsp;<small>integer[]</small>     <i>optional</i> &nbsp;
<input type="number" name="tags.0" data-endpoint="POSTapi-posts" data-component="body"  hidden>
<input type="number" name="tags.1" data-endpoint="POSTapi-posts" data-component="body" hidden>
<br>
List of tag IDs to attach to the post.</p>

</form>


## Display the specified post.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X GET \
    -G "http://localhost:8000/api/posts/necessitatibus" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts/necessitatibus"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "GET",
    headers,
}).then(response => response.json());
```


> Example response (404):

```json
{
    "error": "Resource not found"
}
```
<div id="execution-results-GETapi-posts--post-" hidden>
    <blockquote>Received response<span id="execution-response-status-GETapi-posts--post-"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-GETapi-posts--post-"></code></pre>
</div>
<div id="execution-error-GETapi-posts--post-" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-GETapi-posts--post-"></code></pre>
</div>
<form id="form-GETapi-posts--post-" data-method="GET" data-path="api/posts/{post}" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('GETapi-posts--post-', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-GETapi-posts--post-" onclick="tryItOut('GETapi-posts--post-');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-GETapi-posts--post-" onclick="cancelTryOut('GETapi-posts--post-');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-GETapi-posts--post-" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-green">GET</small>
 <b><code>api/posts/{post}</code></b>
</p>
<p>
<label id="auth-GETapi-posts--post-" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="GETapi-posts--post-" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>post</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="post" data-endpoint="GETapi-posts--post-" data-component="url" required  hidden>
<br>
</p>
</form>


## Update the specified post in the database.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X PUT \
    "http://localhost:8000/api/posts/distinctio" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts/distinctio"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "PUT",
    headers,
}).then(response => response.json());
```


<div id="execution-results-PUTapi-posts--post-" hidden>
    <blockquote>Received response<span id="execution-response-status-PUTapi-posts--post-"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-PUTapi-posts--post-"></code></pre>
</div>
<div id="execution-error-PUTapi-posts--post-" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-PUTapi-posts--post-"></code></pre>
</div>
<form id="form-PUTapi-posts--post-" data-method="PUT" data-path="api/posts/{post}" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('PUTapi-posts--post-', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-PUTapi-posts--post-" onclick="tryItOut('PUTapi-posts--post-');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-PUTapi-posts--post-" onclick="cancelTryOut('PUTapi-posts--post-');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-PUTapi-posts--post-" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-darkblue">PUT</small>
 <b><code>api/posts/{post}</code></b>
</p>
<p>
<small class="badge badge-purple">PATCH</small>
 <b><code>api/posts/{post}</code></b>
</p>
<p>
<label id="auth-PUTapi-posts--post-" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="PUTapi-posts--post-" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>post</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="post" data-endpoint="PUTapi-posts--post-" data-component="url" required  hidden>
<br>
</p>
</form>


## Remove the specified post from the database.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X DELETE \
    "http://localhost:8000/api/posts/non" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts/non"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "DELETE",
    headers,
}).then(response => response.json());
```


<div id="execution-results-DELETEapi-posts--post-" hidden>
    <blockquote>Received response<span id="execution-response-status-DELETEapi-posts--post-"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-DELETEapi-posts--post-"></code></pre>
</div>
<div id="execution-error-DELETEapi-posts--post-" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-DELETEapi-posts--post-"></code></pre>
</div>
<form id="form-DELETEapi-posts--post-" data-method="DELETE" data-path="api/posts/{post}" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('DELETEapi-posts--post-', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-DELETEapi-posts--post-" onclick="tryItOut('DELETEapi-posts--post-');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-DELETEapi-posts--post-" onclick="cancelTryOut('DELETEapi-posts--post-');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-DELETEapi-posts--post-" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-red">DELETE</small>
 <b><code>api/posts/{post}</code></b>
</p>
<p>
<label id="auth-DELETEapi-posts--post-" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="DELETEapi-posts--post-" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>post</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="post" data-endpoint="DELETEapi-posts--post-" data-component="url" required  hidden>
<br>
</p>
</form>


## Display a list of comments for the specified post.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X GET \
    -G "http://localhost:8000/api/posts/aut/comments" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts/aut/comments"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "GET",
    headers,
}).then(response => response.json());
```


> Example response (404):

```json
{
    "error": "Resource not found"
}
```
<div id="execution-results-GETapi-posts--post--comments" hidden>
    <blockquote>Received response<span id="execution-response-status-GETapi-posts--post--comments"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-GETapi-posts--post--comments"></code></pre>
</div>
<div id="execution-error-GETapi-posts--post--comments" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-GETapi-posts--post--comments"></code></pre>
</div>
<form id="form-GETapi-posts--post--comments" data-method="GET" data-path="api/posts/{post}/comments" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('GETapi-posts--post--comments', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-GETapi-posts--post--comments" onclick="tryItOut('GETapi-posts--post--comments');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-GETapi-posts--post--comments" onclick="cancelTryOut('GETapi-posts--post--comments');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-GETapi-posts--post--comments" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-green">GET</small>
 <b><code>api/posts/{post}/comments</code></b>
</p>
<p>
<label id="auth-GETapi-posts--post--comments" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="GETapi-posts--post--comments" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>post</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="post" data-endpoint="GETapi-posts--post--comments" data-component="url" required  hidden>
<br>
</p>
</form>


## Store a newly created comment in the database.

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X POST \
    "http://localhost:8000/api/posts/et/comments" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts/et/comments"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "POST",
    headers,
}).then(response => response.json());
```


> Example response (404):

```json
{
    "error": "Resource not found"
}
```
<div id="execution-results-POSTapi-posts--post--comments" hidden>
    <blockquote>Received response<span id="execution-response-status-POSTapi-posts--post--comments"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-POSTapi-posts--post--comments"></code></pre>
</div>
<div id="execution-error-POSTapi-posts--post--comments" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-POSTapi-posts--post--comments"></code></pre>
</div>
<form id="form-POSTapi-posts--post--comments" data-method="POST" data-path="api/posts/{post}/comments" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('POSTapi-posts--post--comments', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-POSTapi-posts--post--comments" onclick="tryItOut('POSTapi-posts--post--comments');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-POSTapi-posts--post--comments" onclick="cancelTryOut('POSTapi-posts--post--comments');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-POSTapi-posts--post--comments" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-black">POST</small>
 <b><code>api/posts/{post}/comments</code></b>
</p>
<p>
<label id="auth-POSTapi-posts--post--comments" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="POSTapi-posts--post--comments" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>post</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="post" data-endpoint="POSTapi-posts--post--comments" data-component="url" required  hidden>
<br>
</p>
</form>


## Update the specified comment in the database

<small class="badge badge-darkred">requires authentication</small>



> Example request:

```bash
curl -X PUT \
    "http://localhost:8000/api/posts/voluptatem/comments/dicta" \
    -H "Authorization: Bearer {YOUR_AUTH_KEY}" \
    -H "Content-Type: application/json" \
    -H "Accept: application/json"
```

```javascript
const url = new URL(
    "http://localhost:8000/api/posts/voluptatem/comments/dicta"
);

let headers = {
    "Authorization": "Bearer {YOUR_AUTH_KEY}",
    "Content-Type": "application/json",
    "Accept": "application/json",
};


fetch(url, {
    method: "PUT",
    headers,
}).then(response => response.json());
```


<div id="execution-results-PUTapi-posts--post--comments--comment-" hidden>
    <blockquote>Received response<span id="execution-response-status-PUTapi-posts--post--comments--comment-"></span>:</blockquote>
    <pre class="json"><code id="execution-response-content-PUTapi-posts--post--comments--comment-"></code></pre>
</div>
<div id="execution-error-PUTapi-posts--post--comments--comment-" hidden>
    <blockquote>Request failed with error:</blockquote>
    <pre><code id="execution-error-message-PUTapi-posts--post--comments--comment-"></code></pre>
</div>
<form id="form-PUTapi-posts--post--comments--comment-" data-method="PUT" data-path="api/posts/{post}/comments/{comment}" data-authed="1" data-hasfiles="0" data-headers='{"Authorization":"Bearer {YOUR_AUTH_KEY}","Content-Type":"application\/json","Accept":"application\/json"}' onsubmit="event.preventDefault(); executeTryOut('PUTapi-posts--post--comments--comment-', this);">
<h3>
    Request&nbsp;&nbsp;&nbsp;
        <button type="button" style="background-color: #8fbcd4; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-tryout-PUTapi-posts--post--comments--comment-" onclick="tryItOut('PUTapi-posts--post--comments--comment-');">Try it out ⚡</button>
    <button type="button" style="background-color: #c97a7e; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-canceltryout-PUTapi-posts--post--comments--comment-" onclick="cancelTryOut('PUTapi-posts--post--comments--comment-');" hidden>Cancel</button>&nbsp;&nbsp;
    <button type="submit" style="background-color: #6ac174; padding: 5px 10px; border-radius: 5px; border-width: thin;" id="btn-executetryout-PUTapi-posts--post--comments--comment-" hidden>Send Request 💥</button>
    </h3>
<p>
<small class="badge badge-darkblue">PUT</small>
 <b><code>api/posts/{post}/comments/{comment}</code></b>
</p>
<p>
<small class="badge badge-purple">PATCH</small>
 <b><code>api/posts/{post}/comments/{comment}</code></b>
</p>
<p>
<label id="auth-PUTapi-posts--post--comments--comment-" hidden>Authorization header: <b><code>Bearer </code></b><input type="text" name="Authorization" data-prefix="Bearer " data-endpoint="PUTapi-posts--post--comments--comment-" data-component="header"></label>
</p>
<h4 class="fancy-heading-panel"><b>URL Parameters</b></h4>
<p>
<b><code>post</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="post" data-endpoint="PUTapi-posts--post--comments--comment-" data-component="url" required  hidden>
<br>
</p>
<p>
<b><code>comment</code></b>&nbsp;&nbsp;<small>string</small>  &nbsp;
<input type="text" name="comment" data-endpoint="PUTapi-posts--post--comments--comment-" data-component="url" required  hidden>
<br>
</p>
</form>



