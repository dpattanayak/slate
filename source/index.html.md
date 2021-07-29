---
title: Improductive v1.0.0
language_tabs:
  - shell: Shell
  - ruby: Ruby
  - python: Python
  - javascript: Javascript
language_clients:
  - shell: ""
  - ruby: ""
  - python: ""
  - javascript: ""
toc_footers:
  - <a href="http://swagger.io">Find out more about Swagger</a>
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="improductive">Improductive v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Zapier API Details

Base URLs:

* <a href="https://api.improductive.com/api/v1">https://api.improductive.com/api/v1</a>

* <a href="http://api.improductive.com/api/v1">http://api.improductive.com/api/v1</a>

<a href="https://improductive.com/privacy/">Terms of service</a>
Email: <a href="mailto:startup@improductive.com">Support</a> 

# Authentication

- oAuth2 authentication. 

    - Flow: implicit
    - Authorization URL = [http://petstore.swagger.io/oauth/dialog](http://petstore.swagger.io/oauth/dialog)

|Scope|Scope Description|
|---|---|
|write:pets|modify pets in your account|
|read:pets|read your pets|

* API Key (api_key)
    - Parameter Name: **api_key**, in: header. 

<h1 id="improductive-project">Project</h1>

Everything about your project

## Find Project by Id

> Code samples

```shell
# You can also use wget
curl -X GET https://api.improductive.com/api/v1/project?project_id=string \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.get 'https://api.improductive.com/api/v1/project',
  params: {
  'project_id' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.get('https://api.improductive.com/api/v1/project', params={
  'project_id': 'string'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/project?project_id=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /project`

Find a project details.

<h3 id="find-project-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|project_id|query|string|true|none|

> Example responses

> 200 Response

<h3 id="find-project-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="find-project-by-id-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» results|[object]|false|none|none|
|»» _id|string|false|none|none|
|»» created_At|string|false|none|none|
|»» updated_At|string|false|none|none|
|»» name|string|false|none|none|
|»» projectkey|string|false|none|none|
|»» __v|number|false|none|none|
|»» sections|object|false|none|none|
|»»» section|[string]|false|none|none|
|»» workflow|object|false|none|none|
|»»» name|string|false|none|none|
|»»» flow|[string]|false|none|none|
|»» projectType|string|false|none|none|
|»» deleted|boolean|false|none|none|
|»» assigned|[string]|false|none|none|
|»» status|string|false|none|none|
|»» jekyll_path|string|false|none|none|
|»» smtp|object|false|none|none|
|»»» template|string|false|none|none|
|»» type|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create Project

> Code samples

```shell
# You can also use wget
curl -X POST https://api.improductive.com/api/v1/project \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.post 'https://api.improductive.com/api/v1/project',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.post('https://api.improductive.com/api/v1/project', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "name": "string",
  "projectkey": "string",
  "workflow": {
    "name": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/project',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /project`

Adds a new project.

> Body parameter

```json
{
  "name": "string",
  "projectkey": "string",
  "workflow": {
    "name": "string"
  }
}
```

<h3 id="create-project-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|body|body|[Project](#schemaproject)|true|Create Project|

> Example responses

> 200 Response

<h3 id="create-project-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="create-project-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|string|false|none|none|
|» project_id|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="improductive-list">List</h1>

Everything about your list

## Find List

> Code samples

```shell
# You can also use wget
curl -X GET https://api.improductive.com/api/v1/milestone?project_id=string \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string' \
  -H 'user-agent: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string',
  'user-agent' => 'string'
}

result = RestClient.get 'https://api.improductive.com/api/v1/milestone',
  params: {
  'project_id' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string',
  'user-agent': 'string'
}

r = requests.get('https://api.improductive.com/api/v1/milestone', params={
  'project_id': 'string'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string',
  'user-agent':'string'
};

fetch('https://api.improductive.com/api/v1/milestone?project_id=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /milestone`

Find list for a project.

<h3 id="find-list-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|user-agent|header|string|true|none|
|project_id|query|string|true|none|

> Example responses

> 200 Response

<h3 id="find-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="find-list-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» results|[object]|false|none|none|
|»» _id|string|false|none|none|
|»» title|string|false|none|none|
|»» description|string|false|none|none|
|»» projectid|string|false|none|none|
|»» __v|number|false|none|none|
|»» sections|object|false|none|none|
|»»» section|[string]|false|none|none|
|»» deleted|boolean|false|none|none|
|»» updatedate|string|false|none|none|
|»» createdate|string|false|none|none|
|»» status|string|false|none|none|
|»» type|string|false|none|none|
|» info|[object]|false|none|none|
|»» _id|string|false|none|none|
|»» total|object|false|none|none|
|»»» count|number|false|none|none|
|»»» hrs|number|false|none|none|
|»» open|object|false|none|none|
|»»» count|number|false|none|none|
|»»» hrs|number|false|none|none|
|»» closed|object|false|none|none|
|»»» count|number|false|none|none|
|»»» hrs|number|false|none|none|
|»» incomplete|object|false|none|none|
|»»» count|number|false|none|none|
|»»» hrs|number|false|none|none|
|»» inreview|object|false|none|none|
|»»» count|number|false|none|none|
|»»» hrs|number|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create List

> Code samples

```shell
# You can also use wget
curl -X POST https://api.improductive.com/api/v1/milestone \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.post 'https://api.improductive.com/api/v1/milestone',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.post('https://api.improductive.com/api/v1/milestone', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "title": "string",
  "description": "string",
  "type": "string",
  "projectid": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/milestone',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /milestone`

Adds a new list.

> Body parameter

```json
{
  "title": "string",
  "description": "string",
  "type": "string",
  "projectid": 0
}
```

<h3 id="create-list-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|body|body|[List](#schemalist)|true|Create List|

> Example responses

> 200 Response

<h3 id="create-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="create-list-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|string|false|none|none|
|» data|object|false|none|none|
|»» __v|number|false|none|none|
|»» title|string|false|none|none|
|»» description|string|false|none|none|
|»» type|string|false|none|none|
|»» projectid|string|false|none|none|
|»» _id|string|false|none|none|
|»» sections|object|false|none|none|
|»»» section|[string]|false|none|none|
|»» deleted|boolean|false|none|none|
|»» updatedate|string|false|none|none|
|»» createdate|string|false|none|none|
|»» status|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="improductive-section">Section</h1>

Everything about your section

## Get a Section

> Code samples

```shell
# You can also use wget
curl -X GET https://api.improductive.com/api/v1/issue/section?milestone_id=string&project_id=string \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.get 'https://api.improductive.com/api/v1/issue/section',
  params: {
  'milestone_id' => 'string',
'project_id' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.get('https://api.improductive.com/api/v1/issue/section', params={
  'milestone_id': 'string',  'project_id': 'string'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/issue/section?milestone_id=string&project_id=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /issue/section`

Get a Section Details.

<h3 id="get-a-section-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|milestone_id|query|string|true|none|
|project_id|query|string|true|none|

> Example responses

> 200 Response

<h3 id="get-a-section-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="get-a-section-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» results|[object]|false|none|none|
|»» _id|string|false|none|none|
|»» title|string|false|none|none|
|»» projectid|string|false|none|none|
|»» milestoneid|string|false|none|none|
|»» createdby|object|false|none|none|
|»»» _id|string|false|none|none|
|»»» username|string|false|none|none|
|»» updatedby|object|false|none|none|
|»»» _id|string|false|none|none|
|»»» username|string|false|none|none|
|»» issue_id|string|false|none|none|
|»» __v|number|false|none|none|
|»» deleted|boolean|false|none|none|
|»» taskdocs|[string]|false|none|none|
|»» difficulty|string|false|none|none|
|»» attachmentlinks|[string]|false|none|none|
|»» attachments|[string]|false|none|none|
|»» likes|[string]|false|none|none|
|»» comments|[string]|false|none|none|
|»» history|[string]|false|none|none|
|»» logs|[string]|false|none|none|
|»» updatedate|string|false|none|none|
|»» createdate|string|false|none|none|
|»» priority|string|false|none|none|
|»» section|string|false|none|none|
|»» workflow|object|false|none|none|
|»»» flow|[string]|false|none|none|
|»» parentStatus|string|false|none|none|
|»» status|string|false|none|none|
|»» tags|[string]|false|none|none|
|»» tasktype|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create Section

> Code samples

```shell
# You can also use wget
curl -X POST https://api.improductive.com/api/v1/issue/section \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.post 'https://api.improductive.com/api/v1/issue/section',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.post('https://api.improductive.com/api/v1/issue/section', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "title": "string",
  "section": "string",
  "projectid": 0,
  "milestoneid": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/issue/section',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /issue/section`

Adds a new section.

> Body parameter

```json
{
  "title": "string",
  "section": "string",
  "projectid": 0,
  "milestoneid": 0
}
```

<h3 id="create-section-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|body|body|[Section](#schemasection)|true|Create Section|

> Example responses

> 200 Response

<h3 id="create-section-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="create-section-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|string|false|none|none|
|» results|object|false|none|none|
|»» __v|number|false|none|none|
|»» title|string|false|none|none|
|»» type|string|false|none|none|
|»» projectid|string|false|none|none|
|»» _id|string|false|none|none|
|»» issue_id|string|false|none|none|
|»» difficulty|string|false|none|none|
|»» priority|string|false|none|none|
|»» section|string|false|none|none|
|»» parentStatus|string|false|none|none|
|»» tasktype|string|false|none|none|
|»» deleted|boolean|false|none|none|
|»» updatedate|string|false|none|none|
|»» createdate|string|false|none|none|
|»» status|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="improductive-task">Task</h1>

Everything about your task

## Find Task of a List

> Code samples

```shell
# You can also use wget
curl -X GET https://api.improductive.com/api/v1/issue?tasktype=string&milestone_id=string&project_id=string \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.get 'https://api.improductive.com/api/v1/issue',
  params: {
  'tasktype' => 'string',
'milestone_id' => 'string',
'project_id' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.get('https://api.improductive.com/api/v1/issue', params={
  'tasktype': 'string',  'milestone_id': 'string',  'project_id': 'string'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/issue?tasktype=string&milestone_id=string&project_id=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /issue`

Find All Tasks of a List

<h3 id="find-task-of-a-list-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|tasktype|query|string|true|none|
|milestone_id|query|string|true|none|
|project_id|query|string|true|none|

> Example responses

> 200 Response

<h3 id="find-task-of-a-list-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="find-task-of-a-list-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» results|[object]|false|none|none|
|»» _id|string|false|none|none|
|»» title|string|false|none|none|
|»» description|string|false|none|none|
|»» projectid|string|false|none|none|
|»» milestoneid|string|false|none|none|
|»» estimatedtime|number|false|none|none|
|»» createdby|object|false|none|none|
|»»» _id|string|false|none|none|
|»»» username|string|false|none|none|
|»» updatedby|object|false|none|none|
|»»» _id|string|false|none|none|
|»»» username|string|false|none|none|
|»» issue_id|string|false|none|none|
|»» __v|number|false|none|none|
|»» type|string|false|none|none|
|»» deleted|boolean|false|none|none|
|»» taskdocs|[string]|false|none|none|
|»» difficulty|string|false|none|none|
|»» attachmentlinks|[string]|false|none|none|
|»» attachments|[string]|false|none|none|
|»» likes|[string]|false|none|none|
|»» comments|[string]|false|none|none|
|»» history|[object]|false|none|none|
|»»» historyContent|string|false|none|none|
|»»» historyType|string|false|none|none|
|»»» _id|string|false|none|none|
|»»» updatedate|string|false|none|none|
|»»» status|string|false|none|none|
|»» logs|[string]|false|none|none|
|»» updatedate|string|false|none|none|
|»» createdate|string|false|none|none|
|»» priority|string|false|none|none|
|»» section|string|false|none|none|
|»» workflow|object|false|none|none|
|»»» flow|[string]|false|none|none|
|»» parentStatus|string|false|none|none|
|»» status|string|false|none|none|
|»» tags|[string]|false|none|none|
|»» tasktype|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create Task

> Code samples

```shell
# You can also use wget
curl -X POST https://api.improductive.com/api/v1/issue \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.post 'https://api.improductive.com/api/v1/issue',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.post('https://api.improductive.com/api/v1/issue', headers = headers)

print(r.json())

```

```javascript
const inputBody = '{
  "title": "string",
  "description": "string",
  "type": "string",
  "priority": "string",
  "projectid": 0,
  "milestoneid": 0,
  "estimatedtime": 0,
  "section": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/issue',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`POST /issue`

Adds a new task.

> Body parameter

```json
{
  "title": "string",
  "description": "string",
  "type": "string",
  "priority": "string",
  "projectid": 0,
  "milestoneid": 0,
  "estimatedtime": 0,
  "section": "string"
}
```

<h3 id="create-task-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|body|body|[Task](#schematask)|true|Create Task|

> Example responses

> 200 Response

<h3 id="create-task-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="create-task-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|string|false|none|none|
|» results|object|false|none|none|
|»» __v|number|false|none|none|
|»» title|string|false|none|none|
|»» description|string|false|none|none|
|»» projectid|string|false|none|none|
|»» milestoneid|string|false|none|none|
|»» estimatedtime|number|false|none|none|
|»» type|string|false|none|none|
|»» createdby|string|false|none|none|
|»» updatedby|string|false|none|none|
|»» issue_id|string|false|none|none|
|»» _id|string|false|none|none|
|»» deleted|boolean|false|none|none|
|»» difficulty|string|false|none|none|
|»» history|[object]|false|none|none|
|»»» historyContent|string|false|none|none|
|»»» historyType|string|false|none|none|
|»»» _id|string|false|none|none|
|»»» updatedate|string|false|none|none|
|»»» status|string|false|none|none|
|»» updatedate|string|false|none|none|
|»» createdate|string|false|none|none|
|»» priority|string|false|none|none|
|»» section|string|false|none|none|
|»» workflow|object|false|none|none|
|»»» flow|[string]|false|none|none|
|»» parentStatus|string|false|none|none|
|»» status|string|false|none|none|
|»» tasktype|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Search a Task

> Code samples

```shell
# You can also use wget
curl -X GET https://api.improductive.com/api/v1/issue/search?search=string \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string' \
  -H 'user-agent: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string',
  'user-agent' => 'string'
}

