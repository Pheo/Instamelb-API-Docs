# Likes

Users are able like a photo.

## Get Photo Likes

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/photo/1/likes
```

```java
N/A
```

> On sucessful retrieval of likes of a photo, JSON is returned:

```json
{
    "likes": [
        {
            "user_id": 1,
            "username": "Pheo",
            "timestamp": 145234325243324
        }
    ]
}
```

Retrieves a list of users who like a photo.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/photo/:photo_id/likes`

### URL Parameters

Parameters | Description
---------- | -----------
photo_id | id of a Photo

## Like Photo

```shell
curl -X POST -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/photo/1/likes
```

```java
N/A
```

> On successful like, JSON response of:

```json
{
    "liked": true
}
```

> If unsuccessful:

```json
{
    "liked": false,
    "error": "Already liked photo"
}
```

Set a like by authenticated user on a photo.

### HTTP Request

`POST http://instamelb.pinkpineapple.me/photo/:photo_id/likes`

### URL Parameters

Parameters | Description
---------- | -----------
photo_id | id of a Photo

## Unlike Photo

```shell
curl -X DELETE -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/photo/1/likes
```

```java
N/A
```

> Successful unlike returns JSON of: 

```json
{
    "unliked": true
}
```

> In event of failed unlike, returns JSON of:

```json
{
    "unliked": false,
    "error": "Photo not already liked"
}
```

Deletes a comment.

### HTTP Request

`DELETE http://instamelb.pinkpineapple.me/photo/:photo_id/likes`

### URL Parameters
Parameter | Description
--------- | -----------
photo_id | id of a Photo

