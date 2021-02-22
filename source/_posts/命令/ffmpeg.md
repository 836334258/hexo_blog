---
title: linux 安装
---
[教程地址](https://www.jianshu.com/p/ddafe46827b7)

##  常用命令

```bash
-i 设定输入流 
-f 设定输出格式 
-ss 开始时间 

-b 设定视频流量(码率)，默认为200Kbit/s 
-r 设定帧速率，默认为25 
-s 设定画面的宽与高 
-aspect 设定画面的比例 
-vn 不处理视频 
-vcodec 设定视频编解码器，未设定时则使用与输入流相同的编解码器 

-ar 设定采样率 
-ac 设定声音的Channel数 
-acodec 设定声音编解码器，未设定时则使用与输入流相同的编解码器 
-an 不处理音频
```



## 视频

```bash
ffmpeg -i videos/1.mp4 videos/1.avi #转换格式
ffmpeg -i videos/1.mp4 -vcodec copy -an videos/novoice.mp4 #视频静音
ffmpeg -i videos/1.mp4 -ss 00:00:15 -t 00:00:05 videos/5secode.mp4 #裁剪5秒钟视频
ffmpeg -i videos/1.mp4 -b:v 2000k -bufsize 2000k -maxrate 2500k videos/malu.mp4 # 控制码率
ffmpeg -i videos/1.mp4  -vcodec h264 videos/h264.mp4 #编码格式转换
ffmpeg -i videos/1.mp4  -vf scale=960:540 videos/960.mp4 # 将输入的1920x1080缩小到960x540输出:  960:-1将保持宽高比
ffmpeg -i videos/1.mp4  -i audios/2.jpg -filter_complex overlay videos/pic.mp4 #为视频加图片
ffmpeg -i videos/1.mp4 -ss 00:00:20 -t 10 -r 1 -q:v 2 -f image2 pics/pic-%03d.jpeg # ffmpeg会从input.mp4的第20s时间开始，往下10s，即20~30s这10秒钟之间，每隔1s就抓一帧，总共会抓10帧。
-ss 表示开始时间
-t表示共要多少时间。
-r 表示每一秒几帧
-q:v表示存储jpeg的图像质量，一般2是高质量。

ffmpeg -i videos/1.mp4 -vcodec copy -an videos/no-voice.mp4 #提取无声音视频
ffmpeg -i videos/no-voice.mp4 -vcodec mpeg4 -i audios/xusong.mp3 -acodec copy videos/test.mp4 # 嵌入视频音频
```



## 音频

```bash
ffmpeg -i videos/1.mp4 -acodec mp3 audios/1.mp3  #提取音频
```

