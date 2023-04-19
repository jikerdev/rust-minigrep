# rust minigrep

## 一、概述

使用rust编写的迷你grep工具，可以用来查询文件中的匹配输入字符串的文本行，默认大写敏感。

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

## 三、可优化的功能

- 目前大小写是否敏感是使用环境变量来控制的，可以考虑使用命令行参数来控制
- 目前大小写设定为不敏感时，只对输入字符串不敏感，并将输入参数都转化为小写，对文件内容仍然是敏感的，可以考虑对文件内容也不敏感
- 可以支持多文件查询，目前只支持单文件查询
- 可以支持正则表达式查询，目前只支持字符串查询
