# rust minigrep

## 一、概述

使用rust编写的迷你grep工具，可以用来查询文件中的匹配输入字符串的文本行。

## 二、构建与使用

### 2.1 构建

```bash
# 构建
cargo build --release
# 拷贝到系统
sudo mv target/release/minigrep /usr/local/bin
```

### 2.2 简易使用

```bash
minigrep <query> <filename>
```

### 2.3 大小写敏感

如果希望针对输入字符串不区分大小写，可以使用设置`CASE_INSENSITIVE`环境变量，不关心值，只要设置即可。

```bash
export CASE_INSENSITIVE=1
```

如果想撤回，删除掉环境变量即可。

```bash
unset CASE_INSENSITIVE
```
