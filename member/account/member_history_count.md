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
{% api-method-parameter name="STOPED\_COUNT" type="integer" required=false %}
:정지횟수 
{% endapi-method-parameter %}

{% api-method-parameter name="WARNING\_COUNT" type="integer" required=false %}
:경고횟수 
{% endapi-method-parameter %}

{% api-method-parameter name="HOT\_COUNT" type="integer" required=false %}
:핫게/롱런 등 count 
{% endapi-method-parameter %}

{% api-method-parameter name="REPLY" type="object" required=false %}
:작성/삭제/좋아요 등 count 
{% endapi-method-parameter %}

{% api-method-parameter name="PUBLISH" type="object" required=false %}
작성/삭제/좋아요 등 count 
{% endapi-method-parameter %}

{% api-method-parameter name="MEMBER\_UUID" type="string" required=true %}
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
    "UUID": UUID,
    "MEMBER_UUID": "b948e2be-9b7a-4963-bcff-34cee7c2e38a",
    "PUBLISH" : {
                    "write_count" : 0,
                    "delete_count" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "REPLY" : {
                    "write_count" : 0,
                    "delete_count" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "WARNING_COUNT" : 1,
    "STOPED_COUNT" : 0
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/member/history-count/:MEMBER\_UUID" %}
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
{% api-method-parameter name="DETAIL\_COUNT" type="string" required=false %}
write\_count,delete\_count...
{% endapi-method-parameter %}

{% api-method-parameter name="KIND\_OF\_COUNT" type="string" required=false %}
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
    "KIND_OF_COUNT": "PUBLISH",
    "DETAIL_COUNT" : "delete_count"
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/member/history-count/:MEMBER\_UUID" %}
{% api-method-summary %}
:게시글 카운트 정보 호출 
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
    "rstCode": 200,
    "UUID": UUID,
    "MEMBER_UUID": "b948e2be-9b7a-4963-bcff-34cee7c2e38a",
    "PUBLISH" : {
                    "write_count" : 0,
                    "delete_count" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "REPLY" : {
                    "write_count" : 0,
                    "delete_count" : 0,
                    "save_good" : 0,
                    "save_bad" : 0,
                    "gave_good" : 0,
                    "gave_bad" : 0,
                    "admin_del" : 0,
                    },
    "WARNING_COUNT" : 1,
    "STOPED_COUNT" : 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/member/history-count/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```



