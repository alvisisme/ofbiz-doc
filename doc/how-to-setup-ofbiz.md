# 如何启动OFBiz

1. 打开终端
1. 进入ofbiz目录
1. 清理构建文件

    ```
    ./ant clean-all
    ```

1. 加载种子数据

    ```
    ./ant load-extseed
    ```

1. 创建超级管理员账号

    ```
    ./ant create-admin-user-login
    ```

    根据提示输入用户登录账号,自动生成临时密码为**ofbiz**

1. 启动ofbiz

    ```
    ./ant start
    ```

1. 打开应用

    浏览器输入 https://localhost:8443/webtools 进入管理页面,第一次会提示修改密码.


## 参考引用

