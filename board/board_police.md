---
description: 신고 게시판
---

# BOARD\_POLICE

{% api-method method="post" host="https://api.tikita.ca" path="/v1/board/police" %}
{% api-method-summary %}
게시글 신고 입력 
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
{% api-method-parameter name="history" type="object" required=false %}
신고 히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="status\_flag" type="integer" required=false %}
처리유무 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_ip" type="string" required=false %}
록 아이피 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
등록일 
{% endapi-method-parameter %}

{% api-method-parameter name="content" type="string" required=false %}
신고 내용 
{% endapi-method-parameter %}

{% api-method-parameter name="register" type="string" required=false %}
작성\(신고\)자 
{% endapi-method-parameter %}

{% api-method-parameter name="content\_UUID" type="string" required=false %}
게시글/댓글 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="is\_reply" type="boolean" required=false %}
게시글 댓글 구분 
{% endapi-method-parameter %}

{% api-method-parameter name="gallery\_UUID" type="string" required=false %}
갤러리 일련번호 
{% endapi-method-parameter %}

{% api-method-parameter name="police\_UUID" type="string" required=false %}
신고 일련번호 
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
    "rstMsg": "게시글(댓글)이 신고 되었습니다다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "police_UUID" : UUID,
    "gallery_UUID" : UUID,
    "is_reply" : 0,
    "content_UUID" : UUID,
    "register" : "달봉",
    "content" : "신고합니다.",    
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "regist_ip" : "127.0.0.1",        
    "status_flag" : 1,
    "history" : ""
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/board/police/:police\_UUID" %}
{% api-method-summary %}
게시글 신고 호출 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}

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
    "police_UUID" : UUID,
    "gallery_UUID" : UUID,
    "is_reply" : 0,
    "content_UUID" : UUID,
    "register" : "달봉",
    "content" : "신고합니다.",    
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "regist_ip" : "127.0.0.1",        
    "status_flag" : 1,
    "history" : ""
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/board/police/:police\_UUID" %}
{% api-method-summary %}
게시글 신고 히스토리 등록 
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
{% api-method-parameter name="history" type="object" required=false %}
:신고 히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="status\_flag" type="string" required=false %}
처리유무 
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
    "rstMsg": "신고글에 대한 처리내용이 등록되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "status_flag" : 1,
    "history" : [{
                    "manager": "su1",
                    "regist_date":YYYY-MM-DD hh:mm:ss,
                    "memo": ""
                },
                {
                    "manager": "su2",
                    "regist_date":YYYY-MM-DD hh:mm:ss,
                    "memo": ""
                },                
                ]
}
```



