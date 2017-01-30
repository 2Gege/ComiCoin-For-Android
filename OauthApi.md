# OauthApi

### authorize
#### 作用
认证方法
#### 参数说明
* varchar login 手机号或用户名
* varchar password 密码

#### 返回
* {} 
 * oauth_token 其余api接口都需要获取oauth_token
 * oauth_token_secret 其余api接口都需要获取oauth_token_secret
 * uid 用户ID
 * msg 提示
 * status 状态（0:失败；1:成功；）

### logout
#### 作用
注销帐号，刷新token
#### 参数说明
* varchar login 手机号或用户名
### 返回
* {} 
 * msg 提示
 * status 状态（0:失败；1:成功；）
