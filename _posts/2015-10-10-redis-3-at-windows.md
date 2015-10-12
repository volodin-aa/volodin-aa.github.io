---
layout: post
title:  "Три редиски под окном"
date:   2015-10-11 20:44:00 +0300
categories: Chaotic
---

Не удержался, сравнил свежие версии Redis 3.0 под Docker и Windows 10.

##Тестовая кофигурация
1. Windows 10: [Redis-x64-3.0.300-alpha3](https://github.com/MSOpenTech/redis/releases) (C:\Program Files\Redis>redis-server.exe --maxheap 768m)
2. Docker: [Redis 3.0.3](https://hub.docker.com/_/redis/) во [многопоточном контейнере докера](/obvious/2015/10/04/tweak-docker-toolbox.html). 
3. Процессор все тот же: [Intel® Core™ i7-3610QM](http://ark.intel.com/ru/products/64899)

## Результаты

Без комментариев:

![Падение производительности Redis 3.0 в Windows 10](/files/redis-3-at-windows/redis-3.png "Docker Redis 2.8, Docker Redis 3.0.3 и Windows 10 Redis 3.0")

"Нормализованные" результаты:

![Нормализаванное сравнение Docker Redis 3.0 в Windows 10](/files/redis-3-at-windows/redis-3-norm.png "Нормализаванное сравнение Docker Redis 2.8, Docker Redis 3.0.3 и Windows 10 Redis 3.0")

##P.S. Файлы результатов тестов:
1. C:\Program Files\Redis>redis-benchmark.exe > [d:\redis-benchmark-3-win.txt](/files/redis-3-at-windows/redis-benchmark-3-win.txt)
2. redis-benchmark > [redis-benchmark-3-win.txt](/files/redis-3-at-windows/redis-benchmark-3-docker.txt)