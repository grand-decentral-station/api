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
| Parameter | Value Type | Optioanl |
| --------- | ---------- | -------- |
| sizes     | Array      | True     |
| filter    | Array      | True     |
