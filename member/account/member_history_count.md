---
description: 게시글/댓글/경고 카운트
---

# MEMBER\_HISTORY\_COUNT

{% api-method method="post" host="https://api.tikita.ca" path="/v1/member/history-count" %}
{% api-method-summary %}
게시글/댓글/핫게\(롱런\)/신고/정지 카운트 입력 
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
{% api-method-parameter name="stoped" type="integer" required=false %}
:정지횟수 
{% endapi-method-parameter %}

{% api-method-parameter name="warning" type="integer" required=false %}
:경고횟수 
{% endapi-method-parameter %}

{% api-method-parameter name="hot" type="integer" required=false %}
:핫게/롱런 등 count 
{% endapi-method-parameter %}

{% api-method-parameter name="reply" type="object" required=false %}
:작성/삭제/좋아요 등 count 
{% endapi-method-parameter %}

{% api-method-parameter name="publish" type="object" required=false %}
작성/삭제/좋아요 등 count 
{% endapi-method-parameter %}

{% api-method-parameter name="member\_uuid" type="string" required=true %}
:회원 고유 UUID 
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
    "rstMsg": "게시글 카운트 정보가 입력되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "member_uuid": "b948e2be-9b7a-4963-bcff-34cee7c2e38a",
    "publish" : {
                    "write" : 0,
                    "delete" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "reply" : {
                    "write" : 0,
                    "delete" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "warning" : 1,
    "stoped" : 0
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/member/history-count/:member\_uuid" %}
{% api-method-summary %}
게시글 카운트 업데이트 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="detail" type="string" required=false %}
write\_count,delete\_count...
{% endapi-method-parameter %}

{% api-method-parameter name="kind" type="string" required=false %}
PUBLISH/REPLY...
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": "200",
    "rstMsg": "게시글 카운트 정보가 수되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "kind": "publish",
    "detail" : "write"
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/member/history-count/:member\_uuid" %}
{% api-method-summary %}
게시글 카운트 정보 호출 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=false %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "member_uuid": "b948e2be-9b7a-4963-bcff-34cee7c2e38a",
    "publish" : {
                    "write" : 0,
                    "delete" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "reply" : {
                    "write" : 0,
                    "delete" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "warning" : 1,
    "stoped" : 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/member/history-count/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```



