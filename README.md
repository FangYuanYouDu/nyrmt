关于使用you-get的实践
------------------

- 使用you-get下载B站非会员视频
 ~ 当遇到长列表视频从某P下载error的解决方案
 ~ 例如：
 **you-get -l -o D:\es --format=dash-flv https://www.bilibili.com/video/av77345745**
    一共141P 但是下载的时候从P58发生error
    这时，我们需要下载P58~P141；并不需要前边的部分
    - 百度：**https://blog.csdn.net/tortelee/article/details/81630948** 找到：``` for /l %x in (2, 1, 100) do echo hello%x ``` 命令;
    这个命令的意思是for循环，变量为2，每次加1，循环到100为止。do echo hello%x意思是do something：做~输出hello加上变量
    - 修改为：``` for /l %x in (58, 1, 141) do you-get -o D:\es --format=dash-flv https://www.bilibili.com/video/av77345745?p=%x```
