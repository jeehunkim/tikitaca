---
description: 추천/비추
---

# GALLERY\_GOODBAD

{% api-method method="post" host="https://api.tikita.ca" path="/v1/gallery/good-bad" %}
{% api-method-summary %}
추천/비추 입력 
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="regist\_ip" type="string" required=false %}
등록 아이피 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
등록일 
{% endapi-method-parameter %}

{% api-method-parameter name="action\_flag" type="boolean" required=true %}
추천/비추 flag
{% endapi-method-parameter %}

{% api-method-parameter name="member\_uuid" type="string" required=true %}
회원 고유 키값 
{% endapi-method-parameter %}

{% api-method-parameter name="content\_uuid" type="string" required=true %}
게시글/댓글 UUID
{% endapi-method-parameter %}

{% api-method-parameter name="is\_reply" type="boolean" required=true %}
게시글/댓글 구분 
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

/*
    정상일 경우
    gallery_board의 action_count 업데이트
    action_count.like(bad) 카운트 +1
*/
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

> 기본키

{% tabs %}
{% tab title="is\_reply" %}
| default | 0 |
| :--- | :--- |
| 게시글  | 0 |
| 댓글  | 1 |
{% endtab %}

{% tab title="action\_flag" %}
| default | 1 |
| :--- | :--- |
| 비추  | 0 |
| 추천  | 1 |
{% endtab %}
{% endtabs %}

```text
{
    "gallery_uuid": UUID,
    "is_reply": 0,
    "content_uuid": UUID,
    "member_uuid": UUID,
    "action_flag": 0,
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "regist_ip": "127.0.0.1"
}
```

