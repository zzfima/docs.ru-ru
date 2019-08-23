---
title: Практическое руководство. Настройка Visual Studio для отладки приложений браузера XAML для вызова веб-службы
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: e41dd46e4ddbdcde6448c68b4f9fb2e073baca43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958690"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Практическое руководство. Настройка Visual Studio для отладки приложений браузера XAML для вызова веб-службы
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]выполнение в песочнице безопасности с частичным доверием, ограниченным набором разрешений зоны Интернета. Этот набор разрешений разрешает вызовы веб-службы только для веб-служб, расположенных на [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] исходном узле приложения. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Однако при отладке из Visual Studio 2005 не считается, что исходный сайт совпадает с веб-службой, на которую он ссылается. Это приводит к возникновению исключений безопасности при [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] попытке вызова веб-службы. Однако проект Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] можно настроить для имитации того же узла происхождения, что и веб-служба, которую он вызывает во время отладки. Это позволяет безопасно [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] вызывать веб-службу, не вызывая исключений безопасности.

## <a name="configuring-visual-studio"></a>Настройка Visual Studio
 Чтобы настроить Visual Studio 2005 для отладки [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , который вызывает веб-службу, сделайте следующее:

1. Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.

2. В **конструкторе проектов**перейдите на вкладку **Отладка** .

3. В разделе **действие при запуске** выберите **Запуск внешней программы** и введите следующее:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. В разделе **Параметры запуска** введите следующий текст в текстовое поле **аргументы командной строки** :

     `-debug`  *файлов*

     Значение *filename* для параметра **-Debug** — имя файла XBAP; Например:

     `-debug c:\example.xbap`

> [!NOTE]
> Это конфигурация по умолчанию для решений, созданных с помощью шаблона проекта Visual Studio [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 2005.

1. Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.

2. В **конструкторе проектов**перейдите на вкладку **Отладка** .

3. В разделе **Параметры запуска** добавьте следующий параметр командной строки в текстовое поле **аргументы командной строки** :

     `-debugSecurityZoneURL`  *URL*

     *URL-адрес* для [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] параметра **-дебугсекуритизонеурл** — это расположение, которое вы хотите имитировать как исходный сайт приложения.

 Например, рассмотрим [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] , что использует веб-службу со следующим [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 Исходный [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] сайт для этой веб-службы:

 `http://services.msdn.microsoft.com`

 Следовательно, параметр и значение командной строки Complete **-дебугсекуритизонеурл** :

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>См. также

- [Основное приложение WPF (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
