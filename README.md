# sphinx_tabs_selector
基于sphinx_tabs插件创建，支持sphinx所支持的格式。由于tabs在html展示，可以通过点击tab切换，但是生成某些特定格式，不支持这种切换。
例如，生成pdf。而本插件，就是用于选择指定的sphinx tab的内容，便于sphinx生成非html格式的内容。

## 安装
```bash
pip install sphinx-tabs-selector
```
## 使用

在conf.py中添加以下配置
```python
extensions = [
    ...
    'sphinx_tabs_selector.selector',
    ... 
]

# 这里用来配置，需要选择的tabs，如果不配置该项，该插件将不起作用
# 配置项为一个列表，列表中的每个元素为一个字符串，字符串为需要选择的tab的名称，如果涉及到的tab是嵌套的，则需要将一路嵌套下来的tab名，都写上
tabs_selector = ["tab1_name","tab2_name","tab3_name"]
```
在rst文件中tabs的写法可以参照sphinx_tabs插件的说明。

## 注意
1. 必须在conf.py中添加tabs_selector配置，否则插件不会生效。因此,可以使用tabs_selector配置来控制插件的生效。
2. 如果conf.py的extensions中同时添加了sphinx_tabs插件和sphinx_tabs_selector插件，那么sphinx_tabs_selector插件想起作用的话,必须加在sphinx_tabs之后。
3. 如果conf.py中没有添加sphinx_tabs插件，sphinx_tabs_selector插件也是单独可以使用的。