result = RestClient.get 'https://api.improductive.com/api/v1/issue/search',
  params: {
  'search' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string',
  'user-agent': 'string'
}

r = requests.get('https://api.improductive.com/api/v1/issue/search', params={
  'search': 'string'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string',
  'user-agent':'string'
};

fetch('https://api.improductive.com/api/v1/issue/search?search=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /issue/search`

Search a Task by Task Title

<h3 id="search-a-task-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|user-agent|header|string|true|none|
|search|query|string|true|none|

> Example responses

> 200 Response

<h3 id="search-a-task-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="search-a-task-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|string|false|none|none|
|» results|[object]|false|none|none|
|»» _id|string|false|none|none|
|»» title|string|false|none|none|
|»» description|string|false|none|none|
|»» projectid|string|false|none|none|
|»» milestoneid|string|false|none|none|
|»» estimatedtime|number|false|none|none|
|»» createdby|string|false|none|none|
|»» updatedby|string|false|none|none|
|»» issue_id|string|false|none|none|
|»» __v|number|false|none|none|
|»» deleted|boolean|false|none|none|
|»» taskdocs|[string]|false|none|none|
|»» difficulty|string|false|none|none|
|»» attachmentlinks|[string]|false|none|none|
|»» attachments|[string]|false|none|none|
|»» likes|[string]|false|none|none|
|»» comments|[string]|false|none|none|
|»» history|[string]|false|none|none|
|»» logs|[string]|false|none|none|
|»» updatedate|string|false|none|none|
|»» createdate|string|false|none|none|
|»» priority|string|false|none|none|
|»» section|string|false|none|none|
|»» workflow|object|false|none|none|
|»»» flow|[string]|false|none|none|
|»» parentStatus|string|false|none|none|
|»» status|string|false|none|none|
|»» tags|[string]|false|none|none|
|»» tasktype|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="improductive-user">User</h1>

Everything about your user

## Find User by Username

> Code samples

```shell
# You can also use wget
curl -X GET https://api.improductive.com/api/v1/account/search?key=string \
  -H 'Accept: */*' \
  -H 'api_key: string' \
  -H 'content-type: string'

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'api_key' => 'string',
  'content-type' => 'string'
}

result = RestClient.get 'https://api.improductive.com/api/v1/account/search',
  params: {
  'key' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'api_key': 'string',
  'content-type': 'string'
}

r = requests.get('https://api.improductive.com/api/v1/account/search', params={
  'key': 'string'
}, headers = headers)

print(r.json())

```

```javascript

const headers = {
  'Accept':'*/*',
  'api_key':'string',
  'content-type':'string'
};

fetch('https://api.improductive.com/api/v1/account/search?key=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

`GET /account/search`

Finds a user.

<h3 id="find-user-by-username-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|true|none|
|content-type|header|string|true|none|
|key|query|string|true|none|

> Example responses

> 200 Response

<h3 id="find-user-by-username-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="find-user-by-username-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|string|false|none|none|
|» data|[object]|false|none|none|
|»» password|string|false|none|none|
|»» _id|string|false|none|none|
|»» username|string|false|none|none|
|»» email|string|false|none|none|
|»» phone|string|false|none|none|
|»» name|string|false|none|none|
|»» country|string|false|none|none|
|»» clientid|string|false|none|none|
|»» client_db|string|false|none|none|
|»» emailToken|string|false|none|none|
|»» __v|number|false|none|none|
|»» Join_Date|string|false|none|none|
|»» profile_img|string|false|none|none|
|»» fpToken|string|false|none|none|
|»» passToken|string|false|none|none|
|»» last_name|string|false|none|none|
|»» api_key|string|false|none|none|
|»» settings|object|false|none|none|
|»»» notification|boolean|false|none|none|
|»» logincount|number|false|none|none|
|»» skills|[string]|false|none|none|
|»» deleted|boolean|false|none|none|
|»» created_At|string|false|none|none|
|»» updated_At|string|false|none|none|
|»» provider|string|false|none|none|
|»» lm|string|false|none|none|
|»» cd|string|false|none|none|
|»» status|string|false|none|none|
|»» projectid|[string]|false|none|none|
|»» role|string|false|none|none|
|»» message|[string]|false|none|none|
|»» max_project_size|number|false|none|none|
|»» total_donated|number|false|none|none|
|»» current_bonus|number|false|none|none|
|»» type|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Project">Project</h2>
<!-- backwards compatibility -->
<a id="schemaproject"></a>
<a id="schema_Project"></a>
<a id="tocSproject"></a>
<a id="tocsproject"></a>

```json
{
  "name": "string",
  "projectkey": "string",
  "workflow": {
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|projectkey|string|false|none|none|
|workflow|[Workflow](#schemaworkflow)|false|none|none|

<h2 id="tocS_Workflow">Workflow</h2>
<!-- backwards compatibility -->
<a id="schemaworkflow"></a>
<a id="schema_Workflow"></a>
<a id="tocSworkflow"></a>
<a id="tocsworkflow"></a>

```json
{
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|

<h2 id="tocS_List">List</h2>
<!-- backwards compatibility -->
<a id="schemalist"></a>
<a id="schema_List"></a>
<a id="tocSlist"></a>
<a id="tocslist"></a>

```json
{
  "title": "string",
  "description": "string",
  "type": "string",
  "projectid": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|description|string|false|none|none|
|type|string|false|none|none|
|projectid|integer(int32)|false|none|none|

<h2 id="tocS_Section">Section</h2>
<!-- backwards compatibility -->
<a id="schemasection"></a>
<a id="schema_Section"></a>
<a id="tocSsection"></a>
<a id="tocssection"></a>

```json
{
  "title": "string",
  "section": "string",
  "projectid": 0,
  "milestoneid": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|section|string|false|none|none|
|projectid|integer(int32)|false|none|none|
|milestoneid|integer(int32)|false|none|none|

<h2 id="tocS_Task">Task</h2>
<!-- backwards compatibility -->
<a id="schematask"></a>
<a id="schema_Task"></a>
<a id="tocStask"></a>
<a id="tocstask"></a>

```json
{
  "title": "string",
  "description": "string",
  "type": "string",
  "priority": "string",
  "projectid": 0,
  "milestoneid": 0,
  "estimatedtime": 0,
  "section": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|description|string|false|none|none|
|type|string|false|none|none|
|priority|string|false|none|none|
|projectid|integer(int32)|false|none|none|
|milestoneid|integer(int32)|false|none|none|
|estimatedtime|integer(int32)|false|none|none|
|section|string|false|none|none|

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "id": 0,
  "username": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "password": "string",
  "phone": "string",
  "userStatus": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|username|string|false|none|none|
|firstName|string|false|none|none|
|lastName|string|false|none|none|
|email|string|false|none|none|
|password|string|false|none|none|
|phone|string|false|none|none|
|userStatus|integer(int32)|false|none|User Status|

<h2 id="tocS_ApiResponse">ApiResponse</h2>
<!-- backwards compatibility -->
<a id="schemaapiresponse"></a>
<a id="schema_ApiResponse"></a>
<a id="tocSapiresponse"></a>
<a id="tocsapiresponse"></a>

```json
{
  "code": 0,
  "type": "string",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|false|none|none|
|type|string|false|none|none|
|message|string|false|none|none|

