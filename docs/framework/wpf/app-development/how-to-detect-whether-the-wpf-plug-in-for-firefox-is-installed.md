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
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="9e0e1-102">Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox</span><span class="sxs-lookup"><span data-stu-id="9e0e1-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="9e0e1-103">Подключаемый модуль Windows Presentation Foundation (WPF) для Firefox позволяет запускать приложения браузера XAML (XBAP) и свободные XAML-файлы в браузере Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="9e0e1-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables XAML browser applications (XBAPs) and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="9e0e1-104">В этом разделе содержится сценарий, написанный на языке HTML и JavaScript, с помощью которого администраторы могут определить, установлен ли подключаемый модуль WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="9e0e1-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="9e0e1-105">Дополнительные сведения об установке, развертывании и обнаружении .NET Framework см. в [статье установка .NET Framework для разработчиков](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="9e0e1-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="9e0e1-106">Пример</span><span class="sxs-lookup"><span data-stu-id="9e0e1-106">Example</span></span>

<span data-ttu-id="9e0e1-107">При установке .NET Framework 3,5 клиентский компьютер настраивается с помощью подключаемого модуля WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="9e0e1-107">When the .NET Framework 3.5 is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="9e0e1-108">В следующем примере скрипт проверяет наличие подключаемого модуля WPF для Firefox и отображает соответствующее сообщение о состоянии.</span><span class="sxs-lookup"><span data-stu-id="9e0e1-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

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

<span data-ttu-id="9e0e1-109">Если проверка подключаемого модуля WPF для Firefox прошла успешно, отображается следующее сообщение о состоянии:</span><span class="sxs-lookup"><span data-stu-id="9e0e1-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="9e0e1-110">В противном случае отображается следующее сообщение о состоянии:</span><span class="sxs-lookup"><span data-stu-id="9e0e1-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="9e0e1-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e0e1-111">See also</span></span>

- [<span data-ttu-id="9e0e1-112">Проверка наличия установленной платформы .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="9e0e1-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="9e0e1-113">Проверка наличия установленной платформы .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="9e0e1-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="9e0e1-114">Общие сведения о приложениях браузера WPF XAML</span><span class="sxs-lookup"><span data-stu-id="9e0e1-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
