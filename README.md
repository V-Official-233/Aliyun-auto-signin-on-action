# 阿里云盘自动签到
本项目旨在使用Github actions来为阿里云盘进行自动签到

## 如何使用

- [获取阿里云盘手机版Token](#获取阿里云盘手机版Token)
- [获取Github仓库访问密钥](#获取Github仓库访问密钥)
- [仓库环境变量配置](#)
- [执行测试](#)


## 获取阿里云盘手机版Token
 [获取Token](https://alist.nn.ci/zh/guide/drivers/aliyundrive.html)
 (因为我太懒了所以用的AList官方之前获取阿里官方Token的页面）
![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/0.png)
记得拿个小本本把Token记下来~

## 获取Github仓库访问密钥
点击右上角的个人头像，转到设置

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/0.jpg)

直接来到最下面找到Developer settings

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/1.png)

接下来选择Personal access tokens - Tokens（classic） - Generate new token - Generate new token（classic）

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/2.jpg)

Note(名称)可以随便写，"Expiration"把密钥过期换成"No expiration",下方勾选"repo"

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/3.jpg)

然后就划到最下边创建密钥

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/4.png)

完成后记得把成的密钥记下来，后面要用

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/5.jpg)

然后打开你Fork的仓库的设置，找到"Secrets and variables"-"Action"

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/6.jpg)

点击"New repository secret"新建变量

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/7.jpg)

分别填入刚刚获得的两个密钥
 GP_TOKEN | REFRESH_TOKENS
------------- | -------------
Github获取密钥(Personal access tokens (classic)) | 阿里云盘手机版Token
ghp_xxxxx| 获取的密钥是随机的，这里就不写示例了

两个都填好后：

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/20230416023352.png)

## 接下来执行Action运行查看是否签到成功即可

