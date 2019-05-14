#### 1.sessionStorage,localStorage,cookie区别?
    1.有效期：localStorage长期有效，直到用户删除；sessionStorage在窗口关闭前有效；
    cookie在设置的有效期内有效，默认为浏览器关闭
    2.共享：localStorage在同源文档间共享，sessionStorage不能共享，
    cookie在同源且符合path规则的文档之间共享
    3.cookie会在请求时发送到服务器，作为会话标识，服务器可修改cookie，web storage不会发送到服务器
    4.浏览器不能保存超过300个cookie，单个服务器不能超过20个，每个cookie大小不超过4K，
    web storage 大小可达5M