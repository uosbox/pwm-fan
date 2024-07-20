# pwm-fan

#### 介绍
这是一个用ash（bash、sh）编写的类pwm调速风扇的脚本
唯一依赖usleep命令，busybox有提供usleep命令，若是没有
可以从https://git.kos.org.cn/k/usleep下载编译就是了
效果不错
#### 原理
pwm调速（dc调速） 实际是不断的开关电源
调速就是控制开与关之间的间隔时间
所以这里必须用到usleep 微米级别的休眠命令

风扇只需要2pin（正极、负极）


#### 软件架构
本脚本理论上兼容所有Linux 系统
只要能找到gpio控制的插座都可以使用


#### 安装教程

1.  安装busybox,并且执行busybox usleep 看是否有命令支持![检测是否支持usleep](https://foruda.gitee.com/images/1721464810053885731/1525acdf_800143.png "QQ截图20240720163940.png")
或者用这个https://git.kos.org.cn/k/usleep
2.  将本脚本（pwm_fan）复制到设备目录/bin 下面
3.  然后执行 `chmod +x /bin/pwm_fan`

#### 使用说明
1.这里修改需要控制风扇的gpio
![修改控制的gpio](https://foruda.gitee.com/images/1721465196982533932/9f057131_800143.png "QQ截图20240720164426.png")
  下图是tpm312板子的示例
![tpm312板子示例](https://foruda.gitee.com/images/1721465306947108847/d82e7bd8_800143.png "QQ截图20240720164612.png")
2.  直接终端执行 `pwm_fan`即可
3.  开启自启 可以把`pwm_fan`命令放到/etc/rc.local里面 


#### 特技

1.  本脚本由https://LaJiLao.Top 提供

