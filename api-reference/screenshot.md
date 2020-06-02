# 截图

**在调用以下 api 之前，请确保您已经在 console 平台上开通了截图服务功能**

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/rooms/:uuid/screenshots" %}
{% api-method-summary %}
获取指定场景截图 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter type="string" name="uuid" required=true %}
房间的 UUID
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter type="string" name="token" required=true %}
SDK Token 或 Room Token（只读以上）
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="width" type="number" required=true %}
获取截图的宽度，单位为像素
{% endapi-method-parameter %}

{% api-method-parameter name="height" type="number" required=true %}
获取截图的高度，单位为像素
{% endapi-method-parameter %}

{% api-method-parameter name="path" type="string" %}
需要截图的场景路径，以“/”开头，如果不传，默认获取"/init"场景的截图 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
创建截图成功 
{% endapi-method-response-example-description %}

```
{
    "url": "http://xxxxxx.com/xxx/xxx.png",
    "key": "xxx/xxx.png",        // 封面图片存放在存储服务中的 key
    "bucket": "your-bucket",     // 封面图片存放在存储服务中的 bucket
    "region": "your-region"      // 封面图片存放在存储服务中的 region
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/rooms/:uuid/screenshot-list" %}
{% api-method-summary %}
获取指定场景路径下的场景截图
{% endapi-method-summary %}

{% api-method-description %}
该 api 只会返回假设用户有场景列表:  
  - /physics/quantum-mechanics/first-chapter  
  - /physics/newtonian-mechanics  
  - /english  
那么在用户传入 scenePath = "/physics" 后，该接口只会返回  
  - /physics/newtonian-mechanics  
  - /physics/relativity-theory  
这两条截图数据。同样，在用户传入 scenePath = "/" 后，该接口只会返回  
  - /english
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

{% api-method-body-parameters %}
{% api-method-parameter name="width" type="number" required=true %}
获取截图的宽度，单位为像素
{% endapi-method-parameter %}

{% api-method-parameter name="height" type="number" required=true %}
获取截图的高度，单位为像素
{% endapi-method-parameter %}

{% api-method-parameter name="path" required=true type="string" %}
需要截图的场景路径，以“/”开头
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
[{
    "url": "http://xxxxxx.com/xxx/xxx.png",
    "key": "xxx/xxx.png",        // 封面图片存放在存储服务中的 key
    "bucket": "your-bucket",     // 封面图片存放在存储服务中的 bucket
    "region": "your-region"      // 封面图片存放在存储服务中的 region
},{
    ...
}]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



