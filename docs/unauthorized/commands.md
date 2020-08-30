# 用户的身份认证

    401	Unauthorized 请求要求用户的身份认证

### 免身份认证申明

    self.set_unauthorized(path='/v1/users/sms/', method='POST', )

申明哪些项目中哪些端点是不需要用户的身份认证的，比如用户未登陆前的发送短信的接口。
如果未申明，自动化测试将会检测出 HTTP_401_UNAUTHORIZED 的错误


### unauthorized 检测
    self.is_valid_for_unauthorized()
    
自动遍历所有的端点进行 Unauthorized 检测

