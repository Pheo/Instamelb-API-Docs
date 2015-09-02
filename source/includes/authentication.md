# Authentication

Basic HTTP Authentication is used in the Instamelb API. 
Credentials are passed as username:password in all routes.
Server is stateless, we DO NOT maintain session information.
Hence, username:password must be passed at every route.

> Authorization is as such:

```shell
curl -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/
```

```java
N/A
```

<aside class="notice">
You must replace <code>USERNAME</code> and <code>PASSWORD</code> with your respective credentials.
</aside>

## Login

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/login
```

```java
N/A
```

> On successful authentication, the above command returns JSON structured:

```json
{
    "authenticated": true
}
```

Login route is used to verify credentials of user. Usage is not strictly necessary, but is helpful for creation of a login screen.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/login`


## Registration

```shell
curl -H "Content-Type: application/json" -X POST \
    -d '{
            "username": "NEW_USERNAME",
            "email": "USER@NEW_EMAIL.COM",
            "password": "NEW_PASSWORD"
        }' \
    http://instamelb.pinkpineapple.me/register
```

```java
N/A
```

> On successful registration, the above command returns JSON structured like this:

```json
{
    "registered": true
}
```

> In event of failed registration, we return:

```json
{
    "registered": false,
    "error": "Email already registered"
}
```

This endpoint registers a new user in the system.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/register`

### Body Parameters
Parameter | Type | Description
--------- | ---- | ------
username | String | Username of account.
email | String | Email to be registered.
password | String | Password of account.

