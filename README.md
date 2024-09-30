# DYTT_movie
用于电影天堂的电影爬取，获取电影信息并输出到文档，方便选片、下载和对下载的视频文件重命名（在电视上投屏看） 
## 运行备注  
直接执行dytt.py文件既可，现成的‘电影清单.xlsx’文件可要可不要，新爬到的电影会根据列表中是否已存在，选择性进行追加，不用担心数据会重复写入  
## 效果展示  
![image](https://github.com/user-attachments/assets/131bd14e-18f0-4487-83a7-787afaa549e3)  
输出到excel  
![image](https://github.com/user-attachments/assets/6b74719a-692e-4d11-a404-a225f6dcb3f1)  
# 爬取思路  
所有的信息都藏在了页面内容里面，而没有通过啥电影列表、电影详情接口进一步渲染获取
所以只要拿到html文件的txt内容,靠正则解析，既可获取到想要的信息
## 核心页面  
1. 电影首页地址  https://www.dytt8.net/index.htm  
2. 最新电影地址  https://www.dytt8.net/html/gndy/dyzz/list_23_1.html
3. 电影详情页  https://www.dytt8.net/html/gndy/dyzz/20240814/65290.html
4. 其他专题页
   4.1 国内电影  https://www.dytt8.net/html/gndy/china/index.html
   4.2 日韩电影  https://www.dytt8.net/html/gndy/rihan/index.html
   4.3 欧美电影  https://www.dytt8.net/html/gndy/oumei/index.html
   4.4 精品电影  https://www.dytt8.net/html/gndy/dyzz/index.html
首页有一些最新的电影，甚至不展示在最新电影地址页面，可以用来获取下载地址和片名  
![image](https://github.com/user-attachments/assets/53fd912a-dc7c-4ed7-a363-0cc0300bce59)  
最新电影页可以遍历大部分的电影  
![image](https://github.com/user-attachments/assets/8b5d27d1-e10b-4e09-a122-f607e9a15527)  
电影详情页用来进一步获取列表页没有完整显示的内容  
![image](https://github.com/user-attachments/assets/13386253-eea8-46b8-9f04-bdc964a839e9)  
![image](https://github.com/user-attachments/assets/f2b15c01-0a1a-47e6-83bf-7c9177a8b9c2)  
解析出来的结构
![image](https://github.com/user-attachments/assets/2e925fad-33da-44a4-b5f6-0bb42f47c16b)  
