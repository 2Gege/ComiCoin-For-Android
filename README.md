# OauthApi
## 认证方法
### 路径
index.php?app=api&mod=Oauth&act=authorize  

### 参数说明
* varchar login 手机号或用户名（必填）
* varchar password 密码（必填）  

### 返回
* array [status] 状态（0:失败；1:成功；）
* array [msg] 提示
* array [oauth_token]  其余api接口都需要获取oauth_token
* array [oauth_token_secret]  其余api接口都需要获取oauth_token_secret
* array [uid]  用户ID  

## 注销帐号，刷新token
### 路径
index.php?app=api&mod=Oauth&act=logout  

### 参数说明
* login 手机号或用户名（必填）  

### 返回
* array [status] 状态（0:失败;1:成功;）
* array [msg] 提示  

# WeiboStatusesApi
## 获取当前用户所关注用户的最新分享信息
### 路径
index.php?app=api&mod=WeiboStatuses&act=friends_timeline  

### 参数说明
* page 页码（选填）  

### 返回
* array [] [feed_id] 分享ID
* array [] [type] 分享类型（post:文本;postimage:图片;postaudio:音频;postvideo:视频;repost:转发;）
* array [] [feed_content] 分享内容
* array [] [showtime] 分享创建时间
* array [] [uid] 分享者ID
* array [] [uname] 分享者昵称
* array [] [avatar_big] 分享者头像（200x200）
* array [] [avatar_middle] 分享者头像（100x100）
* array [] [avatar_small] 分享者头像（50x50）
