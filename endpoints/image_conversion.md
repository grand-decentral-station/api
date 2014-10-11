# Image Conversion API

To provide a backend independent solution for image conversion the GDS Platform
provides a unified API. If your application already uses an image library like
GD or ImageMagick you can still use it, but it is strongly advised to use the API.

## Thumbnail Generation

| &nbsp;   | &nbsp;            |
| -------- | ----------------- |
| Endpoint | /images/thumbnail |
| Method   | POST              |


Thumbnails are everywhere and if you don't want to load a 4mb image you should use
thumbnails. The GDS Platform provides a convenient API for that use case. Without any further
input the API gives back three thumbnails.

### Parameters

| Parameter   | Value Type | Optioanl |
| ---------   | ---------- | -------- |
| destination | String     | False    |
| sizes       | Array      | True     |
| filter      | Array      | True     |

### Example

```json
{
  "destination": "/var/:app_name/folder/",
  "sizes": ["100x100","250x250","500x500"],
  "filter": ["bw"]
}
```

### Response

Status: 200

```json
{
  "message": "successfully converted",
  "images": [[
      "/var/:app_name/folder/:image_name_100x100",
      "/var/:app_name/folder/:image_name_250x250",
      "/var/:app_name/folder/:image_name_500x5000",
    ],[
      "/var/:app_name/folder/:another_image_name_100x100",
      "/var/:app_name/folder/:another_image_name_250x250",
      "/var/:app_name/folder/:another_image_name_500x5000",
    ]
  ]
}
```