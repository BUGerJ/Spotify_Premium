# Spotify_Premium
ByNguyen
#!name=Spotify_Unlock

#!desc=部分解锁premium,建议重新登录,音质不能设置为超高

# 1. 搜索界面 歌单/歌曲可以随意切换完全播放  2. 音乐库已点赞歌曲随意切换完全播放


[MITM]
hostname = %APPEND% spclient.wg.spotify.com

[Script]
spotify-json = type=http-request,type=http-request,pattern=^https:\/\/spclient\.wg\.spotify\.com\/(artistview\/v1\/artist|album-entity-view\/v2\/album)\/,requires-body=0,script-path=https://raw.githubusercontent.com/app2smile/rules/master/js/spotify-json.js
spotify-proto = type=http-response,pattern=^https:\/\/spclient\.wg\.spotify\.com\/(bootstrap\/v1\/bootstrap|user-customization-service\/v1\/customize)$,requires-body=1,binary-mode=1,max-size=0,script-path=https://raw.githubusercontent.com/app2smile/rules/master/js/spotify-proto.js,script-update-interval=0
