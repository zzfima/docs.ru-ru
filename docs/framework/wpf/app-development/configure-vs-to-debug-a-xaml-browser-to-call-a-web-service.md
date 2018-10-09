---
title: Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 182ceb96385bdca74d1d5c20079f78fe589982cf
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873207"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] Запустите в изолированной среде безопасности частичного доверия, ограниченной набором разрешений зоны Интернета. Этот набор разрешений вызовы веб-службы для веб-служб, расположенных в [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] исходном узле приложения. Когда [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] отладке из Visual Studio 2005, однако не считается имеют тот же исходный узел веб-служба ссылки. Исключения безопасности этой причины, вызываемого при [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] пытается вызвать веб-службы. Тем не менее Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] проекта можно настроить для имитации того же исходного узла как веб-службу, он вызывает во время отладки. Это позволяет [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] безопасно вызвать веб-службу, не вызывая исключения безопасности.

## <a name="configuring-visual-studio"></a>Настройка Visual Studio
 Чтобы настроить Visual Studio 2005 для отладки [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , вызывает веб-службы:

1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.

2.  В **конструктор проектов**, нажмите кнопку **Отладка** вкладки.

3.  В **действие при запуске** выберите **запуск внешней программы** и введите следующее:

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  В **параметры запуска** введите следующий текст в **аргументы командной строки** текстового поля:

     `-debug`  *Имя файла*

     *Filename* значение **-Отладка** параметр является XBAP-файла, например:

     `-debug c:\example.xbap`

> [!NOTE]
>  Это конфигурация по умолчанию для решений, созданных с помощью Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] шаблона проекта.

1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.

2.  В **конструктор проектов**, нажмите кнопку **Отладка** вкладки.

3.  В **параметры запуска** разделе, добавьте следующий параметр командной строки для **аргументы командной строки** текстового поля:

     `-debugSecurityZoneURL`  *URL*

     *URL-адрес* значение **- debugSecurityZoneURL** параметр [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] расположения, которое требуется имитировать как узлу вашего приложения.

 Например, рассмотрим [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , использует веб-службы со следующими [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Исходный узел [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для этого веб-служба является:

 `http://services.msdn.microsoft.com`

 Следовательно, полный **- debugSecurityZoneURL** параметра командной строки и значением является:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>См. также
 [Основное приложение WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
