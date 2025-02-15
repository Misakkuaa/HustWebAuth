
===========

锐捷 WEB 认证跨平台工具


使用方法
-----------

1. 命令行运行 `HustWebAuth_linux_arm -h` 或 `HustWebAuth_linux_mips -h` 查看帮助
2. 命令行运行 `HustWebAuth_linux_arm -a account -p password` 进行认证测试

    > ### Tips:
    >
    > 1. 请确保你的账号密码正确
    > 2. 请确保你的网络连接正常, 且使用锐捷 Web 认证方式
    > 3. 可使用 `HustWebAuth -a account -p password -o` 进行认证并保存配置文件至 `$HOME` 文件夹下
    > 4. 可使用 `HustWebAuth login -r` 开启无感认证, 需提前下线你的设备
    > 5. 可使用 `HustWebAuth_linux_arm -a account -p password -s Dianxin` 学校需要选择运营商则在-s后加入运营商的标识

Help 命令
==========
```bash
> HustWebAuth -h
HustWebAuth is a program used to implement Ruijie web authentication.

Usage:
  HustWebAuth [flags]
  HustWebAuth [command]

Available Commands:
  get         Get the login url from the redirect url
  help        Help about any command
  login       Hust web auth only once
  service     System service related commands

Flags:
  -a, --account string           Account for ruijie web authentication
  -f, --config string            Config file (default is $HOME/HustWebAuth.yaml)
  -c, --cycle                    Enable cycle mode
      --cycleDuration duration   Cycle duration (default 5m0s)
      --cycleRetry int           Cycle retry times, -1 means retry forever (default 3)
  -d, --daemon                   Enable daemon mode, not support windows
      --daemonPidFile string     Daemon pid file
  -e, --encrypt bool             Password is encrypted or not(default false)
  -h, --help                     help for main.exe
      --logAppend                Log file append mode.
                                 NOTE: if logRandom is true, it will be ignored (default true)
      --logConnected             Enable logging of "The network is connected" (default true)
      --logDir string            Log Directory (default Temp/HustWebAuth)
  -l, --logFile string           Log file name (default means output to os.stdout)
      --logRandom                Log file name with random string.
                                 NOTE: If logFile includes a "*", the random string replaces the last "*".
                                  (default true)
  -p, --password string          Password for ruijie web authentication
      --pingCount int            ping count (default 3)
      --pingIP string            IP address to ping (default "202.114.0.131")
      --pingPrivilege            Sets the type of ping pinger will send.
                                 false means pinger will send an "unprivileged" UDP ping.
                                 true means pinger will send a "privileged" raw ICMP ping.
                                 NOTE: setting to true requires that it be run with super-user privileges.
                                  (default true)
      --pingTimeout duration     Ping timeout (default 3s)
      --redirectURL string       Redirect URL (default "http://123.123.123.123")
  -o, --save                     Save config file
  -s, --serviceType string       Service Type, options: [internet, local] (default "internet")
      --syslog                   Enable syslog, not support windows

Use "HustWebAuth [command] --help" for more information about a command.
```

Service Help 命令
=================
```bash
> HustWebAuth service -h
Use HustWebAuth as a system service: install, start, stop, uninstall, etc.

Usage:
  HustWebAuth service [flags]
  HustWebAuth service [command]

Available Commands:
  install     Install HustWebAuth service
  restart     Restart HustWebAuth service
  start       Start HustWebAuth service
  status      Get HustWebAuth service status
  stop        Stop HustWebAuth service
  uninstall   Uninstall HustWebAuth service from system

Flags:
  -h, --help   help for service

Use "HustWebAuth service [command] --help" for more information about a command.
```
