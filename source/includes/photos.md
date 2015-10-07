# Photos

Photos are the building blocks of Instamelb.

## Get Photo

```shell
curl -X GET -u USERNAME:PASSWORD \
    http://instamelb.pinkpineapple.me/photo/1/
```

```java
N/A
```

> On sucessful retrieval of a photo:

```json
{
    "photo_id": 1,
    "photo_image": "http://images.instamelb.pinkpineapple.me/1.jpg",
    "photo_caption": "Good Photo",
    "timestamp": 123456,
    "location": {
        "longitude": 123.45,
        "latitude": 234.56
    },
    "user": {
        "user_id": 1,
        "username": "Pheo",
        "profile_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
    },
    "comments": {
        "count": 127
    },
    "likes": {
        "count": 2045
    }
}
```

Retrieves information about a photo.
See Comments and Likes routes to request those.

### HTTP Request

`GET http://instamelb.pinkpineapple.me/photo/:photo_id`

### URL Parameters

Parameters | Description
---------- | -----------
photo_id | id of a Photo

## Upload Photo

```shell
curl -H "Content-Type: application/json" -X POST -u USERNAME:PASSWORD \
    -d '{
        "caption": "Test Photo",
        "image": "ABSJM28djDJDJSM3ksi3jDJDSn",
        "image_thumbnail": "JJSJDCLKNJLKNSDCDABSJM2J",
        "longitude": 123.45,
        "latitude": 234.45
    }' \
    http://instamelb.pinkpineapple.me/photo
```

```java
N/A
```

> On successful photo upload, JSON response of:

```json
{
    "uploaded": true,
    "photo_id": 1,
    "photo_image": "http://images.instamelb.pinkpineapple.me/1.jpg",
    "photo_caption": "Good Photo",
    "timestamp": 123456,
    "user": {
        "user_id": 1,
        "username": "Pheo",
        "profile_image": "http://images.instamelb.pinkpineapple.me/1.jpg"
    },
    "location": {
        "longitude": 123.45,
        "latitude": 234.56
    }
}
```

> If unsuccessful:

```json
{
    "uploaded": false,
    "error": "Photo too large"
}
```

Uploads a photo to the authenticated user's account.

### HTTP Request

`POST http://instamelb.pinkpineapple.me/photo`

### Body Parameters

Parameters | Type | Description
---------- | ---- | -----------
image | String | BASE64 Compressed string of the image
image_thumbnail | String | BASE64 Compressed thumbnail string of image
caption | String | Text caption for the uploaded photo
latitude | Number | Location Latitude
longitude | Number | Location Longitude

