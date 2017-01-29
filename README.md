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
* array [] [digg_count] 分享赞计数
* array [] [comment_count] 分享评论计数
* array [] [repost_count] 分享转发计数
* array [] [is_digg] 是否点赞
* array [] [is_comment] 是否评论
* array [] [is_repost] 是否转发
* array [] [is_coll] 是否转发
* array [] [uid] 分享者ID
* array [] [uname] 分享者昵称
* array [] [avatar_big] 分享者头像（200x200）
* array [] [avatar_middle] 分享者头像（100x100）
* array [] [avatar_small] 分享者头像（50x50）
* array [] [has_attach] 是否有附件（1:true;0:false;）
* array [] [attach] [] [attach_url] 附件地址
* array [] [attach] [] [attach_small] 附件地址(120x120)
* array [] [attach] [] [attach_medium] 附件地址(240xauto)
* array [] [attach] [] [attach_middle] 附件地址(740xauto)
* array [] [attach] [] [attach_middle_box] 附件地址(240x240)
* array [] [attach] [] [height] 附件长度
* array [] [attach] [] [weight] 附件宽度
* array [] [attach] [] [size] 附件大小
* array [] [attach] [] [transpond_id] 转发原PO的分享ID
* array [] [attach] [] [transpond_data] 转发原PO的分享数据（格式内容同上）

## 获取某条分享的详细内容
### 路径
index.php?app=api&mod=WeiboStatuses&act=show

### 参数说明
* id 分享ID（必填）

### 返回
* array [feed_id] 分享ID
* array [type] 分享类型（post:文本;postimage:图片;postaudio:音频;postvideo:视频;repost:转发;）
* array [feed_content] 分享内容
* array [showtime] 分享创建时间
* array [digg_count] 分享赞计数
* array [comment_count] 分享评论计数
* array [repost_count] 分享转发计数
* array [is_digg] 是否点赞
* array [is_comment] 是否评论
* array [is_repost] 是否转发
* array [is_coll] 是否转发
* array [uid] 分享者ID
* array [uname] 分享者昵称
* array [avatar_big] 分享者头像（200x200）
* array [avatar_middle] 分享者头像（100x100）
* array [avatar_small] 分享者头像（50x50）
* array [has_attach] 是否有附件（1:true;0:false;）
* array [attach] [] [attach_url] 附件地址
* array [attach] [] [attach_small] 附件地址(120x120)
* array [attach] [] [attach_medium] 附件地址(240xauto)
* array [attach] [] [attach_middle] 附件地址(740xauto)
* array [attach] [] [attach_middle_box] 附件地址(240x240)
* array [attach] [] [height] 附件长度
* array [attach] [] [weight] 附件宽度
* array [attach] [] [size] 附件大小
* array [attach] [] [transpond_id] 转发原PO的分享ID
* array [attach] [] [transpond_data] 转发原PO的分享数据（格式内容同上）

## 为某条分享添加赞
### 路径
index.php?app=api&mod=WeiboStatuses&act=add_digg

### 参数说明
* feed_id 分享ID（必填）

### 返回
* true
* false

## 为某条分享取消赞
### 路径
index.php?app=api&mod=WeiboStatuses&act=del_digg

### 参数说明
* feed_id 分享ID（必填）

### 返回
* true
* false
