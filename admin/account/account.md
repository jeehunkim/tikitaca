---
description: 관리자 계정
---

# ADMIN\_ACCOUNT

{% api-method method="post" host="https://api.tikita.ca" path="/v1/admin/member/account" %}
{% api-method-summary %}
관리자 계정 정보 등록 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
jwt
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="history" type="object" required=false %}
계정 히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_status" type="integer" required=true %}
계정 상태  - 대기/정상/보류/삭제 
{% endapi-method-parameter %}

{% api-method-parameter name="regist\_date" type="string" required=true %}
계정 생성일 
{% endapi-method-parameter %}

{% api-method-parameter name="group\_code" type="string" required=true %}
계정 소속코드 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_name" type="string" required=false %}
계정 이름 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_level" type="string" required=true %}
계정 등급코드 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_pwd" type="string" required=true %}
계정 비밀번호 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_ID" type="string" required=true %}
계정 아이디 
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

> 기본키

| account\_status | 0 |
| :--- | :--- |
| 대기  | 0 |
| 정상  | 1 |
| 보류  | 2 |
| 삭제  | 3 |

```text
{
    "account_uuid": UUID,
    "account_ID": "nob98",
    "account_pwd": "1234",
    "account_level": "SU",
    "account_name" : "김지훈",
    "group_code" : "P-00001",
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "account_status" : 1,
    "history" : {
                    "history_memo" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }                
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/member/account/:account\_uuid" %}
{% api-method-summary %}
관리자 등록정보 수정 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
jwt
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="group\_code" type="string" required=false %}
계정 소속 코드 
{% endapi-method-parameter %}

{% api-method-parameter name="history" type="object" required=false %}
계정 히스토리 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_status" type="integer" required=false %}
계정 상태 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_name" type="string" required=false %}
계정 이름 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_level" type="string" required=false %}
계정 등급코드 
{% endapi-method-parameter %}

{% api-method-parameter name="account\_pwd" type="string" required=false %}
계정 비밀번호 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
HTTP/1.1 200 OK
{
  "rst_msg": "계정보가 수정되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
{
    "account_pwd": "1234",
    "account_level": "SU",
    "account_name" : "김지훈",
    "account_status" : 0,
    "history" : {
                    "history_memo" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }                
}
```

{% api-method method="patch" host="https://api.tikita.ca" path="/v1/admin/member/account/:account\_uuid" %}
{% api-method-summary %}
관리자 등록정보 삭제 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
jwt
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="account\_status" type="integer" required=true %}
계정 상태 
{% endapi-method-parameter %}

{% api-method-parameter name="history" type="object" required=true %}
계정 히스토리 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
HTTP/1.1 200 OK
{
  "rst_msg": "계정정보가 삭되었습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
https://api.tikita.ca/v1/admin/member/account/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

```text
{
    "account_status": 3,
    "history" : {
                    "history_memo" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }
}
```

```text
/* in case sql */
update "account" set account_status = 3 where UUID = UUID
update "account" set history.history_memo = 0, ... where UUID = UUID
```

{% api-method method="get" host="https://api.tikita.ca" path="/v1/admin/member/account/:account\_uuid" %}
{% api-method-summary %}
관리자 등록정보 호출 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
jwt
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
/* example */
HTTP/1.1 200 OK

{
    "account_ID": "nob98",
    "account_pwd": "1234",
    "account_level": "SU",
    "account_name" : "김지훈",
    "account_group_code" : "P-00001",
    "regist_date" : YYYY-MM-DD hh:mm:ss,
    "account_status" : 1,
    "history" : [{
                    "history_memo" : 1,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                },
                {
                    "history_memo" : 0,
                    "history_date" : YYYY-MM-DD hh:mm:ss,
                    "history_manager" : "SU"
                }]              

}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```text
/* 관리자 전체 리스트 */
https://api.tikita.ca/v1/admin/member/account

/* 관리자 개 리스트 */
https://api.tikita.ca/v1/admin/member/account/b948e2be-9b7a-4963-bcff-34cee7c2e38a
```

