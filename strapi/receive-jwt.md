# token

{% api-method method="post" host="https://api.tikita.ca" path=":1337/auth/local" %}
{% api-method-summary %}
- 인증토큰 발급 
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
password
{% endapi-method-parameter %}

{% api-method-parameter name="identifier" type="string" required=true %}
ID
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
    "jwt": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVmNTVlMzJhYWIyNGM3MWMzYzFiZjM5MSIsImlhdCI6MTU5OTYyNDAzMiwiZXhwIjoxNjAyMjE2MDMyfQ.RG45leGEZ-5WrcQ8ESCySyeRNtUMP_ygBm1kNx1cVDA",
    "user": {
        "confirmed": true,
        "blocked": false,
        "_id": "5f55e32aab24c71c3c1bf391",
        "username": "user2",
        "email": "jh.kim2@theenm.com",
        "provider": "local",
        "createdAt": "2020-09-07T07:37:14.749Z",
        "updatedAt": "2020-09-07T07:37:14.756Z",
        "__v": 0,
        "created_by": {
            "_id": "5f5599d0eef7bf517c0dc157",
            "username": null,
            "firstname": "jeehun",
            "lastname": "kim",
            "createdAt": "2020-09-07T02:24:16.250Z",
            "updatedAt": "2020-09-07T02:24:16.260Z",
            "__v": 0,
            "id": "5f5599d0eef7bf517c0dc157"
        },
        "role": {
            "_id": "5f5597e9bf84d42da88a1dda",
            "name": "Authenticated",
            "description": "Default role given to authenticated user.",
            "type": "authenticated",
            "createdAt": "2020-09-07T02:16:09.522Z",
            "updatedAt": "2020-09-09T02:53:04.711Z",
            "__v": 0,
            "id": "5f5597e9bf84d42da88a1dda"
        },
        "updated_by": {
            "_id": "5f5599d0eef7bf517c0dc157",
            "username": null,
            "firstname": "jeehun",
            "lastname": "kim",
            "createdAt": "2020-09-07T02:24:16.250Z",
            "updatedAt": "2020-09-07T02:24:16.260Z",
            "__v": 0,
            "id": "5f5599d0eef7bf517c0dc157"
        },
        "posts": [
            {
                "_id": "5f5746108fcb13674c9ae6f2",
                "title": "test2131",
                "content": "content",
                "createdAt": "2020-09-08T08:51:28.960Z",
                "updatedAt": "2020-09-08T08:51:28.968Z",
                "__v": 0,
                "board": "5f571690b149ff6ba840a6dd",
                "user": "5f55e32aab24c71c3c1bf391",
                "id": "5f5746108fcb13674c9ae6f2"
            }
        ],
        "comments": [],
        "articles": [
            {
                "_id": "5f5844c0347b6bba48ee8b1d",
                "title": "user1ArticleTitle3",
                "content": "user1ArticleTitle1",
                "createdAt": "2020-09-09T02:58:08.835Z",
                "updatedAt": "2020-09-09T02:58:08.842Z",
                "__v": 0,
                "author": "5f55e32aab24c71c3c1bf391",
                "id": "5f5844c0347b6bba48ee8b1d"
            },
            {
                "_id": "5f5844e9347b6bba48ee8b1e",
                "title": "user1ArticleTitle3",
                "content": "user1ArticleTitle1",
                "createdAt": "2020-09-09T02:58:49.512Z",
                "updatedAt": "2020-09-09T02:58:49.517Z",
                "__v": 0,
                "author": "5f55e32aab24c71c3c1bf391",
                "id": "5f5844e9347b6bba48ee8b1e"
            }
        ],
        "id": "5f55e32aab24c71c3c1bf391"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



