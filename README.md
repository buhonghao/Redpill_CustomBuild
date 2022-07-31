# Redpill_CustomBuild

## 介绍  
[Redpill_CustomBuild](https://github.com/wjz304/Redpill_CustomBuild)

[![](https://img.shields.io/github/issues-closed-raw/wjz304/Redpill_CustomBuild/custom?label=定制成功)](https://github.com/wjz304/Redpill_CustomBuild/issues?q=is%3Aissue+is%3Aclosed+label%3Acustom)
[![](https://img.shields.io/github/issues-raw/wjz304/Redpill_CustomBuild/custom?label=定制失败)](https://github.com/wjz304/Redpill_CustomBuild/issues?q=is%3Aopen+is%3Aissue+label%3Acustom)

## 说明  
方式一：  
在本项目 Issues 中创建问题，按需填写即可发起定制构建，参考示例[issues#1](https://github.com/wjz304/Redpill_CustomBuild/issues/1)  

构建成功 Issues 会自动 closed。  
构建失败 后请调整参数重新创建 Issues发起重新构建（每个 Issues 只会触发一次编译）。  
ext 存在兼容性问题, 添加是请与型号和版本对应, 并酌情添加 (不恰当的例子：r8125 不支持 DS920+ 的 7.0.1-42218 版本, 添加会编译失败)  


方式二：   
fork 本项目 通过 Actions 填写相关参数进行构建。

#### title:
标题请以 custom 开头（不区分大小写），且不要包含'(单引号),"(双引号) 等转义字符。
- eg:
  - custom 918
  - Custom test
  - CUSTOM Ing 定制
  
#### body:
内容 以json格式编写 ( 切记符号为英文符号，尤其是'[,]()'和 '["]()')

参数      | 必选  |     默认值     | 说明  
----------|------|----------------|---------
platform  | √    |"DS918+"        | "DS3615xs", "DS3617xs", "DS918+", "DS920+", "DS3622xs+"  
version   | √    |"7.1.0-42661"   | "7.1.0-42661", "7.0.1-42218", "6.2.4-25556"  
map       | ×    |-               | 控制器的盘数和盘序[格式: sataportmap, diskidxmap]. 默认无. eg: "0, 10"  
dtb       | ×    |-               | 暂不可用, 待实现.  
sn        | ×    |-               | 序列号. 默认根据型号随机生成.  
mac       | ×    |-               | 多个请以 "," 间隔. 默认根据型号随机生成. eg: "001132888A95, 001132888A96"  
usb       | ×    |"0x0001, 0x46f4"| 设备识别码（pid）和供应商ID（vid）[格式: pid, vid]. 默认无.  eg: "0xa4a5, 0x0525"  
ext       | ×    |-               | 多个请以 "," 间隔. 可选项参考: [[rp-ext](https://raw.githubusercontent.com/pocopico/rp-ext/main/exts)]. eg: "r8125, tg3"  
exp       | ×    |"pocopico"      | "pocopico", "jumkey" (大佬的抉择，7.1 优先选 pocopico, 7.0-jun 优先选 jumkey)
jun       | ×    |"0"             | 仅7.0.1-42218 版本可以选择jun模式，jun模式 支持 7.01~7.1u3 的 DSM。

- eg:
  - {"platform":"DS3622xs+", "version":"7.0.1-42218", "jun":"1", "ext":"r8125, tg3"}  
  - {"platform":"DS3622xs+", "map":"1, 10", "usb":"0xa4a5, 0x0525"}  
  - {"platform":"DS3622xs+", "version":"7.1.0-42661", "sn":"1980PDN002189", "mac":"001132888A95", "ext":"r8125"}  
  - {"platform":"DS3622xs+", "version":"7.0.1-42218", "jun":"1", "mac":"001132888A95, 001132888A96", "ext":"r8125, tg3"}  
  - {  
      "platform":"DS3622xs+",  
      "version":"7.0.1-42218",  
      "jun":"1",  
      "exp": "jumkey",  
      "mac":"001132888A95, 001132888A96, 001132888A97",  
      "ext":"r8125, r8168, e1000e, igb, vmxnet3, ixgbe"  
    }  

## 写在这里
1. 当前 7.0.1-42218 使用 jumkey库 的构建。7.1.0-42661 使用 pocopico库 构建。
2. ext 当前使用 pocopico 库。
3. 驱动默认集成 acpid, misc, virtio, dtb-static(only DS920+)。
4. SN&MAC算号使用 pocopico 的脚本。




## 鸣谢
https://github.com/RedPill-TTG/redpill-load  
https://github.com/jumkey/redpill-load  
https://github.com/pocopico/redpill-load  
https://github.com/Online24Hours/Redpill_Build  

