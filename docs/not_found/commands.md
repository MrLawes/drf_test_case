# not_found
    
    404	Not Found 服务器无法根据客户端的请求找到资源。

### 申明端点可访问资源数量
                
    self.testcase.set_found(
        path='/v1/teacher/{pk}/', method='GET',
        auth_user=self.english_teacher, found_count=1,
    )
    
    self.testcase.set_found(
        path='/v1/teacher/{pk}/', method='GET',
        auth_user=self.chinse_teacher, found_count=1,
    )

### 免 not_found 检测

    self.add_not_found_ignore(endpoint='/v1/teacher/{pk}/:GET')

该端点不会进行 not_found 检测

### not_found 检测
    self.is_valid_for_not_found()
    
遍历所有的端点, 进行 not_found 检测。

