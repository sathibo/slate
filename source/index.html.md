---
title: API Reference
language_tabs:
  - shell
  - java
  - python
  - php
toc_footers:
 - <a href='#'>Sign Up for a Developer Key</a>
includes:
    - errors
search: true
---
# Introduction

```
We have language bindings in java, python, php! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.
```

An analytics platform API that lets you create your own analytics services.

### Version
Version: 1.0

## Contact Information
Email: contact@rakam.com

### License
License: Apache License 2.0

License url: http://www.apache.org/licenses/LICENSE-2.0.html

### URI scheme
Host: https://app.getrakam.com
BasePath: /

# Event stream


Event Stream Module

## Subscribe Event Stream
```shell
curl "https://app.getrakam.com/stream/subscribe" -X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.EventstreamApi();
api.subscribe();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventstreamApi;

ApiClient apiClient = new ApiClient();

EventstreamApi api = new EventstreamApi(apiClient);
api.subscribe();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\EventstreamApi($api_client);
$api->subscribe();


```

### HTTP Request
`GET /stream/subscribe`
### Responses for status codes
|400|
|----|
||



Subscribes the event stream periodically to the client.

# Funnel


Funnel Analyzer module

## Execute query
```shell
curl "https://app.getrakam.com/funnel/analyze" -H "read_key: myread_key" -X GET -d @- << EOF 
{
  "project" : "str",
  "steps" : [ {
    "collection" : "str",
    "filterExpression" : "str"
  } ],
  "dimension" : "str",
  "startDate" : "2015-01-20",
  "endDate" : "2015-01-20",
  "enableOtherGrouping" : true
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.FunnelApi();
api.analyze(funnel_query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.FunnelApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
FunnelApi api = new FunnelApi(apiClient);
api.analyze(funnelQuery);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\FunnelApi($api_client);
$api->analyze(funnel_query);


```

