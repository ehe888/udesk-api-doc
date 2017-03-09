###Webhook总体说明

所谓Webhook，就是用户提供一个url，当Udesk系统中的某些信息发生变化时，会触发Webhook，将变更信息推送至用户提供的url。目前支持的触发事件有6个，它们分别是：
1. 客户创建
2. 客户更新
3. 客户删除
4. 公司创建
5. 公司更新
6. 公司删除

这6个事件的每一个推送都需要用户设置权限来决定是否开启或者关闭。

用户提供Url的接口说明详见“设置推送url”文档。

用户设置权限接口说明详见“设置推送权限”文档。

其中：
1. 客户、公司删除时会将被删除的id推送给用户url
2. 客户、公司更新时会将变更信息推送给用户url
3. 客户、公司创建是会将新建对象信息推送给用户url

###设置推送权限
* URL https://yoursubdomain.udesk.cn/open_api_v1/set_permissions
* METHOD POST

####请求参数说明
```yaml
organization_create: 创建公司
organization_update: 更新公司
organization_destroy: 摧毁公司
customer_create: 创建客户
customer_destroy: 删除客户
customer_update: 更新客户
```
####请求示例
```javascript
{ 
  "permissions":
  {
    "organization_create":true,
    "organization_update": true,
    "organization_destroy": true
  }
}
//JSON要按照这个格式传，这里的六个值，不传就不变，传了就更新
```

####返回示例
```json
{
  "code":1000,
  "message": "OK",
  "permissions":
  {
    "organization_create":true,
    "organization_update": true,
    "organization_destroy": true,
    "customer_create": true,
    "customer_update": true,
    "customer_destroy": true
  }
}
```
###设置推送url

* URL https://yoursubdomain.udesk.cn/open_api_v1/set_url
* METHOD POST

####请求示例
```json
  { "push_url":"https://baidu.com" }
```

####返回结果示例
```javascript

//code为结果状态码，message为信息
{ 
  "code": 1000, 
  "message":"OK",
  "push_url":"https://baidu.com"
}

```
