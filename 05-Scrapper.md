# 网络爬虫

## /robots.txt
robots.txt是一个协议，而不是一个命令。robots.txt是搜索引擎中访问网站的时候要查看的第一个文件。robots.txt文件告诉蜘蛛程序在服务器上什么文件是可以被查看的。

当一个搜索蜘蛛访问一个站点时，它会首先检查该站点根目录下是否存在robots.txt，如果存在，搜索机器人就会按照该文件中的内容来确定访问的范围；如果该文件不存在，所有的搜索蜘蛛将能够访问网站上所有没有被口令保护的页面。百度官方建议，仅当您的网站包含不希望被搜索引擎收录的内容时，才需要使用robots.txt文件。如果您希望搜索引擎收录网站上所有内容，请勿建立robots.txt文件。

robots.txt必须放置在一个站点的根目录下，而且文件名必须全部小写。
语法：最简单的 robots.txt 文件使用两条规则：
* User-Agent: 适用下列规则的漫游器
* Disallow: 要拦截的网页

## python上的网页获取库：urllib, requests


## python上的网页解析库：beautifulsoup


## python上的模拟浏览器：selenium