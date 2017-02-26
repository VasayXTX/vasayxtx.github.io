---
layout: post
title: Шпаргалка по работе с Virtuozzo
---

**Parallels Virtuozzo (ранее Parallels Cloud Server)** - платформа для виртуализации, позволяющая создавать виртуальные машины и контейнеры.

*Отобразить конфигурация Virtuozzo:*
    
    prlsrvctl info

*Вывести список контейнеров и ВМ:*

    prlctl list # Только запущенные
    prlctl list -a # Все
    prlctl list -i # Детали по всем контейнерам
    prlctl list -i MyCT # Детали по контейнеру с именем MyCT
    
*Вывод списка ОС-шаблонов:*
    
    vzpkg list --with-summary 
    
*Создание контейнера c именем MyCT:*

    prlctl create MyCT --vmtype ct # На базе дефолтного шаблона 
    prlctl create MyCT --vmtype ct --ostemplate centos-7-x86_64
    
*Вывод статуса, старт, стоп и рестарт контейнера и ВМ:*

    prlctl status MyCT 
    prlctl start MyCT
    prlctl stop MyCT
    prlctl restart MyCT
    
*Выполнить команду внутри контейнера:*

    prlctl exec MyCT whoami # root
    
*Конфигурирование контейнера:*
    
    prlctl set MyCT --netif_add eth0 # Добавление сетевого интерфейса
    prlctl set MyCT --ifname eth0 --dhcp yes # Включение dhcp на сетевом интерфейсе
    prlctl set MyCT --memsize 1G # Выделение 1gb оперативной памяти
    prlctl set MyCT --swappages 512M # Выделение 512mb swap'а
    
*Вывод списка сетей:*
    
    vznetcfg net list

*Список NIC/VLAN/bridge интерфейсов:*

    vznetcfg if list

*Управление лицензией:*
    
    vzlicview # Вывод данных об установленной лицензии
    vzlicload -p <key_or_code>
    vzlicload -f <license_file>
    
*Удаление контейнера или ВМ (перед этим он должен быть остановлен):*

    prlctl delete MyCT
