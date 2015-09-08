# Feed

Two types of Feeds currently available. User (or Self) Feed and Activity (or Follows) Feed.

## Get Self Feed

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/self/feed
```

```java
N/A
```

> Successful retrieval of self feed returns JSON of:

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

Get authenticated user's feed. AKA "Self Feed".

### HTTP Request

`POST http://instamelb.pinkpineapple.me/users/self/feed`


## Get Follows Feed

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/follows/feed
```

```java
N/A
```

> Successful retrieval of follows feed returns JSON of:

```json
{
    "feed": [
        {
            "event": "comment",
            "message": "B commented on A's Photo.",
            "user_commenting": {
                "user_id": 3,
                "username": "B"
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
            "message": "B liked A's Photo.",
            "user_liking": {
                "user_id": 3,
                "username": "B"
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
            "message": "B is following A.",
            "user_following": {
                "user_id": 3,
                "username": "B"
            },
            "user_followed": {
                "user_id": 2,
                "username": "A"
            }
        }
    ]
}
```

Get feed for users followed by the authenticated user. AKA "Activity Feed".

### HTTP Request

`POST http://instamelb.pinkpineapple.me/users/follows/feed`
