---
layout: post
title:  "Как настроить таймзону в Jekyll"
date:   2015-09-07 22:11:00 +0300
categories: Complicated
---

Решил настроить тайм зону в Jekyll. В документации описана простая настройка в [_config.yml](http://jekyllrb.com/docs/configuration/):

> timezone: "Europe/Moscow"

В итоге пост с датой

> date:   2015-09-06 22:22:00

попал в папку 2015/09/**07**

Проблема решилась явным указанием тайм зоны. Причем с минутами:

> date:   2015-09-06 22:22:00 +0300

Теперь дата выглядит так:

> {{ post.date | date_to_xmlschema }}

Есть предположение, что Jekyll GitHub Pages по умолчанию подхватывает тайм зону сервера.