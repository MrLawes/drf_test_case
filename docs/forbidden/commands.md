# Forbidden
    
    403	Forbidden 服务器理解请求客户端的请求，但是拒绝执行此请求

### 申明端点的访问限制

    self.register_user(user_name='class_1_student', http_authorization='Bearer xxx', user_id=1,
                                user_types='student,class_1_student')
                                
    self.set_forbidden(
        path='/v1/teacher/{pk}/', method='GET',
        exclude_auth_user=[self.class_1_student, ]
    )
              
    self.set_forbidden(
        path='/v1/teacher/{pk}/', method='GET',
        exclude_auth_user=self.get_users_by_user_type(user_types='student'),
    )

以学生身份访问老师列表，需要返回网络状态码为 403

### 免 Forbidden 检测

    self.add_forbidden_ignore(endpoint='/v1/teacher/{pk}/:GET')

该端点不会进行 Forbidden 检测

### Forbidden 检测
    self.is_valid_for_forbidden()
    
遍历所有的端点, 进行 forbidden 检测。

