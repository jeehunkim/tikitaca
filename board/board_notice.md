---
description: 전체공지
---

# BOARD\_NOTICE

{% api-method method="post" host="https://api.tikita.ca" path="/v1/board/notice" %}
{% api-method-summary %}
전체공지 입력 
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
{% api-method-parameter name="view\_flag" type="string" required=false %}
상태 flag 게시/보류/삭제 
{% endapi-method-parameter %}

{% api-method-parameter name="view\_count" type="string" required=false %}
조회수 
{% endapi-method-parameter %}

{% api-method-parameter name="modify\_date" type="string" required=false %}
수정일 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
등록일 
{% endapi-method-parameter %}

{% api-method-parameter name="register" type="string" required=false %}
등록자 
{% endapi-method-parameter %}

{% api-method-parameter name="notice\_content" type="string" required=false %}
내용 
{% endapi-method-parameter %}

{% api-method-parameter name="notice\_title" type="string" required=false %}
제목 
{% endapi-method-parameter %}

{% api-method-parameter name="notice\_UUID" type="string" required=false %}
공지 일련번호 
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
    "rstMsg": "공지글 등록 되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "notice_UUID": UUID,
    "notice_title": "공지제목",
    "notice_content": "공지내용",
    "register": "작성자",    
    "regist_date": "YYYY-MM-DD hh:mm:ss",
    "modify_date": "YYYY-MM-DD hh:mm:ss",
    "view_count" : 10,
    "view_flag" : 0
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/board/notice/:notice\_UUID" %}
{% api-method-summary %}
전체공지 수정 
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
{% api-method-parameter name="view\_flag" type="string" required=false %}
상태 flag 게시/보류/삭제 
{% endapi-method-parameter %}

{% api-method-parameter name="modify\_date" type="string" required=false %}
수정일 
{% endapi-method-parameter %}

{% api-method-parameter name="notice\_content" type="string" required=false %}
내용 
{% endapi-method-parameter %}

{% api-method-parameter name="notice\_title" type="string" required=false %}
제목 
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
    "rstMsg": "공지글이 수 되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{  
    "notice_title": "공지제목",
    "notice_content": "공지내용",
    "modify_date": "YYYY-MM-DD hh:mm:ss",
    "view_flag" : 0
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/board/notice/:notice\_UUID" %}
{% api-method-summary %}
공지글 호출 
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
    "rstCode":200,
    "notice_UUID": UUID,
    "notice_title": "공지제목",
    "notice_content": "공지내용",
    "register": "작성자",    
    "regist_date": "YYYY-MM-DD hh:mm:ss",
    "modify_date": "YYYY-MM-DD hh:mm:ss",
    "view_count" : 10,
    "view_flag" : 0
}

/*
    sql update view count 
*/
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

