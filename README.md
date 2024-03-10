代码概括：
导入必要的库

requests：用于发送HTTP请求
lxml：用于解析HTML
os：用于创建目录和保存文件
multiprocessing.dummy：用于创建线程池
json：用于解析JSON字符串
time：用于测量运行时间
类定义：BingImagesSpider

此类用于爬取必应图片。它具有以下属性和方法：

属性：
thread_amount：线程池中的线程数
per_page_images：每页必应图片的数量
count：已下载图片的数量
success_count：成功下载图片的数量
ignore_chars：图片标题中要忽略的字符
image_types：允许的图片类型
headers：HTTP请求头
bing_image_url_pattern：必应图片URL模式
方法：
__init__：初始化类，设置爬取参数
__del__：析构函数，关闭线程池
request_homepage：请求必应图片主页
parse_homepage_response：解析必应图片主页响应，提取图片信息
request_and_save_image：请求并保存单个图片
deduplication：去除重复的图片信息
run：运行爬虫
主函数

从用户获取爬取参数：关键词、图片数量、保存路径
创建BingImagesSpider对象
运行run方法爬取图片
代码执行流程

根据用户输入的关键词和图片数量，生成必应图片主页URL列表。
使用线程池并发请求所有必应图片主页。
解析每个必应图片主页响应，提取图片信息。
去除重复的图片信息。
使用线程池并发下载并保存图片。
打印爬取结果，包括成功下载的图片数量和失败的图片数量。
运行效果：
![image](https://github.com/admin191/Bing-image-crawling/assets/111217383/8f149ea3-cf7a-45e9-9ed6-314ec2b1b395)

