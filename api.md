

# 接口文档


## 系统鉴权

| 名称        | URL                 | 方式 | 描述         | 参数     |
| ----------- | ------------------- | ---- | ------------ | -------- |
| login       | /system/login       | post | 登录         | 用户表单 |
| logout      | /system/logout      | post | 登出         |          |
| getUserInfo | /system/getUserInfo | get  | 获取用户信息 |          |

## 作业

| 名称  | URL                   | 方式 | 描述                       | 参数             |
| ----- | --------------------- | ---- | -------------------------- | ---------------- |
| tasks | /tasks/{card}&{state} | get  | 查询装载司机已完成委托作业 | 车号、作业状态 |
| tasks | /tasks/{taskId}       | put  | 更新委托作业确认状态       | 委托作业号       |
