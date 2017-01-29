# OauthApi

### authorize
#### 作用
认证方法
#### 参数说明
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
