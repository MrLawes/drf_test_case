# 用户注册和分类

### 注册用户

    from drf_test_case.test import UserAPITestCase

    class Test(UserAPITestCase):
    
        def test_cases(self):
            self.register_user(user_name='english_teacher', http_authorization='Bearer xxx', user_id=1,
                                        user_types='teacher,english_teacher')
            self.register_user(user_name='chinse_teacher', http_authorization='Bearer xxx', user_id=1,
                                        user_types='teacher,chinse_teacher')
            self.english_teacher.get('/v1/students/')
             
使用 register_user 注册用户。

注册完之后，可以使用 self.{user_name} 进行 post or get 操作， token 使用的是 http_authorization

### 获得不同类型的用户

    teachers = self.get_users_by_user_type(user_types='teacher')
    >>> [ APIClient('english_teacher'),  APIClient('chinse_teacher'),  ]
    chinse_teachers = self.get_users_by_user_type(user_types='chinse_teacher')
    >>> [ APIClient('chinse_teacher'),  ]

