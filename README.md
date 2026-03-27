# 橙 狐 (OFRP) for Redmi K30 至尊纪念版
适用于橙狐安卓12,14分支  
====================================================
# 目前进度
刚开始研究喵
# 如何使用
请自备[fastboot工具](https://developer.android.google.cn/studio/releases/platform-tools?hl=zh-cn)，手动重启手机至bootloader模式（橙色fastboot字样）  
把rec镜像刷入rec分区，重启进入rec，命令：  
```bash
fastboot flash recovery （所编译出的文件名称）
fastboot reboot recovery
```
温馨提示：mtk机型刷recovery有风险，如果错误的刷入未经验证的recovery可能会导致设备无法开机，无限重启，且无法进入recovery和fastboot，请先确保你有救回的办法再尝试  
可从mi rom 下载线刷包来作为恢复方案，注意不要选到 flash and lock
请根据你手机当前运行rom的安卓版本选择recovery，使用安卓12-14版本rom的手机，请刷入近期的橙狐；早期版本和文件名有写a11的版本，只能在运行安卓11版本rom的手机上刷；wzsx150 twrp只支持安卓10。  
# 如何构建
利用Github Action在线编译橙狐  
例如你的 Github 用户名是 "Neko"  
1. 打开[橙狐Action编译器](https://github.com/ymdzq/OrangeFox-Action-Builder)仓库，然后在新页面点击右上角的`Fork`按钮  
![image](https://user-images.githubusercontent.com/37921907/177914706-c92476c5-7e14-4fb3-be94-0c8a11dae874.png)
2. 等待网页自动重定向后，你将会看到你的用户名下的新仓库  
![image](https://user-images.githubusercontent.com/37921907/177915106-5bde6fc9-303c-479e-b290-22b48efd1e4e.png)
3. 网页上方进入 `Actions` 页面 > `All workflows` > `OrangeFox - Build` > `Run workflow`  
![image](https://user-images.githubusercontent.com/37921907/177915304-8731ed80-1d49-48c9-9848-70d0ac8f2720.png)
4. 按照以下内容填写参数  
OrangeFox Branch  
`12.1` / `14.1`  
Custom Recovery Tree  
`https://github.com/PomuSanza/ofrp_device_xiaomi_cezanne`  
Custom Recovery Tree Branch  
`fox_12.1` / `fox_14.1`  
Specify your device path.  
`device/xiaomi/cezanne`  
Specify your Device Codename.  
`cezanne`  
Specify your Build Target  
`recovery`  
![image](https://user-images.githubusercontent.com/37921907/177915346-71c29149-78fb-4a00-996f-5d84ffc9eb8c.png)
5. 填写完毕后, 点击 "Run workflow" 开始运行
6. 编译结果可以在你Fork后的新仓库的Release页面下载
