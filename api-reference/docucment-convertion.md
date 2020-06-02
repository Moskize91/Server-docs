# 文档转换

**在调用以下 api 之前，请确保您已经在 console 平台上开通了 文档转网页 或是 文档转图片 服务**

{% api-method method="post" host="https://shunt-api.netless.link" path="/v5/services/conversion/tasks" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
当请求中的 type 为 dynamic 时将调用 文档转网页（动态文档转换）服务，当 type 为 static 时将调用 文档转图片（静态文档转换）服务，请确保调用时对应服务已开通，否则 api 将会报错
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
SDK Token （只读以上）
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="resource" type="string" required=true %}
转换任务源文件 url
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
转换任务类型，枚举：dynamic, static
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "uuid": "2fa009xxxxxxxxxxxxxxxxxca93da2ad",  // task uuid
    "type": "static",  // task 类型，枚举：dynamic, static
    "status": "Waiting"  // task 状态，枚举：Waiting, Converting, Finished, Fail
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://shunt-api.netless.link" path="/v5/services/conversion/tasks/:uuid" %}
{% api-method-summary %}
查询任务转换进度
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
Task uuid
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
Task Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="type" type="string" required=true %}
转换任务类型，枚举：dynamic, static
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
动态转换任务进度中的 conversionFileUrl 字段是以 pptx:// 协议开头的，需要将该 url 传入 sdk 中进行解析才可以正常在网页中展示
{% endapi-method-response-example-description %}

```
{
    "uuid": "2fa009xxxxxxxxxxxxxxxxxca93da2ad",  // task uuid
    "type": "static",  // task 类型，枚举：dynamic, static
    "status": "Waiting",  // task 状态，枚举：Waiting, Converting, Finished, Fail
    "failedReason": "",  // 任务失败后的原因
    "progress": {
        "totalPageSize": 10,  // 转换文档总页数
        "convertedPageSize": 3,  // 已经转换完成的页数
        "convertedPercentage": 30,  // 转换进度百分比
        "convertedFileList": [{  // 转换结果列表
            "width": 1024,  // 当页跨度
            "height": 960,  // 当页高度
            "conversionFileUrl": "xxxx://xxxx.xxx.xx/xxxx.xxx" // 转换结果文件地址
        },{...}]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

