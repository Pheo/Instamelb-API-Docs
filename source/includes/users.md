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

## Get Self Feed

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/self/feed
```

```java
N/A
```

> Successful posting of comment returns JSON of:

```json
{
    "feed": [
        {
            "event": "comment",
            "message": "Pheo commented on A's Photo.",
            "user_commenting": {
                "user_id": 1,
                "username": "Pheo"
            },
            "user_commented": {
                "user_id": 2,
                "username": "A"
            },
            "photo": {
                "photo_id": 1,
                "photo_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
            }
        },
        {
            "event": "like",
            "message": "Pheo liked A's Photo.",
            "user_liking": {
                "user_id": 1,
                "username": "Pheo"
            },
            "user_liked": {
                "user_id": 2,
                "username": "A"
            },
            "photo": {
                "photo_id": 1,
                "photo_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
            }
        },
        {
            "event": "follow",
            "message": "Pheo is following A.",
            "user_following": {
                "user_id": 1,
                "username": "Pheo"
            },
            "user_followed": {
                "user_id": 2,
                "username": "A"
            }
        }
    ]
}
```

Get authenticated user's feed.

### HTTP Request

`POST http://instamelb.pinkpineapple.me/users/self/feed`

