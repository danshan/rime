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

1\. 修改 default.custom.yaml 确定你的输入方案。按「control+` 」时出现的明月拼音、明月拼音·简化字、五笔等候选方案；
2\. 修改输入法外观 squirrel.custom.yaml；
3\. 修改输入方案配置文件，例如：明月拼音·简化字，需要修改 luna_pinyin_simp.custom.yaml ，输入方案配置文件像是一个接口文件，模糊拼音、加载扩充词库、定义一些特殊符号的直接上屏、定义个性化的翻页按键等都在这个文件里。