# 基于github action的京东自动化签到

## 介绍

> 使用NobyDa “京东多合一签到脚本”为基础，移植到github actions自动化执行。


## 触发方式
* 点亮`Star`
* 凌晨4点定时执行
*  自定义：.github/workflows/work.yaml 编辑

## 注意问题

> **问题一：[项目Fork后定时任务没有执行](https://github.com/ZHDeveloper/JD_Sign_Action/issues/3)**
> 
>>1、建议修改README.md提交，以触发定时任务。
>>
>>2、定时任务的时间是UTC时间，跟中国时间有8小时的时差。
> 
>  **问题二：京东Cookie的有效期**
> 
> >就我自己项目中的使用情况而言，一个月有效期。



## 使用用法
* 点击右上角 `Fork` 项目；
* `Settings` -> `Secrets` 中添加京东Cookie、Server酱SCKEY；
	- `JD_COOKIE`：__jda=122270672.16165728463751443612603.1616572846.1616572846.1616572846.1; __jdv=122270672%7Cdirect%7C-%7Cnone%7C-%7C1616572846376; __jdc=122270672; mba_muid=16165728463751443612603; shshshfpa=cdfc2a75-1458-9143-7023-9651496a0fba-1616572847; shshshfpb=cOmkER3xGD04MceZ0mlHzJg%3D%3D; 3AB9D23F7A4B3C9B=LO5EAOZEU2W6ZWELMH7YSOSNP2GY2DDL2KTTP5PG566TYPSNBPEJTP72PKZAVX4S53PL2J5B2UOW2SERJJJ2NVXHOU; TrackerID=fu39IJ0mawb9ppIyFXjzxho_K_-JRI0eM_ohjj1szAtJE7CIu6WMMqrmu08C9vtUOJrHdjPSu35hcV3Gi4ptd5Hv36h79a-GgYzZI3gPhJzs43wET90Zx3zksh6nyWl1iHyNo6fY1XlndEAKUbR0ow; pt_key=AAJgWvHKADCqTlO-J5BMoo6OGYgn9Lh4wEQkR3ufBHBMViW3ODO-Vf_KMcXVyiC01nOJPOufACU; pt_pin=15578483319_p; pt_token=f87bkab2; pwdt_id=15578483319_p; sfstoken=tk01m95241ad2a8sMSsyQjNnWThTdQHWL25q40+y5/LbUAkIcafimk1WDJY1xx/+T1a7DP9iQ1Jpnn6UzPCRfR0KW69/; wxa_level=1; cid=9; retina=1; jxsid=16165728757476843107; webp=1; visitkey=9738010177889830; wqmnx1=MDEyNjM5NHNtbW9uMDA1blAxayBXNUhlVjNpODYvOUZkLTJVKSY%3D; __jdb=122270672.3.16165728463751443612603|1.1616572846; mba_sid=16165728463804414847981829961.3; __wga=1616572892975.1616572892975.1616572892975.1616572892975.1.1; PPRD_P=UUID.16165728463751443612603; jxsid_s_t=1616572893128; jxsid_s_u=https%3A//home.m.jd.com/myJd/newhome.action; sc_width=375; shshshfp=28c7e1087a8befeb8242abfa4bd76ee3; shshshsID=ea69068abf8e61dd5eb1162b65619e70_2_1616572893796
	- `JD_DUAL_COOKIE`：账号2Cookie(选填)
	- `PUSH_KEY`：SCT9674TQ9YHXpWm7Ymjcx67LIXyPzVo
* 点击`Star`，任务会自动执行，运行进度和结果可以在`Actions`页面查看；
* 当任务运行完成时，会将运行结果和错误信息打包到`Artifacts`，可自行下载查看；
* 如果配置了Server酱，运行结果会推送到微信；

## 获取京东cookie

* 使用项目中的Chrome插件：`JDCookie`；
* Chrome中拓展程序开启`开发者模式`；
* 点击`加载已解压的拓展程序`，选择`JDCookie`目录；
* 登录[领京豆](https://bean.m.jd.com/)；
* 点击`JDCookie`即可拷贝京东cookie；

## 获取Server酱SCKEY

* github 授权登录[Server酱](http://sc.ftqq.com/3.version)官网；
* 菜单栏`微信推送`扫描绑定微信；
* 菜单栏`发送消息`拷贝SCKEY；



## 效果截图

![WechatIMG3](./images/WechatIMG3.jpeg)

![WechatIMG4](./images/WechatIMG4.jpeg)


## 参考项目
* [NobyDa/Script/JD-DailyBonus](https://github.com/NobyDa/Script/blob/master/JD-DailyBonus/JD_DailyBonus.js)
* [ruicky/jd-sign-bot](https://github.com/ruicky/jd_sign_bot)
* [jerrykuku/luci-app-jd-dailybonus](https://github.com/jerrykuku/luci-app-jd-dailybonus)


