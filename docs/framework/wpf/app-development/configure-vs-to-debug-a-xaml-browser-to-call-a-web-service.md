---
title: "Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "настройка Visual Studio для отладки приложений браузера XAML [WPF]"
  - "настройка Visual Studio для отладки XBAP [WPF]"
  - "отладка исключений безопасности для XBAP [WPF]"
  - "отладка XBAP, вызывающих веб-службу [WPF]"
  - "исключение безопасности для XBAP [WPF], отладка"
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] выполняется в изолированной среде безопасности частичного доверия, ограниченной множеством разрешений зоны Интернет.  Этот набор разрешений вызовы веб\-служб до веб\-служб, расположенных на исходном узле приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  При отладке [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] из [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], считается, что он не имеет тот же исходный узел, на который ссылается веб\-служба.  Это служит причиной возникновения исключений безопасности, если [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] пытается вызвать веб\-службу.  Однако, проект [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] может быть настроен для имитации того же исходного узла, как для веб\-службы, которую он вызывает в процессе отладки.  Это позволяет [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] безопасно вызвать веб\-службу, не вызывая исключения безопасности.  
  
## Настройка Visual Studio  
 Чтобы настроить [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] для отладки [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], который вызывает веб\-службу:  
  
1.  Выбрав проект в **обозревателе решений**, в меню **Проект** выберите пункт **Свойства**.  
  
2.  В **Конструкторе проектов** перейдите на вкладку **Отладка**.  
  
3.  В разделе **Действия при запуске** выберите **Запуск внешней программы** и введите следующую команду:  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  В разделе **Параметры запуска** введите в текстовое поле **Аргументы командной строки** следующее:  
  
     `-debug`  *filename*  
  
     Значением *имя\_файла* для параметра **\-debug** является имя XBAP\-файла; например:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  Это конфигурация по умолчанию для решений, созданных с помощью шаблона проекта [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] в среде [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)].  
  
1.  Выбрав проект в **обозревателе решений**, в меню **Проект** выберите пункт **Свойства**.  
  
2.  В **Конструкторе проектов** перейдите на вкладку **Отладка**.  
  
3.  В разделе **Параметры старта** добавьте следующий параметр командной строки к текстовому полю **аргументы командной строки**:  
  
     `-debugSecurityZoneURL`  *URL\-адрес*  
  
     Значение *URL* для параметра **\-debugSecurityZoneURL** равно [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] для места, которое будет назначено исходным узелом приложения.  
  
 Например, рассмотрим [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], использующий веб\-службу с помощью следующих [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 Исходный узел [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для этой веб\-службы выглядит следующим образом:  
  
 `http://services.msdn.microsoft.com`  
  
 Следовательно, полный параметр командной строки **\-debugSecurityZoneURL** и значение выглядят так:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## См. также  
 [Ведущее приложение WPF \(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)