---
description: VS 갤러리 전용 투표데이터
---

# GALLERY\_POLL

{% api-method method="post" host="https://api.tikita.ca" path="/v1/gallery/poll/:gallery\_UUID/:content\_UUID" %}
{% api-method-summary %}
투표 입력 
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
투표 일시 
{% endapi-method-parameter %}

{% api-method-parameter name="poll\_number" type="integer" required=true %}
투표번호 
{% endapi-method-parameter %}

{% api-method-parameter name="MEMBER\_UUID" type="string" required=true %}
회원 고유값 
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
    "rstMsg": "투표가 정상적으로 등록되었습니다. "
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "MEMBER_UUID": UUID,
    "poll_number": 3,
    "regist_date": YYYY-MM-DD hh:mm:ss,
    "regist_ip": "127.0.0.1"
}
/*
    정상일 경우
    gallery_board의 vs전용 poll count update
    only_vs.vs_poll_count 의 3번 값에 해당하는 카운트 +1
*/
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/gallery/poll/:gallery\_UUID/:content\_UUID" %}
{% api-method-summary %}
투표 결과 
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "rstCode": 200,
    "total_poll_count": 100,
    "detail_poll_count":{
                            "poll_number_1": 30,
                            "poll_number_2": 40,
                            "poll_number_3": 20,                            
                            "poll_number_4": 10
                        }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/gallery/poll/b948e2be-9b7a-4963-bcff-34cee7c2e38a/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

