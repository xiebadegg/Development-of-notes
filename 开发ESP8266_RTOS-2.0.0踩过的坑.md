# 开发ESP8266_RTOS-2.0.0踩过的坑

## 1.使用cJSON遇到的坑

### 1.1 cJSON引用math.h报错

#### 1.1.1 问题描述

- 在使用JSON.c时发现编译报错

```  undefine 'pow'
undefine 'pow'
```

- 上网搜了一波解决办法后，发现cjson.c引用了math.h，在gcc中，需要使用-lm链接math库文件方可使用。

#### 1.1.2 解决办法

求教官方后获知可在makefile在 makefile 中将 -lminic 改为 -lcirom，再加上 -lmirom

