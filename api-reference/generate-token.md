# 生成 Token

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/tokens/teams" %}
{% api-method-summary %}
生成 SDK Token
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="accessKey" type="string" required=true %}
Access Key
{% endapi-method-parameter %}

{% api-method-parameter name="secretAccessKey" type="string" required=true %}
Secret Access Key
{% endapi-method-parameter %}

{% api-method-parameter name="lifespan" type="integer" required=true %}
有效时间（ms）设为 0 表示永久有效
{% endapi-method-parameter %}

{% api-method-parameter name="role" type="string" required=true %}
权限角色，可取 admin、writer、reader
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
"NETLESSSDK_YWs9MzRsNzBoQ2dINFkxZ1BCYWpqbU5Ick9qM3FGeDFMWE5GY3R0Jm5vbmNlPTE1OTA3MzkyOTgwOTUwMCZyb2xlPTAmc2lnPTY0NGY5ODQwMDMzZDA1MjcxNWE2NDc0MWQyMTExNzFhMGY0NWQ2YzZhZjZlZTc2YTA4YjNkNjFmZDc1NTJkMDM"
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/tokens/rooms/:uuid" %}
{% api-method-summary %}
生成 Room Token
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

{% api-method-body-parameters %}
{% api-method-parameter name="ak" type="string" required=false %}
Access Key
{% endapi-method-parameter %}

{% api-method-parameter name="lifespan" type="string" required=true %}
有效时间（ms）0 标示永久有效
{% endapi-method-parameter %}

{% api-method-parameter name="role" type="string" required=true %}
权限角色，可取 admin、writer、reader
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
"NETLESSROOM_YWs9eGQxSE5UY2h3REozaG44M1V1SmZ4OE15cWxmOTlkSU9WRUVzJm5vbmNlPTE1OTA3Mzk3NjUxNjQwMCZyb2xlPTAmc2lnPWNmZWUwMmEzYWE5NjY5NzVmNGJhZTQwMjJiODcxYzg4MzQ3MTIwMWRmYzI2MThjMjRhOTg3ODFmMTVkNmNkYWQmdXVpZD0xNzFmZWYxMDdlMDAxMWVhYTU1ZTZkOWE0ZTA3OGRhNA"
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/tokens/tasks/:uuid" %}
{% api-method-summary %}
生成 Task Token
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
转换任务的 UUID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
SDK Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="ak" type="string" required=false %}
Access Key
{% endapi-method-parameter %}

{% api-method-parameter name="lifespan" type="integer" required=true %}
有效时间（ms）0 标示永久有效
{% endapi-method-parameter %}

{% api-method-parameter name="role" type="string" required=true %}
权限角色，可取 admin、writer、reader
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
"NETLESSTASK_YWs9eGQxSE5UY2h3REozaG44M1V1SmZ4OE15cWxmOTlkSU9WRUVzJm5vbmNlPTE1OTA3NDAyMjg4ODEwMCZyb2xlPTAmc2lnPTUyMTY0ZjRlZmE5NzViYWJlNjgyOWU0ZDE5MGUzNDhhZjBiYzY5N2Q3NWM3ZThmNjFjNzExZTJjMjYwODI3ZjImdXVpZD0wMGQ0ZTAxNWRmNGM0ODg0ODBjM2Y4YTI0ZDA1M2ViMQ"
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



