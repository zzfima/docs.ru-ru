---
title: Практическое руководство. Проверка наличия установленного подключаемого модуля WPF для Firefox
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: f84a0a2af43931b3ada1f674390ec5d841b79a1c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690429"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Практическое руководство. Проверка наличия установленного подключаемого модуля WPF для Firefox

Позволяет Windows Presentation Foundation (WPF) подключаемого модуля для Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободных файлов XAML для выполнения в браузере Mozilla Firefox. В этом разделе содержится скрипт, написанный на языках HTML и JavaScript, который администраторы могут использовать, чтобы определить, установлен ли подключаемый модуль WPF для Firefox.

> [!NOTE]
> Дополнительные сведения об установке, развертывании и обнаружении .NET Framework, см. в разделе [установка .NET Framework для разработчиков](../../install/guide-for-developers.md).

## <a name="example"></a>Пример

При установке .NET Framework 3.5, клиентский компьютер настроен с помощью подключаемого модуля WPF для Firefox. В нижеприведенном примере сценария проверяет для подключаемого модуля WPF для Firefox, а затем отображает соответствующее сообщение о состоянии.

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

При успешном выполнении проверки подключаемого модуля WPF для Firefox отображается следующее сообщение:

`The WPF plug-in for Firefox is installed.`

В противном случае отображается следующее сообщение:

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>См. также

- [Проверка наличия установленной платформы .NET Framework 3.0](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [Проверка наличия установленной платформы .NET Framework 3.5](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md)
