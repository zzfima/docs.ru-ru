---
title: Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: ba411d662a8e5b0c4727e23c8d507e8924b6e9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="154d4-102">Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox</span><span class="sxs-lookup"><span data-stu-id="154d4-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="154d4-103">Windows Presentation Foundation (WPF) для Firefox подключаемый модуль включает [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] , отменив XAML-файлы для выполнения в браузере Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="154d4-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="154d4-104">В этом разделе содержится скрипт, написанный на языках HTML и JavaScript, который администраторы могут использовать для определения наличия подключаемого модуля WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="154d4-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="154d4-105">Дополнительные сведения об установке, развертывании и обнаружении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], в разделе [установить платформу .NET Framework для разработчиков](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="154d4-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="154d4-106">Пример</span><span class="sxs-lookup"><span data-stu-id="154d4-106">Example</span></span>  
 <span data-ttu-id="154d4-107">Когда [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] будет установлен, клиентский компьютер настроен подключаемый модуль WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="154d4-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="154d4-108">Следующий пример скрипта проверяет наличие подключаемого модуля WPF для Firefox и затем отображает соответствующее сообщение о состоянии.</span><span class="sxs-lookup"><span data-stu-id="154d4-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
```  
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
  
 <span data-ttu-id="154d4-109">При успешном выполнении проверки подключаемого модуля WPF для Firefox отображается следующее сообщение о состоянии:</span><span class="sxs-lookup"><span data-stu-id="154d4-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="154d4-110">В противном случае отображается следующее сообщение о состоянии:</span><span class="sxs-lookup"><span data-stu-id="154d4-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="154d4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="154d4-111">See Also</span></span>  
 [<span data-ttu-id="154d4-112">Проверка наличия установленной платформы .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="154d4-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="154d4-113">Проверка наличия установленной платформы .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="154d4-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [<span data-ttu-id="154d4-114">Общие сведения о приложениях браузера WPF XAML</span><span class="sxs-lookup"><span data-stu-id="154d4-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
