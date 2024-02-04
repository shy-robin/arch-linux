# 一些设置

## 修改键位

caps_lock: tap -> esc, hold -> Ctrl

> https://superuser.com/questions/566871/how-to-map-the-caps-lock-key-to-escape-key-in-arch-linux

1. 安装 caps2esc: `sudo pacman -S interception-caps2esc`
2. 创建 `/etc/interception/udevmon.yaml`, 写入：

```
- JOB: intercept -g $DEVNODE | caps2esc -m 1 | uinput -d $DEVNODE
  DEVICE:
    EVENTS:
      EV_KEY: [KEY_CAPSLOCK, KEY_ESC]
```

3. 开启并运行 udevmon:

```
sudo systemctl enable udevmon
sudo systemctl start udevmon
```
