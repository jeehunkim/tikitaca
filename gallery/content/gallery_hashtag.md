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

{% api-method-parameter name="keyword" type="object" required=false %}
hashtag
{% endapi-method-parameter %}

{% api-method-parameter name="content\_UUID" type="string" required=false %}
게시글 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_UUID" type="string" required=false %}
갤러리 일련번호 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "rstCode": "200",
    "rstMsg": "해시태그 등록 되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "gallery_UUID": UUID,
    "content_UUID": UUID,
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
{
    "rstCode": "200",
    "rstList":[   
                   {
                   "gallery_UUID":"",
                   "content_UUID":"UUID"
                   },
                   {
                   "gallery_UUID":"",
                   "content_UUID":"UUID"
                   }
               ]                
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/gallery/hash-tag/연예
```

