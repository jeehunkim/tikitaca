---
description: 게시글 해시태그
---

# GALLERY\_HASHTAG

{% api-method method="post" host="https://api.tikita.ca" path="/v1/gallery/hash-tag" %}
{% api-method-summary %}
게시글 해시태그 입력 
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
{% api-method-parameter name="regist\_date" type="string" required=false %}
등록일 
{% endapi-method-parameter %}

{% api-method-parameter name="keyword" type="object" required=true %}
hashtag
{% endapi-method-parameter %}

{% api-method-parameter name="content\_uuid" type="string" required=true %}
게시글 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_uuid" type="string" required=true %}
갤러리 일련번호 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
HTTP/1.1 201 Created
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "gallery_uuid": UUID,
    "content_uuid": UUID,
    "keyword": ["연예인","여자","아이"],
    "write_date": YYYY-MM-DD hh:mm:ss
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/gallery/hash-tag/:keyword" %}
{% api-method-summary %}
게시글 해시태그 검색 
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
[   
    {
        "gallery_uuid":"",
        "content_uuid":"UUID"
    },
    {
        "gallery_uuid":"",
        "content_uuid":"UUID"
    }
] 
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/gallery/hash-tag/연예
```

