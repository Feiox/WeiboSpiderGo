# WeiboSpiderGo

It's a sina weibo (chinese twitter) spider written by golang golly

可以双击运行的微博爬虫

#### 使用准备

- chrome driver安装

  本地需要安装chrome浏览器、以及下载对应版本的chromedriver。例如，本机上安装了版本号为78的chrome则需要在https://chromedriver.chromium.org/downloads 链接中下载版本号为78的，对应平台的chromedriver.zip

  将解压后的chromedriver文件放于项目的browser目录下

- mongodb安装

  安装mongodb，将地址和端口、数据库名填写到config.yaml中

#### 使用

完成上一步的使用准备工作后，可以下载release中的代码，在上方栏的release页中，分别有mac版与windows exe版本的压缩包，可以直接下载运行

填写需要登陆的账号于account/account.txt中，每行一个账号，源码的account文件夹可以看到示例，双击login开始批量登陆（账号要选择免验证码的邮箱登陆的账号）

在account/target.txt文件中，同样每行一个，写下要爬取的用户id，双击weibo_spider或weibo_spider.exe开始爬取

希望大家不要涸泽而渔，release中的版本爬取间隔为10秒左右

#### 配置文件内容

配置文件为根目录下的config.yaml

配置文件含义

```
MONGO_ADDRESS - mongodb地址
DB_NAME       - mongodb数据库名
ACCOUNT_FILE  - 存放要爬取的目标账户id的文件
DRIVER_PATH: "/browser/chromedriver"
# 爬取类型
SCRAPY_TYPE:
  Info: True
  Follow: False
  Fans: False
  Tweet:
    Main: True
    Comment: False
```







#### 编译

安装依赖后使用

```
go build login.go
go build weibo_spider.go
```

进行编译

#### 下一步

- [ ] 代理ip添加
- [ ] 图片视频下载

