---
layout: post
title: Шпаргалка по работе с Virtuozzo
---

**Parallels Virtuozzo (ранее Parallels Cloud Server)** - платформа для виртуализации позволяющая создавать виртуальные машины и контейнеры.


*Вывести список всех контейнеров и ВМ:*

    prlctl list
    
*Создание контейнера c именем 101 на основании дефолтного шаблона:*

    prlctl create 101 --vmtype ct
