# Users

Users are entities that are able to post, comment and like photos

## Get User Profile

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/1
```

```java
N/A
```

> On sucessful retrieval of a user profile, JSON is returned:

```json
{
    "user_id": 4,
    "username": "Pheo",
    "email": "pheo@email.com",
    "profile_image": "http://images.instamelb.pinkpineapple.me/1.jpg",
    "counts": {
        "photos": 1320,
        "follows": 420,
        "followed_by": 3410
    }
}
```

Retrieves user profile. Use self as user_id to get profile of authenticated user.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/users/:user_id`

### URL Parameters

Parameters | Description
---------- | -----------
user_id | id of a User

## Get User Photos

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/1/photos
```

```java
N/A
```

> Successful retrieval of user photos returns JSON of: 

```json
{
    "photos": [
        {
            "photo_id": 1,
            "photo_image": "http://images.instamelb.pinkpineapple.me/1.jpg",
            "photo_caption": "Good Photo",
            "timestamp": 123456,
            "comments": {
                "count": 127
            },
            "likes": {
                "count": 2045
            },
            "location": {
                "longitude": 123.45,
                "latitude": 234.56
            }
        }
    ]
}
```

Gets list of photos posted by a user. Use self as user_id for authenticated user.

### HTTP Request
`GET http://instamelb.pinkpineapple.me/users/:user_id/photos`

### URL Parameters
Parameter | Description
--------- | -----------
user_id | id of a User

## Search Users

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/search?q=Pheo&suggested=false
```

```java
N/A
```

> Sucessful search for users returns JSON of:

```json
{
    "result": [
        {
            "user_id": 1,
            "username": "Pheo",
            "profile_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
        }
    ]
}

```

Searches for users. Allows searching for recommended/suggested users via query arguments.

### HTTP Request
`GET http://instamelb.pinkpineapple.me/users/search`

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
q | null | Query string.
suggested | true | true or false. If set to true, returns results sorted by relevance to authenticated user.
