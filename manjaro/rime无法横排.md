### rime输入法无法横排

1. 创建空白文件:
   `~/.config/ibus/rime/build/ibus_rime.yaml`
2. 向 ibus_rime.yaml 写入并保存以下内容:

```
style:
   horizontal: true
```