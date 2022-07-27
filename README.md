# Redpill_CustomBuild

## 介绍  
[Redpill_CustomBuild](https://github.com/wjz304/Redpill_CustomBuild)

## 说明  
在 Issues 创建问题，按需填写即可 参考示例[issues#1](https://github.com/wjz304/Redpill_CustomBuild/issues/1)  
构建成功 会自动 closed  
构建失败 目前不会有通知  
ext 存在兼容性问题, 添加是请与型号和版本对应, (比如r8125 不支持 DS920+ 的 7.0.1-42218 版本, 添加会编译失败)


#### title:
标题请以 custom 开头（不区分大小写），且不要包含'(单引号),"(双引号) 等转义字符。
- eg:
  - custom 918
  - Custom test
  - CUSTOM Ing 定制
  
#### body:
内容 以json格式编写

参数        | 必选  |    默认值   | 说明  
------------|------|-------------|---------
platform    | √    |"DS918+"     | "DS3615xs", "DS3617xs", "DS918+", "DS920+", "DS3622xs+"  
version     | √    |"7.1.0-42661"| "7.1.0-42661", "7.0.1-42218" 
sataportmap | ×    |-            | 控制器的盘数. 默认无.  
diskidxmap  | ×    |-            | 控制器的盘序. 默认无.  
sn          | ×    |-            | 序列号. 默认根据型号随机生成.  
mac         | ×    |-            | 多个请以 "," 间隔. 默认根据型号随机生成. eg: "001132888A95, 001132888A96"  
pid         | ×    |"0x0001"     | 磁盘 pid. eg: "0xa4a5"  
vid         | ×    |"0x46f4"     | 磁盘 vid. eg: "0x0525"  
ext         | ×    |-            | 多个请以 "," 间隔. 可选项参考: [[rp-ext](https://raw.githubusercontent.com/pocopico/rp-ext/main/exts)]. eg: "r8125, tg3"
jun         | ×    |"0"          | 7.0.1-42218 版本的jun模式 支持 7.01~7.1u3 的 DSM。

- eg:
  - {"platform":"DS3622xs+", "version":"7.0.1-42218", "jun":"1", "ext":"r8125, tg3"}
  - {"platform":"DS3622xs+", "sataportmap":"1", "diskidxmap":"10", "pid":"0xa4a5", "vid":"0x0525"}
  - {"platform":"DS3622xs+", "version":"7.1.0-42661", "sn":"1980PDN002189", "mac":"001132888A95", "ext":"r8125"}
  - {"platform":"DS3622xs+", "version":"7.0.1-42218", "jun":"1", "mac":"001132888A95, 001132888A96", "ext":"r8125, tg3"}

## 鸣谢
https://github.com/RedPill-TTG/redpill-load  
https://github.com/jumkey/redpill-load  
https://github.com/pocopico/redpill-load  
https://github.com/Online24Hours/Redpill_Build  

