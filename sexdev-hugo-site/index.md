# sexdev的hugo建站


这篇文章是我通过hugo建站的过程。

<!--more-->

## 1 建立空站点

首先建立空站点:

```bash
hugo new site sexdev
```

## 2 下载主题

下载喜欢的主题，可通过国内的gitee下载：

```git
#首先初始化git目录
git init
#从开源站点拉取主题
git submodule add https://gitee.com/fbus/FixIt.git themes/FixIt
#更新主题
git submodule update --remote --merge
```

## 3 本地运行站点

```bash
#可以直接用themes里的实例运行，参数--source为需要运行的站点目录，默认在站点的根目录下
hugo server --source=D:\website\sexdev\Themes\FixIt\exampleSite -D
```

## 4 上传到gitee或者github上的代码库

可以把本地代码上传到gitee或者github代码库，gitee会快一些，关于怎样建立代码库请上网搜索。gitee需要开启gitee page。github我没有成功。

```bash
#进入站点目录运行，其中--destination参数为指定public文件夹生成的位置
hugo --theme=FixIt --baseUrl="https://sexdev.gitee.io" --source=D:\website\sexdev\Themes\FixIt\exampleSite --destination=D:\website\sexdev\public
#进入public目录，运行
git init
git remote add origin https://gitee.com/sexdev/sexdev.git
git add .
git commit -m "second commit"
git push -u origin master -f
```

在运行过程中会出现需要你提供用户名和邮箱的提示，按照提示把用户名和邮箱替换就行。执行最后一步会提示需要用户名和密码，gitee为你的注册用户和密码，github为你的注册用户，密码需要你进入github生成令牌环，使用令牌环作为密码进行登录。具体方法，请上网搜索。



