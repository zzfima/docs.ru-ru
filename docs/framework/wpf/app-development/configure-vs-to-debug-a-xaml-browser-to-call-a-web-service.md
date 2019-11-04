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
ms.openlocfilehash: d8cfae2fb47876d578c51e5f4acdfe0c31e752fe
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460904"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Настройка Visual Studio для отладки приложения браузера XAML для вызова веб-службы
Приложения браузера XAML (XBAP) выполняются в изолированной среде безопасности с частичным доверием, которая ограничена набором разрешений зоны Интернета. Этот набор разрешений разрешает вызовы веб-службы только для веб-служб, расположенных на исходном узле приложения XBAP. Однако при отладке XBAP из Visual Studio 2005 не считается, что исходный сайт совпадает с веб-службой, на которую он ссылается. Это приводит к возникновению исключений безопасности, когда XBAP пытается вызвать веб-службу. Однако проект приложения браузера XAML Visual Studio 2005 можно настроить для имитации того же узла происхождения, что и веб-служба, которую он вызывает во время отладки. Это позволяет XBAP безопасно вызывать веб-службу, не вызывая исключений безопасности.

## <a name="configuring-visual-studio"></a>Настройка Visual Studio
 Чтобы настроить Visual Studio 2005 для отладки XBAP, вызывающего веб-службу, сделайте следующее:

1. Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.

2. В **конструкторе проектов**перейдите на вкладку **Отладка** .

3. В разделе **действие при запуске** выберите **Запуск внешней программы** и введите следующее:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. В разделе **Параметры запуска** введите следующий текст в текстовое поле **аргументы командной строки** :

     `-debug`  *имя_файла*

     Значение *filename* для параметра **-Debug** — имя файла XBAP; Например:

     `-debug c:\example.xbap`

> [!NOTE]
> Это конфигурация по умолчанию для решений, созданных с помощью шаблона проекта приложения браузера XAML Visual Studio 2005 (WPF).

1. Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.

2. В **конструкторе проектов**перейдите на вкладку **Отладка** .

3. В разделе **Параметры запуска** добавьте следующий параметр командной строки в текстовое поле **аргументы командной строки** :

     `-debugSecurityZoneURL`  *URL*

     *URL-адрес* параметра **-дебугсекуритизонеурл** — это URL-адрес расположения, которое вы хотите имитировать как исходный сайт приложения.

 В качестве примера рассмотрим приложение браузера XAML (XBAP), использующее веб-службу со следующим URL-адресом:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 URL-адрес исходного узла для этой веб-службы:

 `http://services.msdn.microsoft.com`

 Следовательно, параметр и значение командной строки Complete **-дебугсекуритизонеурл** :

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>См. также

- [Основное приложение WPF (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
