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

>下載 playlist.m3u
Service : GET /stb/playlist/m3u?id=[playlist_id]
Request Parameters : id : playlist id, 若無此參數則會傳回系統預設的 playlist
Response (File): 
```sh
#EXTM3U
#EXTINF:1, artist - title
file:///media/mmcblk0p1/emmcMusic/image.scm
#EXTINF:2, artist - title
file:///media/mmcblk0p1/emmcMusic/book.scm
```

>下載解密金鑰

Service : GET /stb/key/download?id=[key_id]  
Request Parameter :  
id : 取回 playlist 中的 keyname 欄位置, 目前設定為 UUID 格式  
Response :
```sh
下載解密金鑰, 檔名為上傳時所用之檔案名稱
```

2017/09/27
>取得此 STB 被指派的 playlist 下載資訊

Service : GET /stb/download_list?access_token=[the_access_token]
Parameter :
    access_token : STB 安裝完成後所取得的 access_token 
Response (File):
```sh
7a763dff-65ad-4566-975e-19e27f692cd5.pem,00000000df77b0d8d6536c7509a97363b4dd6f25,http://stbapi.timcircle.com:80/stb/key/download?id=7a763dff-65ad-4566-975e-19e27f692cd5
playlist.m3u,C1967371781F38CC985F38D6586B78F1,http://stbapi.timcircle.com:80/stb/playlist/m3u?id=4
facebook.png,null,http://www.facebook.com
```

>取回 playlist 的解密金鑰

Service : GET /stb/key/download?id=[key id]&access_token=[the_access_token]
Parameter :
    id : 解密金鑰的 id, 由上方 Download File Content 中取出時應該就會自動帶出
access_token : STB 安裝完成後所取得的 access_token , 這段不會由上方自動帶出, 請自行加上
Response (File): key.pem
```sh
-----BEGIN RSA PUBLIC KEY-----
......
-----END RSA PUBLIC KEY-----

```

>取回此 STB 的 playlist.m3u 內容

Service : GET /stb/playlist/m3u?id=[playlist_id]&access_token=[the_access_token]
Parameter :
    id : playlist 的 id, 由上方 Download File Content 中取出時應該就會自動帶出
access_token : STB 安裝完成後所取得的 access_token, 這段不會由上方自動帶出, 請自行加上
Response (File): playlist.m3u
```sh
#EXTM3U
#EXTINF:1, artist - title
file:///media/mmcblk0p1/emmcMusic/facebook.png
```


