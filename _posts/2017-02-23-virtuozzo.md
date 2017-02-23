---
layout: post
title: Шпаргалка по работе с Virtuozzo
---

**Parallels Virtuozzo (ранее Parallels Cloud Server)** - платформа для виртуализации позволяющая создавать виртуальные машины и контейнеры.

*Отобразить конфигурация Virtuozzo:
    
    prlsrvctl info

*Вывести список контейнеров и ВМ:*

    prlctl list # Только запущенных
    prlctl list -a # Всех
    
*Вывод списка ОС-шаблонов:*
    
    vzpkg list --with-summary 
    
*Создание контейнера c именем 101:*

    prlctl create 101 --vmtype ct # На базе дефолтного шаблона 
    prlctl create 101 --vmtype ct --ostemplate centos-7-x86_64
    
*Старт, стоп и рестарт контейнера и ВМ:*
    
    prlctl start 101
    prlctl stop 101
    prlctl restart 101
    
*Добавление сетевого интерфейса:*

    prlctl set 101 --netif_add eth0

*Включение dhcp на сетевом интерфейсе:*

    prlctl set 101 --ifname eth0 --dhcp yes

Вывод списка сетей:
    
    vznetcfg net list

Список NIC/VLAN/bridge интерфейсов:

    vznetcfg if list

*Управление лицензией:*
    
    vzlicview # Вывод данных об установленной лицензии
    vzlicload -p <key_or_code>
    vzlicload -f <license_file>
