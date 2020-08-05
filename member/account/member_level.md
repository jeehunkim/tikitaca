---
description: 회원 등급
---

# MEMBER\_LEVEL

{% api-method method="post" host="https://api.tikita.ca" path="/v1/member/level" %}
{% api-method-summary %}
회원 등급 등록 
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="is\_use" type="integer" required=true %}
:사용 유무 
{% endapi-method-parameter %}

{% api-method-parameter name="level\_name" type="string" required=true %}
레벨명 
{% endapi-method-parameter %}

{% api-method-parameter name="level\_value" type="integer" required=true %}
레벨 값 
{% endapi-method-parameter %}

{% api-method-parameter name="level\_uuid" type="string" required=true %}
례벨 고유값 
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
    "rstCode": 200
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "level_uuid": UUID,
    "level_value": 0,
    "level_name": "고인물 ",
    "is_use": 0
}
```

{% api-method method="put" host="https://api.tikita.ca" path="/v1/member/level/:level\_uuid" %}
{% api-method-summary %}
회원등급 수정/삭제 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="is\_use" type="integer" required=false %}
사용유무 
{% endapi-method-parameter %}

{% api-method-parameter name="level\_name" type="string" required=false %}
레벨명 
{% endapi-method-parameter %}

{% api-method-parameter name="level\_value" type="integer" required=false %}
레벨 값  
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": 200,
    "rstMsg": "수정되었습니다"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "level_value": 0,
    "level_name": "고인물 ",
    "is_use": 0
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/member/level/:level\_uuid" %}
{% api-method-summary %}
회원등급 정보 호출 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authentication" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "level_uuid": UUID,
    "level_value": 0,
    "level_name": "고인물 ",
    "is_use": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



