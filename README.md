# Redpill_CustomBuild

## 介绍  
[Redpill_CustomBuild](https://github.com/wjz304/Redpill_CustomBuild)

## 说明  

#### title:
  - 标题请以 custom 开头（不区分大小写），且不要包含'(单引号),"(双引号) 等转义字符。
  - eg:
    - custom 918
    - Custom test
    - CUSTOM Ing 定制
  
#### body:
  - 内容 以json格式编写, 不要换行（目前处理不了换行）
  - eg:
    - {"platform":"DS3622xs+", "version":"7.0.1-42218", "jun":"1", "ext":"r8125, tg3"}
    - {"platform":"DS3622xs+", "sataportmap":"1", "diskidxmap":"10", "pid":"0xa4a5", "vid":"0x0525"}
    - {"platform":"DS3622xs+", "version":"7.1.0-42661", "sn":"1980PDN002189", "mac":"001132888A95", "ext":"r8125"}
    - {"platform":"DS3622xs+", "version":"7.0.1-42218", "jun":"1", "mac":"001132888A95, 001132888A96", "ext":"r8125, tg3"}
  
       - platform: <"DS3615xs" | "DS3617xs" | "DS918+" | "DS920+" | "DS3622xs+">    default: "DS918+"
       - version: <"7.1.0-42661" | "7.0.1-42218">    default: "7.1.0-42661"
       - sataportmap:  
       - diskidxmap:  
       - sn:  
       - mac:  多个请以 "," 间隔
       - pid:  
       - vid:  
       - ext:  多个请以 "," 间隔, [可选项](https://raw.githubusercontent.com/pocopico/rp-ext/main/exts)
       - jun: <"0" | "1">    default: "0"




## 鸣谢
https://github.com/pocopico/redpill-load  

