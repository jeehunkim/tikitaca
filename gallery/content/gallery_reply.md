---
description: 게시물 댓글
---

# GALLERY\_REPLY

{% api-method method="post" host="https://api.tikita.ca" path="/v1/gallery/reply/:gallery\_UUID/:content\_UUID" %}
{% api-method-summary %}
Get Cakes
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
{% api-method-parameter name="reply\_status" type="integer" required=false %}
:리플 상태값\(정상/삭제/관리자 삭제\)
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_ip" type="string" required=false %}
작성 IP
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_m\_date" type="string" required=false %}
수정일 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_w\_date" type="string" required=false %}
작성일 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_content" type="string" required=false %}
리플내용 
{% endapi-method-parameter %}

{% api-method-parameter name="vs\_reply" type="string" required=false %}
VS갤러리의 1:1일 경우 찬/반/중립 선택시 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_writer" type="string" required=false %}
작성자 
{% endapi-method-parameter %}

{% api-method-parameter name="action\_count" type="object" required=false %}
좋아요/싫어요/신고 count 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_depth" type="string" required=false %}
대댓을 위한 순서 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_group\_sort" type="string" required=false %}
동일한 게시글 일련번호에 대한 순서 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_group\_id" type="string" required=false %}
게시글 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="reply\_UUID" type="string" required=false %}
댓글 일련번호 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



