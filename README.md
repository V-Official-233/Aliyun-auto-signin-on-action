# 阿里云盘自动签到
本项目旨在使用Github actions来为阿里云盘进行自动签到  [博客图文版教程](https://v-official-233.github.io/2023/04/28/%E5%88%A9%E7%94%A8github-action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0/)

## 如何使用

- [获取阿里云盘手机版Token](#获取阿里云盘手机版Token)
- [获取Github仓库访问密钥](#获取Github仓库访问密钥)
- [仓库环境变量配置](#仓库环境变量配置)
- [执行测试](#执行测试)


## 获取阿里云盘手机版Token
 [获取Token](https://alist.nn.ci/zh/guide/drivers/aliyundrive.html)
 (因为我太懒了所以用的AList官方之前获取阿里官方Token的页面）
![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E8%8E%B7%E5%8F%96%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E6%89%8B%E6%9C%BA%E7%89%88%E4%BB%A4%E7%89%8C.png)
记得拿个小本本把Token记下来吧

## 获取Github仓库访问密钥
点击右上角的个人头像，转到设置

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E8%BD%AC%E5%88%B0Github%E8%AE%BE%E7%BD%AE.jpg)

直接来到最下面找到Developer settings

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E6%89%BE%E5%88%B0Developer%20settings.png)

接下来选择Personal access tokens - Tokens（classic） - Generate new token - Generate new token（classic）

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E6%89%BE%E5%88%B0%E6%96%B0%E5%BB%BA%E5%AF%86%E9%92%A5.jpg)

Note(名称)可以随便写，"Expiration"把密钥过期换成"No expiration",下方勾选"repo"

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E6%96%B0%E5%BB%BA%E5%AF%86%E9%92%A5%E7%A4%BA%E4%BE%8B.jpg)

然后就划到最下边创建密钥

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E6%96%B0%E5%BB%BA%E5%AF%86%E9%92%A5.png)

完成后记得把成的密钥记下来，后面要用

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E4%BF%9D%E5%AD%98%E5%AF%86%E9%92%A5.jpg)

## 仓库环境变量配置

然后打开你Fork的仓库的设置，找到"Secrets and variables"-"Action"

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E6%89%BE%E5%88%B0%E4%BB%93%E5%BA%93%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F.jpg)

点击"New repository secret"新建变量

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E5%A1%AB%E5%86%99%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F.jpg)

分别填入刚刚获得的两个密钥
 GP_TOKEN | REFRESH_TOKENS
------------- | -------------
Github获取密钥(Personal access tokens (classic)) | 阿里云盘手机版Token
ghp_xxxxx| 获取的密钥是随机的，这里就不写示例了

两个都填好后：

![](https://gcore.jsdelivr.net/gh/V-Official-233/photo/%E5%88%A9%E7%94%A8Github%20Action%E5%AE%9E%E7%8E%B0%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%E8%87%AA%E5%8A%A8%E7%AD%BE%E5%88%B0_%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F%E7%A4%BA%E4%BE%8B.png)

## 执行测试
接下来执行Action运行查看是否签到成功即可

