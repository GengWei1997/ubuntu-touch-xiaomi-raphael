# Redmi K20 Pro (raphael)

## 构建

参考官方指南：<https://docs.ubports.com/zh-cn/latest/>

## 刷机

1. 先刷卡刷 `PixelExperience_raphael-11.0-20211123-2039-OFFICIAL.zip`
2. 记得格式化 `userdata`（这个就是作为存储，可以像安卓一样格式化恢复出厂设置）

然后：

```bash
fastboot flash boot     boot.img
fastboot flash dtbo     dtbo.img
fastboot flash recovery recovery.img   # recovery直接用twrp就行，可以不用刷我这个，这是为了之后看能不能推到官方支持用来ota的
fastboot flash system   system.img

fastboot reboot
```

## 说明

- 首次开机 屏幕可能会闪几下，后面开机就不会再闪了
- 每次开机前置摄像头都会升起然后自动收回（这是因为Ubuntu Touch没有相对应的 API，我只能改成开机自动收回，拍照啥的都能自动升降）
- RNDIS连接电脑可以去设置里开启开发者模式

## 功能状态

| 组件 | 状态 |
| --- | --- |
| 启动 / initrd | ✅ 正常 |
| 显示（DRM） | ✅ 正常 |
| 触摸（`goodix`） | ✅ 正常 |
| 双击唤醒（DT2W） | ✅ 正常 |
| USB / RNDIS / SSH | ✅ 正常 |
| WiFi | ✅ 正常 |
| 热点 | ✅ 正常 |
| 蓝牙 | ✅ 正常 |
| 声音（扬声器 / 耳机 / 麦克风） | ✅ 正常 |
| 亮度 / 通知 LED / 手电筒 | ✅ 正常（手动 + 自动） |
| 相机 | ✅ 正常（拍照 / 录像 / 前后摄切换 / 闪光灯） |
| 升降前摄 | ✅ 自动随前摄升降；开机自检后会主动收回 |
| 蜂窝通信（RIL） | ✅ 双卡枚举、4G、语音/VoLTE、短信、彩信均实测通过 |
| 振动 | ✅ 正常 |
| GPS | ✅ 正常 |
| 传感器（旋转 / 接近 / 自动亮度） | ✅ 正常 |
| AppArmor | ✅ 已启用 |
| 关机 / 重启 / 离线充电 / 恢复出厂 | ✅ 实测通过 |
| 续航 / 稳定性 | ✅ 24h 续航、7 天稳定性实测通过 |
| Recovery | ✅ 官方 unified recovery（halium-14.0 ramdisk）；USB/ADB、`mount /data`、本地 OTA 全流程实测通过 |
