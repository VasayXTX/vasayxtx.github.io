---
layout: post
title: Шпаргалка по работе с Virtuozzo
---

**Parallels Virtuozzo (ранее Parallels Cloud Server)** - платформа для виртуализации позволяющая создавать виртуальные машины и контейнеры.


*Вывести список контейнеров и ВМ:*

    prlctl list
    
*Старт контейнера:*

    prlctl create 101 --vmtype ct