### HTTP Request
`GET /funnel/analyze`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|steps|false|[FunnelStep](#funnelstep) array||
|dimension|false|string||
|startDate|false|string (date)||
|endDate|false|string (date)||
|enableOtherGrouping|false|boolean||


### Responses for status codes
|default|
|----|
||


# Retention


Retention Analyzer module

## Execute query
```shell
curl "https://app.getrakam.com/retention/analyze" -H "read_key: myread_key" -X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RetentionApi();
api.execute();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RetentionApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RetentionApi api = new RetentionApi(apiClient);
api.execute();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RetentionApi($api_client);
$api->execute();


```

### HTTP Request
`GET /retention/analyze`
### Responses for status codes
|default|
|----|
||


# User


User module for Rakam

## Create new user
```shell
curl "https://app.getrakam.com/user/create" -X POST -d @- << EOF 
{
  "project" : "str",
  "properties" : {
    "prop" : { }
  }
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.UserApi();
api.create(user_http_service_create);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.create(userHttpServiceCreate);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->create(user_http_service_create);


```

> The above command returns JSON structured like this:

```json
{
  "identifier" : "object"
}
```

### HTTP Request
`POST /user/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|properties|false|object||


### Responses for status codes
|200|400|
|----|----|
|[CreateUserResponse](#createuserresponse)|


## Get user
```shell
curl "https://app.getrakam.com/user/get" -X POST -d @- << EOF 
{
  "project" : "str",
  "user" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.UserApi();
api.get_user(project, user);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.getUser(project, user);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->getUser(project, user);


```

> The above command returns JSON structured like this:

```json
{
  "project" : "str",
  "id" : "object",
  "properties" : {
    "prop" : { }
  }
}
```

### HTTP Request
`POST /user/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||


### Responses for status codes
|200|400|
|----|----|
|[User](#user)|


## Get events of the user
```shell
curl "https://app.getrakam.com/user/get_events" -X POST -d @- << EOF 
{
  "project" : "str",
  "user" : "str",
  "limit" : 0,
  "offset" : 0
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.UserApi();
api.get_events(project, user, limit, offset);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.getEvents(project, user, limit, offset);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->getEvents(project, user, limit, offset);


```

> The above command returns JSON structured like this:

```json
[ "object" ]
```

### HTTP Request
`POST /user/get_events`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|limit|false|integer (int32)||
|offset|false|integer (int64)||


### Responses for status codes
|200|400|
|----|----|
|object array|


## Get user storage metadata
```shell
curl "https://app.getrakam.com/user/metadata" -X POST -d @- << EOF 
{
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.UserApi();
api.metadata(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.metadata(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->metadata(project);


```

> The above command returns JSON structured like this:

```json
{
  "columns" : [ {
    "name" : "str",
    "type" : "STRING",
    "nullable" : true,
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "identifierColumn" : "str"
}
```

### HTTP Request
`POST /user/metadata`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|200|400|
|----|----|
|[MetadataResponse](#metadataresponse)|


## Search users
```shell
curl "https://app.getrakam.com/user/search" -X POST -d @- << EOF 
{
  "project" : "str",
  "filter" : "str",
  "event_filters" : [ {
    "collection" : "str",
    "aggregation" : {
      "field" : "str",
      "minimum" : 1,
      "maximum" : 1,
      "type" : "COUNT"
    },
    "filterExpression" : "str"
  } ],
  "sorting" : {
    "column" : "str",
    "order" : "asc"
  },
  "offset" : 1,
  "limit" : 1
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.UserApi();
api.search(user_http_service_search);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.search(userHttpServiceSearch);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->search(user_http_service_search);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "STRING",
    "nullable" : true,
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
}
```

### HTTP Request
`POST /user/search`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|filter|false|string||
|event_filters|false|[EventFilter](#eventfilter) array||
|sorting|false|[Sorting](#sorting)||
|offset|false|integer (int32)||
|limit|false|integer (int32)||


### Responses for status codes
|200|400|
|----|----|
|[QueryResult](#queryresult)|


## Set user property
```shell
curl "https://app.getrakam.com/user/set_property" -X POST -d @- << EOF 
{
  "project" : "str",
  "user" : "str",
  "property" : "str",
  "value" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.UserApi();
api.set_user_property(project, user, property, value);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UserApi;

ApiClient apiClient = new ApiClient();

UserApi api = new UserApi(apiClient);
api.setUserProperty(project, user, property, value);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\UserApi($api_client);
$api->setUserProperty(project, user, property, value);


```

> The above command returns JSON structured like this:

```json
{
  "success" : true,
  "message" : "str"
}
```

### HTTP Request
`POST /user/set_property`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|property|false|string||
|value|false|string||


### Responses for status codes
|200|400|
|----|----|
|[JsonResponse](#jsonresponse)|


# User mailbox




## Get user mailbox
```shell
curl "https://app.getrakam.com/user/mailbox/get" -H "read_key: myread_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "user" : "str",
  "parent" : 0,
  "limit" : 0,
  "offset" : 0
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.get(project, user, parent, limit, offset);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi(apiClient);
api.get(project, user, parent, limit, offset);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->get(project, user, parent, limit, offset);


```

> The above command returns JSON structured like this:

```json
[ {
  "id" : 1,
  "content" : "str",
  "from_user" : "object",
  "to_user" : "object",
  "parentId" : 1,
  "seen" : true,
  "time" : 1,
  "project" : "str"
} ]
```

### HTTP Request
`POST /user/mailbox/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|parent|false|integer (int32)||
|limit|false|integer (int32)||
|offset|false|integer (int64)||


### Responses for status codes
|200|400|404|
|----|----|----|
|[Message](#message) array|



Returns the last mails sent to the user

## Get connected users
```shell
curl "https://app.getrakam.com/user/mailbox/getOnlineUsers" -H "read_key: myread_key" -X POST -d @- << EOF 
{
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.get_connected_users(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi(apiClient);
api.getConnectedUsers(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->getConnectedUsers(project);


```

> The above command returns JSON structured like this:

```json
[ "object" ]
```

### HTTP Request
`POST /user/mailbox/getOnlineUsers`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|200|400|
|----|----|
|object array|


## Listen all mailboxes
```shell
curl "https://app.getrakam.com/user/mailbox/listen" -H "read_key: myread_key" -X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.listen(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi(apiClient);
api.listen(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->listen(project);


```

### HTTP Request
`GET /user/mailbox/listen`
### Query Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|default|
|----|
||


## Mark mail as read
```shell
curl "https://app.getrakam.com/user/mailbox/mark_as_read" -H "write_key: mywrite_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "user" : "str",
  "message_ids" : [ 1 ]
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.mark_as_read(project, user, message_ids);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi(apiClient);
api.markAsRead(project, user, messageIds);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->markAsRead(project, user, message_ids);


```

> The above command returns JSON structured like this:

```json
{
  "success" : true,
  "message" : "str"
}
```

### HTTP Request
`POST /user/mailbox/mark_as_read`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|user|false|string||
|message_ids|false|multi integer (int32) array||


### Responses for status codes
|200|400|404|
|----|----|----|
|[JsonResponse](#jsonresponse)|



Marks the specified mails as read.

## Send mail to user
```shell
curl "https://app.getrakam.com/user/mailbox/send" -H "write_key: mywrite_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "from_user" : "str",
  "to_user" : "str",
  "parent" : 0,
  "message" : "str",
  "timestamp" : 0
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.UsermailboxApi();
api.send(project, from_user, to_user, parent, message, timestamp);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.UsermailboxApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
UsermailboxApi api = new UsermailboxApi(apiClient);
api.send(project, fromUser, toUser, parent, message, timestamp);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\UsermailboxApi($api_client);
$api->send(project, from_user, to_user, parent, message, timestamp);


```

> The above command returns JSON structured like this:

```json
{
  "id" : 1,
  "content" : "str",
  "from_user" : "object",
  "to_user" : "object",
  "parentId" : 1,
  "seen" : true,
  "time" : 1,
  "project" : "str"
}
```

### HTTP Request
`POST /user/mailbox/send`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|from_user|false|string||
|to_user|false|string||
|parent|false|integer (int32)||
|message|false|string||
|timestamp|false|integer (int64)||


### Responses for status codes
|200|400|404|
|----|----|----|
|[Message](#message)|



Sends a mail to users mailbox

# Realtime




## Create report
```shell
curl "https://app.getrakam.com/realtime/create" -H "read_key: myread_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "name" : "str",
  "chart" : "str",
  "collections" : [ "str" ],
  "aggregation" : "str",
  "table_name" : "str",
  "filter" : "str",
  "measure" : "str",
  "dimension" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.create(project, name, chart, collections, aggregation, table_name, filter, measure, dimension);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.create(project, name, chart, collections, aggregation, tableName, filter, measure, dimension);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->create(project, name, chart, collections, aggregation, table_name, filter, measure, dimension);


```

> The above command returns JSON structured like this:

```json
{
  "success" : true,
  "message" : "str"
}
```

### HTTP Request
`POST /realtime/create`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|chart|false|string||
|collections|false|multi string array||
|aggregation|false|string||
|table_name|false|string||
|filter|false|string||
|measure|false|string||
|dimension|false|string||


### Responses for status codes
|200|400|
|----|----|
|[JsonResponse](#jsonresponse)|


## Delete report
```shell
curl "https://app.getrakam.com/realtime/delete" -H "read_key: myread_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.delete(project, name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.delete(project, name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->delete(project, name);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /realtime/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||


### Responses for status codes
|200|
|----|
|object|


## Get report
```shell
curl "https://app.getrakam.com/realtime/get" -H "read_key: myread_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "table_name" : "str",
  "filter" : "str",
  "aggregate" : false,
  "date_start" : "str",
  "date_end" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.get(project, table_name, filter, aggregate, date_start, date_end);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.get(project, tableName, filter, aggregate, dateStart, dateEnd);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->get(project, table_name, filter, aggregate, date_start, date_end);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /realtime/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|table_name|false|string||
|filter|false|string||
|aggregate|false|boolean||
|date_start|false|string (date-time)||
|date_end|false|string (date-time)||


### Responses for status codes
|200|400|
|----|----|
|object|


## List reports
```shell
curl "https://app.getrakam.com/realtime/list" -H "read_key: myread_key" -X POST -d @- << EOF 
{
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.RealtimeApi();
api.list_reports(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.RealtimeApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
RealtimeApi api = new RealtimeApi(apiClient);
api.listReports(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\RealtimeApi($api_client);
$api->listReports(project);


```

> The above command returns JSON structured like this:

```json
[ "object" ]
```

### HTTP Request
`POST /realtime/list`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|200|
|----|
|object array|


# Admin


System related actions

## List installed modules
```shell
curl "https://app.getrakam.com/admin/modules" -H "master_key: mymaster_key" -X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['master_key'] = 'myApiKey'

api = client.AdminApi();
api.get_modules();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.AdminApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("master_key").setApiKey("myApiKey");
AdminApi api = new AdminApi(apiClient);
api.getModules();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("master_key", "myApiKey");

$api = new Swagger\Client\AdminApi($api_client);
$api->getModules();


```

> The above command returns JSON structured like this:

```json
[ "object" ]
```

### HTTP Request
`GET /admin/modules`
### Responses for status codes
|200|
|----|
|object array|


# Event


Event Analyzer

## Collect event
```shell
curl "https://app.getrakam.com/event/collect" -H "write_key: mywrite_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "collection" : "str",
  "properties" : "object"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['write_key'] = 'myApiKey'

api = client.EventApi();
api.collect(org_rakam_collection_event_event_collection_http_service_collect);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("write_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.collect(orgRakamCollectionEventEventCollectionHttpServiceCollect);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("write_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->collect(org_rakam_collection_event_event_collection_http_service_collect);


```

### HTTP Request
`POST /event/collect`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|true|string||
|collection|true|string||
|properties|true|object||


### Responses for status codes
|400|
|----|
||


## Analyze events
```shell
curl "https://app.getrakam.com/query/execute" -H "read_key: myread_key" -X GET -d @- << EOF 
{
  "project" : "str",
  "query" : "str",
  "limit" : 0
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.execute(project, query, limit);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.execute(project, query, limit);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->execute(project, query, limit);


```

### HTTP Request
`GET /query/execute`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|query|false|string||
|limit|false|integer (int32)||


### Responses for status codes
|default|
|----|
||


## Analyze events
```shell
curl "https://app.getrakam.com/query/execute" -H "read_key: myread_key" -X POST -d @- << EOF 
{
  "project" : "str",
  "query" : "str",
  "limit" : 0
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")
apiClient.configuration.api_key['read_key'] = 'myApiKey'

api = client.EventApi();
api.execute(project, query, limit);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.EventApi;

ApiClient apiClient = new ApiClient();
apiClient.getAuthentication("read_key").setApiKey("myApiKey");
EventApi api = new EventApi(apiClient);
api.execute(project, query, limit);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');

$api_client->getConfig().setApiKey("read_key", "myApiKey");

$api = new Swagger\Client\EventApi($api_client);
$api->execute(project, query, limit);


```

> The above command returns JSON structured like this:

```json
{
  "metadata" : [ {
    "name" : "str",
    "type" : "STRING",
    "nullable" : true,
    "unique" : true,
    "descriptiveName" : "str",
    "description" : "str",
    "category" : "str"
  } ],
  "result" : [ [ "object" ] ],
  "error" : {
    "message" : "str",
    "sqlState" : "str",
    "errorCode" : 1
  },
  "properties" : {
    "prop" : { }
  },
  "failed" : true
}
```

### HTTP Request
`POST /query/execute`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|query|false|string||
|limit|false|integer (int32)||


### Responses for status codes
|200|
|----|
|[QueryResult](#queryresult)|


# Materialized view


Materialized view

## Create view
```shell
curl "https://app.getrakam.com/materialized-view/create" -X POST -d @- << EOF 
{
  "project" : "str",
  "name" : "str",
  "table_name" : "str",
  "query" : "str",
  "update_interval" : "str",
  "options" : {
    "prop" : { }
  }
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.MaterializedviewApi();
api.create(materialized_view);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.create(materializedView);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->create(materialized_view);


```

> The above command returns JSON structured like this:

```json
{
  "success" : true,
  "message" : "str"
}
```

### HTTP Request
`POST /materialized-view/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|table_name|false|string||
|query|false|string||
|update_interval|false|string||
|options|false|object||


### Responses for status codes
|200|400|
|----|----|
|[JsonResponse](#jsonresponse)|


## Delete materialized view
```shell
curl "https://app.getrakam.com/materialized-view/delete" -X POST -d @- << EOF 
{
  "project" : "str",
  "name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.MaterializedviewApi();
api.delete(project, name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.delete(project, name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->delete(project, name);


```

> The above command returns JSON structured like this:

```json
{
  "success" : true,
  "message" : "str"
}
```

### HTTP Request
`POST /materialized-view/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||


### Responses for status codes
|200|400|
|----|----|
|[JsonResponse](#jsonresponse)|


## Get view
```shell
curl "https://app.getrakam.com/materialized-view/get" -X POST -d @- << EOF 
{
  "project" : "str",
  "name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.MaterializedviewApi();
api.get(project, name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.get(project, name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->get(project, name);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /materialized-view/get`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||


### Responses for status codes
|200|400|
|----|----|
|object|


## List views
```shell
curl "https://app.getrakam.com/materialized-view/list" -X POST -d @- << EOF 
{
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.MaterializedviewApi();
api.list_views(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.listViews(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->listViews(project);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /materialized-view/list`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|200|400|
|----|----|
|object|


## Get schemas
```shell
curl "https://app.getrakam.com/materialized-view/schema" -X POST -d @- << EOF 
{
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.MaterializedviewApi();
api.schema(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.schema(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->schema(project);


```

> The above command returns JSON structured like this:

```json
[ "object" ]
```

### HTTP Request
`POST /materialized-view/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|200|400|
|----|----|
|object array|


## Update view
```shell
curl "https://app.getrakam.com/materialized-view/update" -X GET
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.MaterializedviewApi();
api.update();


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.MaterializedviewApi;

ApiClient apiClient = new ApiClient();

MaterializedviewApi api = new MaterializedviewApi(apiClient);
api.update();

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\MaterializedviewApi($api_client);
$api->update();


```

### HTTP Request
`GET /materialized-view/update`
### Responses for status codes
|400|
|----|
||


# Continuous query


Continuous query

## Create stream
```shell
curl "https://app.getrakam.com/continuous-query/create" -X POST -d @- << EOF 
{
  "project" : "str",
  "name" : "str",
  "query" : "str",
  "table_name" : "str",
  "collections" : [ "str" ],
  "partition_keys" : [ "str" ],
  "options" : {
    "prop" : { }
  }
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.ContinuousqueryApi();
api.create(continuous_query);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();

ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.create(continuousQuery);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->create(continuous_query);


```

> The above command returns JSON structured like this:

```json
{
  "success" : true,
  "message" : "str"
}
```

### HTTP Request
`POST /continuous-query/create`
### Body Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||
|query|false|string||
|table_name|false|string||
|collections|false|string array||
|partition_keys|false|string array||
|options|false|object||


### Responses for status codes
|200|400|
|----|----|
|[JsonResponse](#jsonresponse)|


## Delete stream
```shell
curl "https://app.getrakam.com/continuous-query/delete" -X POST -d @- << EOF 
{
  "project" : "str",
  "name" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.ContinuousqueryApi();
api.delete(project, name);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();

ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.delete(project, name);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->delete(project, name);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /continuous-query/delete`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||
|name|false|string||


### Responses for status codes
|200|400|
|----|----|
|object|


## List queries
```shell
curl "https://app.getrakam.com/continuous-query/list" -X POST -d @- << EOF 
{
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.ContinuousqueryApi();
api.list_queries(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();

ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.listQueries(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->listQueries(project);


```

> The above command returns JSON structured like this:

```json
"object"
```

### HTTP Request
`POST /continuous-query/list`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|200|400|
|----|----|
|object|


## Get query schema
```shell
curl "https://app.getrakam.com/continuous-query/schema" -X POST -d @- << EOF 
{
  "project" : "str"
}
EOF
```

```python

from ..api_client import ApiClient;
from ..configuration import Configuration

apiClient = client.ApiClient("https://app.getrakam.com")

api = client.ContinuousqueryApi();
api.schema(project);


```

```java
import io.swagger.client.api.ApiClient;
import io.swagger.client.api.ContinuousqueryApi;

ApiClient apiClient = new ApiClient();

ContinuousqueryApi api = new ContinuousqueryApi(apiClient);
api.schema(project);

```

```php


require_once('/path/to/Swagger\Client\Api');

$api_client = new Swagger\Client\ApiClient('https://app.getrakam.com');


$api = new Swagger\Client\ContinuousqueryApi($api_client);
$api->schema(project);


```

> The above command returns JSON structured like this:

```json
[ "object" ]
```

### HTTP Request
`POST /continuous-query/schema`
### Form Parameters
|Parameter|Required|Type|Description|
|----|----|----|----|
|project|false|string||


### Responses for status codes
|200|400|
|----|----|
|object array|



## Definitions
### QueryResult
|name|description|required|schema|default|
|----|----|----|----|----|
|metadata||false|[SchemaField](#schemafield) array||
|result||false|object array array||
|error||false|[QueryError](#queryerror)||
|properties||false|object||
|failed||false|boolean|false|


### User
|name|description|required|schema|default|
|----|----|----|----|----|
|project||false|string||
|id||false|object||
|properties||false|object||


### Message
|name|description|required|schema|default|
|----|----|----|----|----|
|id||false|integer (int32)||
|content||false|string||
|from_user||false|object||
|to_user||false|object||
|parentId||false|integer (int32)||
|seen||false|boolean|false|
|time||false|integer (int64)||
|project||false|string||


### MetadataResponse
|name|description|required|schema|default|
|----|----|----|----|----|
|columns||false|[SchemaField](#schemafield) array||
|identifierColumn||false|string||


### CreateUserResponse
|name|description|required|schema|default|
|----|----|----|----|----|
|identifier||false|object||


### EventFilter
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|aggregation||false|[EventFilterAggregation](#eventfilteraggregation)||
|filterExpression||false|string||


### JsonResponse
|name|description|required|schema|default|
|----|----|----|----|----|
|success||false|boolean|false|
|message||false|string||


### FunnelStep
|name|description|required|schema|default|
|----|----|----|----|----|
|collection||false|string||
|filterExpression||false|string||


### Sorting
|name|description|required|schema|default|
|----|----|----|----|----|
|column||false|string||
|order||false|enum (asc, desc)||


