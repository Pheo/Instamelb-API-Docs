# Follows

Users are able to follow other users. Following another user allows the follower to access latest feed about the followed user in the follower's Activity Feed.

## Get User Follows

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/1/follows
```

```java
N/A
```

> On sucessful retrieval of user follows, JSON is returned:

```json
{
    "follows":  [
        {
            "user_id": 1,
            "username": "Pheo",
            "profile_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
        }
    ]
}
```

Retrieves a list of users that a user is following.
Plain English: People you follow.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/users/:user_id/follows`

### URL Parameters

Parameters | Description
---------- | -----------
user_id | id of a User

## Get User Followers

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/users/1/followers
```

```java
N/A
```

> Successful retrieval of user's followers returns JSON of: 

```json
{
    "followers":  [
        {
            "user_id": 1,
            "username": "Pheo",
            "profile_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
        }
    ]
}
```

Retrieves a list of users that follow a user.
Plain English: People that are following you.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/users/:user_id/followers`

### URL Parameters
Parameter | Description
--------- | -----------
user_id | id of a User

## Follow/Unfollow User

```shell
curl -H "Content-Type: application/json" -X POST -u USERNAME:PASSWORD \
    -d '{
        "action": "follow"
    }' \
    http://instamelb.pinkpineapple.me/users/1/relationship
```

```java
N/A
```

> Sucessful follow of a user returns JSON of:

```json
{
    "modified": true,
    "action": "follow"
}
```

The authenticated user may follow/unfollow another user. No permission to follow is required in Instamelb (constrasting with Instagram)

### HTTP Request

`POST http://instamelb.pinkpineapple.me/users/:user_id/relationship`

### URL Parameters
Parameter | Description
--------- | -----------
user_id | id of a User

### Body Parameters
Parameter | Type | Description
--------- | ------- | -----------
action | String | One of follow, unfollow

