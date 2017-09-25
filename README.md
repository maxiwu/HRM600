# HRM600
# RESTful API Spec

> STB 取得 playlist 列表 [Not Use]

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

Service : GET /stb/playlist
Description : 取得指定 playlist 內容  
Response Payload :
```sh
keyname=7a763dff-65ad-4566-975e-19e27f692cd5,[md5]
playlist.m3u,song1.scm,[url]
song1.scm,[md5],[url]
song2.scm,[md5],[url]
```

>下載解密金鑰

Service : GET /stb/key/download?id=[key_id]  
Request Parameter :  
id : 取回 playlist 中的 keyname 欄位置, 目前設定為 UUID 格式  
Response :
```sh
下載解密金鑰, 檔名為上傳時所用之檔案名稱
```
