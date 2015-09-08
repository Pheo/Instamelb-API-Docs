# Comments

Users are able to comment on photos.
Comments can be in reply to other comments by including the recipient's username in the text.
For example, "@Pheo: You retard."


## Retrieve Comments

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/photo/1/comments
```

```java
N/A
```

> On sucessful retrieval of comments of a photo, JSON is returned:

```json
{
    "comments": [
        {
            "comment_id": 1,
            "created_at": 1280780324,
            "updated_at": 1234124096,
            "location": {
                "longitude": 123.45,
                "latitude": 123.45
            },
            "text": "Really amazing photo!",
            "from": {
                "user_id": 1,
                "username": "Pheo",
                "profile_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
            }
        }
    ]
}
```

Retrieves comments on a photo.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/photo/:photo_id/comments`

### URL Parameters

Parameters | Description
---------- | -----------
photo_id | id of a Photo

## Post Comment

```shell
curl -H "Content-Type: application/json" -X POST \
    -u USERNAME:PASSWORD \
    -d '{
            "text": "This photo sucks!"
        }' \
    http://instamelb.pinkpineapple.me/photo/1/comments
```

```java
N/A
```

> Successful posting of comment returns JSON of:

```json
{
    "posted": true
}
```

Post a comment on a photo.

### HTTP Request

`POST http://instamelb.pinkpineapple.me/photo/:photo_id/comments`

### URL Parameters

Parameters | Description
---------- | -----------
photo_id | id of a Photo

### Body Parameters

Parameters | Type | Description
---------- | ---- | -----------
text | String | Text of comment


## Delete Comment

```shell
curl -X DELETE -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/photo/1/comments/8
```

```java
N/A
```

> Successful deletion of comment returns JSON of: 

```json
{
    "deleted": true
}
```

> In event of failed deletion, returns JSON of:

```json
{
    "deleted": false,
    "error": "Comment does not exist"
}
```

Deletes a comment.

### HTTP Request

`DELETE http://instamelb.pinkpineapple.me/photo/:photo_id/comments/:comment_id`

### URL Parameters
Parameter | Description
--------- | -----------
photo_id | id of a Photo
comment_id | id of a Comment

