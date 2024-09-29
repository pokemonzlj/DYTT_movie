# DYTT_movie
用于电影天堂的电影爬取，获取电影信息并输出到文档，方便选片、下载和视频文件重命名  
# 爬取思路  
所有的信息都藏在了页面内容里面，而没有通过啥电影列表、电影详情接口进一步渲染获取
所以只要拿到html文件的txt内容既可获取到想要的信息
## 核心页面路径  
1. 电影首页地址  https://www.dytt8.net/index.htm  
2. 最新电影地址  https://www.dytt8.net/html/gndy/dyzz/list_23_1.html
3. 电影详情页  https://www.dytt8.net/html/gndy/dyzz/20240814/65290.html
首页有一些最新的电影，甚至不展示在最新电影地址页面，可以用来获取下载地址和片名  
![image](https://github.com/user-attachments/assets/53fd912a-dc7c-4ed7-a363-0cc0300bce59)  
最新电影页可以遍历大部分的电影  
![image](https://github.com/user-attachments/assets/8b5d27d1-e10b-4e09-a122-f607e9a15527)  
电影详情页用来进一步获取列表页没有完整显示的内容  
![image](https://github.com/user-attachments/assets/13386253-eea8-46b8-9f04-bdc964a839e9)  
![image](https://github.com/user-attachments/assets/f2b15c01-0a1a-47e6-83bf-7c9177a8b9c2)  
