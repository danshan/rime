# Rime

---

个人使用的 rime 配置.

支持如下特性: 

1\. 使用微软双拼作为常用中文输入法.

输入法外观和特性的几个文件：

* squirrel.custom.yaml, 自定义皮肤.

* default.custom.yaml, 设定备选词数量, 定义输入方案.

* luna_pinyin_simp.custom.yaml, 定义扩充词库 / 加载符号库 / 模糊拼音. 明月拼音·简化字输入方案配置文件, 明月拼音对应的文件是 luna_pinyin.custom.yaml.

* installation.yaml，用来同步配置的文件信息, 比如 dropbox 或者 坚果云.

> 以上几个以 .custom.yaml 作为后缀的文件, 是以补丁的方式来实现个性化定制, 输入法后续升级不会覆盖这些文件. 
> 自定义文件配置中起始部分都会有patch: 字段, 每个配置文件中有且只需要一行这个代码.

## 扩展词库文件

> 扩展词库文件被修改后需要 `重新部署` 才能生效.

1\. 修改 default.custom.yaml 确定你的输入方案。按「control+` 」时出现的明月拼音、明月拼音·简化字、五笔等候选方案
2\. 修改输入法外观 squirrel.custom.yaml
3\. 修改输入方案配置文件，例如：明月拼音·简化字，需要修改 luna_pinyin_simp.custom.yaml ，输入方案配置文件像是一个接口文件，模糊拼音、加载扩充词库、定义一些特殊符号的直接上屏、定义个性化的翻页按键等都在这个文件里。


### squirrel.custom.yaml

输入法外观设定是在 [梁海](https://zhuanlan.zhihu.com/p/19599206?columnSlug=lianghai) 方案的基础上修改的, 并参照了系统输入法的配色和字体.
候选词条中如果出现生僻字无法显示 (显示为框问号), 可以在方案配色的字体指向上加一个 `[花园明朝](http://fonts.jp/hanazono/)` 字体(需单独 [下载](http://fonts.jp/hanazono/) 并 [安装](https://zh.osdn.net/projects/hanazono-font/howto/install) 字体).

```yaml
patch:
  show_notifications_via_notification_center: true
  show_notifications_when: appropriate  # 状态通知，适当(appropriate)，开（always）关（never）

  style:
    color_scheme: apathy 
    font_point: 18
    #horizontal: true

  preset_color_schemes:
    apathy:
      name: "Apathy"
      author: "Dan"

      # horizontal: true
      inline_preedit: true # 单行模式
      #candidate_format: "%c\u2005%@\u2005" # 用 1/6 em 空格 U+2005 来控制编号 %c 和候选词 %@ 前后的空间。

      corner_radius: 5 #候选条圆角
      border_height: 0
      border_width: 0
      back_color: 0xFFFFFF #候选条圆角

      #font_face: "Lucida Grande"
      font_face: "PingFangSC-Regular,H-SiuNiu"  #候选词字体
        # 我的系统简中字体已设定为冬青黑体；
        # 此处设定西文字体让它自动回退，以免候选词里的西文用中文字体显示。
      font_point: 16  #候选字词大小
      text_color: 0x424242  #高亮选中词颜色

      #label_font_face: "Lucida Grande"
      label_font_face: "PingFangSC-Light"   #候选词编号字体
      label_font_point: 12   #候选编号大小
      
      hilited_candidate_text_color: 0xEE6E00  #候选文字颜色
      hilited_candidate_back_color: 0xFFFFEF  #候选文字背景色
      comment_text_color: 0x999999  #拼音等提示文字颜色
```