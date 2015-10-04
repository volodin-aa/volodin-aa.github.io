---
layout: post
title:  "Редис на подоконнке"
date:   2015-10-04 23:13:00 +0300
categories: Chaotic
---

Очень было любытно, на сколько проседает производительность редиса в виртуальной машине по сравнению с запуском в реальной системе.

Для этого на Windows 10 установил [Redis-x64-2.8.2103](https://github.com/MSOpenTech/redis/releases) (актульную на данный момент версию редиса для винды). Сравнивал с Redis 2.8.22 во [многопоточном контейнере докера](/obvious/2015/10/04/tweak-docker-toolbox.html). Процессор все тот же [Intel® Core™ i7-3610QM](http://ark.intel.com/ru/products/64899)

Вот что у меня получилось:

![Падение производительности редиса в Windows 10](/files/redis-on-the-windowsill/vm-win.png "Сравнение производительности Redis 2.8 в Docker VM и Windows 10")

"Нормализованные" результаты:

![Падение производительности редиса в Windows 10](/files/redis-on-the-windowsill/vm-norm.png "Нормализаванное сравнение производительности Redis 2.8 в Docker VM и Windows 10")

Как видно редиска плохо растет на подоконнике. Redis 2.8 в Windows в 1,2-1,5 раза медленнее редиса в виртуальной машине, да еще в контейнере докера. 

P.S. Файлы результатов тестов:

1. [1 ядро](/files/tweak-docker-toolbox/redis-benchmark-2.8-docker-1-thread.txt)
2. [4 ядра](/files/tweak-docker-toolbox/redis-benchmark-2.8-docker-4-thread.txt)
3. [Windows 10](/files/tweak-docker-toolbox/redis-benchmark-2.8-win.txt)