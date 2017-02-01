# WeiboStatusesApi

### friends_timeline
#### 作用
获取当前用户所关注用户的最新分享信息
#### 参数说明
* int [page] 页码

#### 返回
* [] 
    * feed_id 分享ID 
    * type 分享类型（post:文本;postimage:图片;postaudio:音频;postvideo:视频;repost:转发;）
    * feed_content 分享内容
    * showtime 分享创建时间
    * digg_count 分享赞计数
    * comment_count 分享评论计数
    * repost_count 分享转发计数
    * is_digg 是否点赞
    * is_comment 是否评论
    * is_repost 是否转发
    * is_coll 是否转发
    * uid 分享者ID
    * uname 分享者昵称
    * avatar_big 分享者头像（200x200）
    * avatar_middle 分享者头像（100x100）
    * avatar_small 分享者头像（50x50）
    * has_attach 是否有附件（1:true;0:false;）
    * attach []
      * attach_url 附件地址
      * attach_small 附件地址(120x120)
      * attach_medium 附件地址(240xauto)
      * attach_middle 附件地址(740xauto)
      * attach_middle_box 附件地址(240x240)
      * attach_middle 附件地址(740xauto)
      * height 附件长度
      * weight 附件宽度
      * size 附件大小
    * transpond_id 转发原PO的分享ID
    * transpond_data 转发原PO的分享数据（格式同show方法）

### user_timeline
#### 作用
获取用户发布的分享信息列表
#### 参数说明
* int user_id 用户ID
* int [page] 页码

#### 返回（同friends_timeline方法）

### show
#### 作用
获取某条分享的详细内容
#### 参数说明
* int id 分享ID

#### 返回
* feed_id 分享ID 
* type 分享类型（post:文本;postimage:图片;postaudio:音频;postvideo:视频;repost:转发;）
* feed_content 分享内容
* showtime 分享创建时间
* digg_count 分享赞计数
* comment_count 分享评论计数
* repost_count 分享转发计数
* is_digg 是否点赞
* is_comment 是否评论
* is_repost 是否转发
* is_coll 是否转发
* uid 分享者ID
* uname 分享者昵称
* avatar_big 分享者头像（200x200）
* avatar_middle 分享者头像（100x100）
* avatar_small 分享者头像（50x50）
* has_attach 是否有附件（1:true;0:false;）
* attach []
  * attach_url 附件地址
  * attach_small 附件地址(120x120)
  * attach_medium 附件地址(240xauto)
  * attach_middle 附件地址(740xauto)
  * attach_middle_box 附件地址(240x240)
  * attach_middle 附件地址(740xauto)
  * height 附件长度
  * weight 附件宽度
  * size 附件大小
* transpond_id 转发原PO的分享ID
* transpond_data 转发原PO的分享数据（格式同show方法）

### add_digg
#### 作用
为某条分享添加赞
#### 参数说明
* int feed_id 分享ID

#### 返回
* true
* false

### del_digg
#### 作用
为某条分享取消赞
#### 参数说明
* int feed_id 分享ID

#### 返回
* true
* false

### destroy
#### 作用
删除指定分享
#### 参数说明
* int id 分享ID

#### 返回
* status （1:true;0:false;）

### reposts
#### 作用
获取指定分享的转发列表
#### 参数说明
* int id 分享ID

#### 返回（同friends_timeline方法）

### comments
#### 作用
获取指定分享的评论列表
#### 参数说明
* int id 分享ID

#### 返回
* []
   * comment_id 评论ID
   * content 评论内容
   * showtime 创建时间
   * uid 评论者ID
   * uname 评论者昵称
   * avatar_big 评论者头像（200x200）
   * avatar_middle 评论者头像（100x100）
   * avatar_small 评论者头像（50x50）
   * to_uid 被评论的评论者ID（楼中楼的情况）
   * to_comment_id 被评论的评论ID（楼中楼的情况）

### diggs
#### 作用
获取指定分享的赞过的人的列表
#### 参数说明
* int id 分享ID

#### 返回
* count 收到的赞总数
* data []
   * cTime 点赞时间戳
   * feed_id 被赞的分享ID
   * uid 点赞用户ID
   * uname 点赞用户昵称
   * avatar_big 点赞者头像（200x200）
   * avatar_middle 点赞者头像（100x100）
   * avatar_small 点赞者头像（50x50）

### diggs_to_me
#### 作用
获取我收到的赞
#### 参数说明
#### 返回(同diggs方法)
 
### comments_to_me_true
#### 作用
获取当前用户收到的评论,除去自己的评论
#### 参数说明
* int [page] 页码

#### 返回（同comments方法）

### comments_by_me
#### 作用
获取当前用户发出的评论
#### 参数说明
* int [page] 页码

#### 返回（同comments方法）

### mentions_feed
#### 作用
提到我的feed
#### 参数说明
* int [page] 页码

#### 返回（同friends_timeline方法）

### favorite_feed
#### 作用
收藏的feed列表
#### 参数说明
* int [page] 页码

#### 返回（同friends_timeline方法）

### update
#### 作用
发布一条分享
#### 参数说明
* varchar content 分享内容
* varchar type 分享类型（post:文本;postimage:图片;postaudio:音频;postvideo:视频;）

#### 返回
* status 状态（1:true;0:false;）
* info 提示
* feed_id 分享ID

### comment
#### 作用
发表评论
#### 参数说明
* int row_id 分享ID
* int app_uid 分享者ID
* varchar content 评论内容
* int [to_comment_id] 被评论的评论ID
* int [to_uid] 被评论的评论者ID

#### 返回
* status 状态（1:true;0:false;）
* info 提示
