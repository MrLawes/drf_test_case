# 如何注册用户

### 注册用户

    from drf_test_case.test import UserAPITestCase

    class Test(UserAPITestCase):
    
        def test_cases(self):
            self.register_user(user_name='teacher', http_authorization='Bearer xxx', user_id=1,
                                        user_types='teacher,english_teacher')
            self.teacher.get('/v1/students/')
             
使用 register_user 注册用户。

注册完之后，可以使用 self.{user_name} 进行 post or get 操作， token 使用的是 http_authorization

