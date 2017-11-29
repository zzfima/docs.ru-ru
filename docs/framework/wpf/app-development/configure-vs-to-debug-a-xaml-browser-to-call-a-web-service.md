---
title: "Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5db89cf6220f086d2d71b99f3e6440e584d6a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]Запустите в изолированной среде безопасности частичного доверия, которая ограничена набором разрешений зоны Интернета. Этот набор разрешений вызовы веб-службы для веб-служб, которые можно найти в папке [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] исходного узла приложения. Когда [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] отладке из [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], хотя не считается имеют тот же исходный узел веб-служба ссылки. Это причины исключения системы безопасности, вызываемого при [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] пытается вызвать веб-службы. Тем не менее [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] проекта можно настроить для имитации того же исходный узел веб-служба вызывается во время отладки. Это позволяет [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] безопасно вызвать веб-службу, не вызывая исключения безопасности.  
  
## <a name="configuring-visual-studio"></a>Настройка Visual Studio  
 Чтобы настроить [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] для отладки [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , которая вызывает веб-службы:  
  
1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.  
  
2.  В **конструктора проектов**, нажмите кнопку **отладки** вкладки.  
  
3.  В **действие при запуске** выберите **запуск внешней программы** и введите следующее:  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  В **параметры запуска** введите следующий текст в **аргументы командной строки** текстовое поле:  
  
     `-debug`  *Имя файла*  
  
     *Filename* значение для **-Отладка** параметр является XBAP-файла, например:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  Это конфигурация по умолчанию для решений, созданных с помощью [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] шаблона проекта.  
  
1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.  
  
2.  В **конструктора проектов**, нажмите кнопку **отладки** вкладки.  
  
3.  В **параметры запуска** добавьте следующий параметр командной строки для **аргументы командной строки** текстовое поле:  
  
     `-debugSecurityZoneURL`  *URL*  
  
     *URL-адрес* значение для **- debugSecurityZoneURL** параметр [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] для расположения, которое требуется имитировать как узлу приложения.  
  
 Например, рассмотрим [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , использует веб-службы со следующими [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 Исходный узел [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для этого веб-служба является:  
  
 `http://services.msdn.microsoft.com`  
  
 Следовательно, полный **- debugSecurityZoneURL** параметр командной строки и значением является:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a>См. также  
 [Основное приложение WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
