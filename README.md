# py-ios-device

A python based Apple instruments protocol，you can get CPU, Memory and other metrics from real iOS devices

win，mac 跨平台方案，通过 Instruments 私有协议获取 iOS 相关性能指标数据。

相关文章链接:https://testerhome.com/topics/27159


### unix 模拟 socat 测试代理工具，debug 时使用
unix_socket.py 该工具可以模拟类似 socat 的一个简单的 unix socket 代理工具，用于中间人劫持获取数据包， iOS 与 usbmuxd 交互过程中，将数据包自动转换成明文数据。
使用方式：
```
1.sudo chmod 777 /var/run/
2.sudo  mv /var/run/usbmuxd /var/run/usbmuxx
3.python /tools/unix_socket.py
4.恢复  sudo  mv /var/run/usbmuxx /var/run/usbmuxd

```



### demo 演示 sysmontap.py 
```
[
    {
        "PerCPUUsage": [
            {
                "CPU_NiceLoad": 0.0,
                "CPU_SystemLoad": -1.0,
                "CPU_TotalLoad": 11.881188118811878,
                "CPU_UserLoad": -1.0
            },
            {
                "CPU_NiceLoad": 0.0,
                "CPU_SystemLoad": -1.0,
                "CPU_TotalLoad": 17.0,
                "CPU_UserLoad": -1.0
            }
        ],
        "EndMachAbsTime": 656566442146,
        "CPUCount": 2,
        "EnabledCPUs": 2,
        "SystemCPUUsage": {
            "CPU_NiceLoad": 0.0,
            "CPU_SystemLoad": -1.0,
            "CPU_TotalLoad": 28.881188118811878,
            "CPU_UserLoad": -1.0
        },
        "Type": 33,
        "StartMachAbsTime": 656542341717
    },
    {
        "Processes": {
            "351": [
                351,            // pid 
                417710325760,   // memVirtualSize
                770048,         // memResidentSize
                0.0,            // cpuUsage
                528,
                -82,            
                934232,         // physFootprint
                819200,         // memAnon
                0.0,            // powerScore
                708608          // diskBytesRead
            ],
            "519": [
                519,
                418581921792,
                46628864,
                13.8574323237612,
                30281,
                6465,
                61965152,
                20381696,
                14.082756426586586,
                57790464
            ],
            "311": [
                311,
                417748434944,
                6635520,
                0.0,
                10189,
                43,
                1671552,
                1540096,
                0.0,
                22274048
            ],
            "271": [
                271,
                417744961536,
                4718592,
                0.0,
                8188,
                473,
                2130344,
                1998848,
                0.0,
                36442112
            ]
        },
        "Type": 5,
        "EndMachAbsTime": 656567535862,
        "StartMachAbsTime": 656542716738
    }
]
```
