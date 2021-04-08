# Rime 自用设置
## 皮肤截图
![GSyDz7sZP5nO3jY](https://github.com/li4li/rime_theme/blob/main/rime%E7%9A%AE%E8%82%A4%E9%85%8D%E8%89%B2%E6%96%B9%E6%A1%88.png)

## 词库配置文件
下载并解压 [配置文件](https://github.com/li4li/rime_theme/blob/main/%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6.rar) 。

点选**用户文件夹**打开 Rime 目录文件夹，将【配置文件】里所有文件粘贴进去，并选择覆盖。

> 注意：覆盖前建议先备份原文件。

点击**重新部署**完成配置。

> 注1：修改任何配置文件都要**重新部署**才会生效（快捷键 `Control+Option+｀`）。
>
> 注2：搜狗词库较大，重新部署时间会稍长，请耐心等待。

##自定义设置
###翻页
示例：逗号` <`和句号` >`翻页。

1. 打开 ` default.custom.yaml`，修改 `key_binder/bindings` 。

2. 如下所示。

```
   key_binder/bindings: # 翻页  minus/减号，equal/等号，comma/逗号，period/句号，exclam/感叹号，numbersign/井号，percent/百分号，semicolon/分号，apostrophe/单引号
    - { when: composing, accept: ISO_Left_Tab, send: Page_Up }  # "tab"翻页
    - { when: composing, accept: Shift+Tab, send: Page_Up }
    - { when: composing, accept: Tab, send: Page_Down }     
    - { when: paging, accept: minus, send: Page_Up }            # "-"上一页
    - { when: has_menu, accept: equal, send: Page_Down }        # "="下一页
    - { when: paging, accept: comma, send: Page_Up }            # "<"上一页
    - { when: has_menu, accept: period, send: Page_Down }       # ">"下一页
```
###皮肤
示例：荧光` yingguang`皮肤。

1. 打开 ` weasel.custom.yaml`，修改 `style/color_scheme` 后面的皮肤名为 `yingguang` 。

2. 如下所示。

```
patch:
  "us_keyboard_layot": true
  "style/display_tray_icon": true
  "style/horizontal": true                    # 水平排列
  "style/inline_preedit": true                # 单行显示，false双行显示
  #"style/font_face": "PingFangSC"            # 候选词编号字体 显示不对
  "style/font_face": "Microsoft YaHei"        # 不是很喜欢雅黑但没办法
  "style/font_point": 13                      # 候选文字大小
  #"style/label_font_point": 10               # 候选编号大小 不生效，想必跟鼠须管不同的原因
  "style/layout/candidate_format": "%c\u2005%@"      # 用 1/6 em 空格 U+2005 来控制编号 %c 和候选词 %@ 前后的空间
  "style/layout/border_height": 2             # 窗口上下高度
  "style/layout/border_width": 2              # 窗口左右宽度
  "style/layout/border_color_width": 0        # 输入条边框宽度
  "style/laout/corner_radius": 5              # 候选条圆角
  "style/layout/hilited_corner_radius": 5     # 高亮圆角
  # 修改后面的名字更换皮肤
  "style/color_scheme": yingguang             # 荧光 
```

详细方案参考：[这里](https://github.com/maomiui/rime) 或者 [这里](https://xinlu.ink/tech/rime.html) (翻页参考)
