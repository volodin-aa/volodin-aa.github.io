---
layout: post
title:  "Уменьшаем фрагментацию памяти Linux"
date:   2018-09-14 12:45:00 +0300
categories: Complex
---

Дано: компьютер с Ubuntu Linux 16.04

Цель: уменьшить фрагментацию памяти

Для этого записываем в переменную окружения MALLOC_ARENA_MAX количество
потоков процессора. По умолчанию система использует значение 8 * количество
потоков, что может привести к излишней фрагментации памяти 
[Consider lowering MALLOC_ARENA_MAX to prevent native memory OOM](https://github.com/prestodb/presto/issues/8993)

В файле /etc/environment

```
$ sudo vim /etc/environment
```

добавляем значение переменной окружения

```
MALLOC_ARENA_MAX=4
```
