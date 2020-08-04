---
description: '1:1 문의'
---

# BOARD\_INQUIRY

{% api-method method="post" host="https://api.tikita.ca" path="/v1/board/inquiry" %}
{% api-method-summary %}
1:1문의글 작성 
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
{% api-method-parameter name="answer\_history" type="object" required=false %}
답변 히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_flag" type="integer" required=false %}
처리상태 처리중/완료/보류
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_ip" type="string" required=false %}
등록 아이피 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=false %}
작성일 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_writer" type="string" required=false %}
작성자 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_file" type="string" required=false %}
첨부파일 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_content" type="string" required=false %}
문의글 내용 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_title" type="string" required=false %}
문의글 제목 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_kind" type="string" required=false %}
문의글 유형 어드민 등록된 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_UUID" type="string" required=false %}
문의글 일련번호 
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
    "rstMsg": "1:1 문의글이 등록되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "inquiry_UUID" : "과금관련 ",
    "inquiry_kind" : "SU",
    "inquiry_title" : "SU",
    "inquiry_content" : "SU",
    "inquiry_file" : "SU",
    "inquiry_writer" : "SU",    
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "regist_ip" : "SU",        
    "inquiry_flag" : 1,
    "answer_history" : ""
}
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/board/inquiry/:inquiry\_UUID" %}
{% api-method-summary %}
1:1 문의글 호출 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=false %}

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
    "inquiry_UUID" : "과금관련 ",
    "inquiry_kind" : "SU",
    "inquiry_title" : "SU",
    "inquiry_content" : "SU",
    "inquiry_file" : "SU",
    "inquiry_writer" : "SU",    
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "regist_ip" : "SU",        
    "inquiry_flag" : 1,
    "answer_history" : ""
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/board/inquiry/:inquiry\_UUID" %}
{% api-method-summary %}
1:1문의글 답글 등록 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authentication" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="answer\_history" type="object" required=false %}
답변히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="inquiry\_flag" type="integer" required=false %}
처리상태 처리중/완료/보류 
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
    "rstMsg": "문의글에 대한 답변이 등록되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "inquiry_flag" : 1,
    "answer_history" : [{
                    "answer_manager" : "su",
                    "answer_date" : "YYYY-MM-DD hh:mm:ss,",
                    "answer_content" : "답변내용1"
                },
                {
                    "answer_manager" : "su1",
                    "answer_date" : "YYYY-MM-DD hh:mm:ss,",
                    "answer_content" : "답변내용2"
                }                
                ]
}
```

