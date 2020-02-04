---
title: Определить, установлен ли подключаемый модуль WPF для Firefox
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 91680859c1742e5d5443d626c81273a80504f4a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740396"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox

Подключаемый модуль Windows Presentation Foundation (WPF) для Firefox позволяет запускать приложения браузера XAML (XBAP) и свободные XAML-файлы в браузере Mozilla Firefox. В этом разделе содержится сценарий, написанный на языке HTML и JavaScript, с помощью которого администраторы могут определить, установлен ли подключаемый модуль WPF для Firefox.

> [!NOTE]
> Дополнительные сведения об установке, развертывании и обнаружении .NET Framework см. в [статье установка .NET Framework для разработчиков](../../install/guide-for-developers.md).

## <a name="example"></a>Пример

При установке .NET Framework 3,5 клиентский компьютер настраивается с помощью подключаемого модуля WPF для Firefox. В следующем примере скрипт проверяет наличие подключаемого модуля WPF для Firefox и отображает соответствующее сообщение о состоянии.

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

Если проверка подключаемого модуля WPF для Firefox прошла успешно, отображается следующее сообщение о состоянии:

`The WPF plug-in for Firefox is installed.`

В противном случае отображается следующее сообщение о состоянии:

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>См. также раздел

- [Проверка наличия установленной платформы .NET Framework 3.0](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Проверка наличия установленной платформы .NET Framework 3.5](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md)
