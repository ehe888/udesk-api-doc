###获取token
+ URL  https://yourdomain.udesk.cn/open_api_v1/log_in
+ METHOD POST

#####请求参数:

| 字段名称  |  类型  |是否必填|
|-----------|--------|--------|
| email     | String |   是   |
| password  | String |   是   |

#####请求示例：
```json
{ 
  "email":"libai@udesk.cn", 
  "password":"password"
}
```
#####返回参数示例：
```json
{
  "code":1000, 
  "open_api_token":"123abc"
}
```
