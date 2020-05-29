# 房间

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/rooms" %}
{% api-method-summary %}
创建房间
{% endapi-method-summary %}

{% api-method-description %}
​
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
 SDK Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=false %}
房间名字（最长 2048）
{% endapi-method-parameter %}

{% api-method-parameter name="isRecord" type="boolean" required=false %}
是否开启录制
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
可写人数上限​，若传 0，标示没有限制
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
创建成功，返回房间描述对象。
{% endapi-method-response-example-description %}

```javascript
{
    "uuid": "d07bcaf0a17911ea9d7e23232cddf42d",
    "name": "my first room",
    "teamUUID": "177",
    "isRecord": false,
    "isBan": false,
    "limit": 0,
    "createdAt": "2020-05-29T06:58:35.085Z"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://shunt-api.netless.link" path="/v5/rooms/:uuid" %}
{% api-method-summary %}
获取房间信息
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
房间的 UUID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
SDK Token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "uuid": "d07bcaf0a17911ea9d7e23232cddf42d",
    "name": "my first room",
    "teamUUID": "177",
    "isRecord": false,
    "isBan": false,
    "createdAt": "2020-05-29T06:58:35.085Z",
    "limit": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://shunt-api.netless.link" path="/v5/rooms" %}
{% api-method-summary %}
获取房间列表
{% endapi-method-summary %}

{% api-method-description %}
获取公司账号下的所有的房间，以 UUID 的自然顺序排列。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
SDK Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="beginUUID" type="string" required=false %}
列表从哪个房间开始（指定 UUID）
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="integer" required=false %}
返回列表的最大长度
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
    {
        "uuid": "37875f5089c611eaa629dbb375b5adfc",
        "name": "",
        "teamUUID": "177",
        "isRecord": true,
        "isBan": false,
        "createdAt": "2020-04-29T03:05:01.716Z",
        "limit": 0
    },
    {
        "uuid": "3787fb9089c611eaa629dbb375b5adfc",
        "name": "",
        "teamUUID": "177",
        "isRecord": true,
        "isBan": false,
        "createdAt": "2020-04-29T03:05:01.717Z",
        "limit": 0
    }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="https://shunt-api.netless.link" path="/v5/rooms/:uuid" %}
{% api-method-summary %}
封禁房间
{% endapi-method-summary %}

{% api-method-description %}
封禁后，房间里的人全部会被踢出，之后任何人都无法加入。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=false %}
SDK Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="isBan" type="boolean" required=true %}
设置 true 标示封禁，设置 false 标示取消封禁
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "uuid": "d07bcaf0a17911ea9d7e23232cddf42d",
    "name": "my first room",
    "teamUUID": "177",
    "isRecord": false,
    "isBan": true,
    "limit": 0,
    "createdAt": "2020-05-29T06:58:35.085Z"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

