# HRM600
# RESTful API Spec

> STB 取得 playlist 列表

Service : GET /stb/playlist/list  
Description : 取得 playlist 列表  
Response Payload :
```sh
[{
    "playlist_id": 4
},
{
    "playlist_id": 3
}]
```
>STB 取得 playlist 內容

Service : GET /stb/playlist?id=[playlist_id]  
Description : 取得指定 playlist 內容  
Response Payload :
```sh
keyname=7a763dff-65ad-4566-975e-19e27f692cd5
period_start=08:30
period_end=18:00
facebook.png,null,http://www.facebook.com
image.png,null,http://www.google.com
```

