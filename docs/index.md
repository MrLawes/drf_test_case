欢迎阅读 drf_test_case 文档
====================================
 drf_test_case 基于 rest_framework APITestCase 的基础之上， 
 支持注册不同身份的用户，用其身份进行接口测试。
 并使用注册过的用户，对所有端点进行 401， 403， 404 自动检测。
    
 快速安装
===================
    pip install drf-test-case

使用方法
====================================
    from drf_test_case.test import UserAPITestCase

    class Test(UserAPITestCase):
    
        def test_cases(self):
            pass
            
快速上手
====================================
  * [注册用户](register/commands.md)
  * [unauthorized](unauthorized/commands.md)
  * [forbidden](forbidden/commands.md)
  * [not_found](not_found/commands.md)
