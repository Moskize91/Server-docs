# 场景

{% api-method method="get" host="https://shunt-api.netless.link" path="/v5/rooms/:uuid/scenes" %}
{% api-method-summary %}
获取场景地址列表
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
SDK Token 或 Room Token（只读以上）
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="sceneDir" type="string" required=false %}
返回哪个场景组下的场景列表（不填则返回所有场景）
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
    "/init",
    "/6f026653989b4439b32a6899e7d32fed",
    "/b3a423f8caaa4ff688c0e395431776a5"
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/rooms/:uuid/scenes" %}
{% api-method-summary %}
插入新场景
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
SDK Token 或 Room Token（可写权限以上）
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="scenes" type="array" required=true %}
由 Scene 组成的数组，标明要插入的场景的数据结构。
{% endapi-method-parameter %}

{% api-method-parameter name="path" type="string" required=true %}
新场景应该插入到那个场景组之中  
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```typescript
// 插入场景的描述对象
type Scene = {
    name: string; // 场景名
    ppt?: {
        src: string; // 背景图片的 URL 地址
        width: number; // 背景图片的宽
        height: number; // 背景图片的高
    };
};
```

{% api-method method="patch" host="https://shunt-api.netless.link" path="/v5/rooms/:uuid/scene-state" %}
{% api-method-summary %}
场景跳转
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
SDK Token 或 Room Token（可写以上权限）
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="scenePath" type="string" required=true %}
切换到的场景地址
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "currentScenePath": [
        "/init"
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

