---
title: "Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87e821bd95679372fd169b7880e969fd10b5d03c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="bd337-102">Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox</span><span class="sxs-lookup"><span data-stu-id="bd337-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="bd337-103">[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Подключаемого модуля для Firefox позволяет [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] , отменив XAML-файлы для выполнения в браузере Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="bd337-103">The [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="bd337-104">В этом разделе содержится скрипт, написанный на языках HTML и JavaScript, который администраторы могут использовать для определения наличия подключаемого модуля WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="bd337-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd337-105">Дополнительные сведения об установке, развертывании и обнаружении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], в разделе [установить платформу .NET Framework для разработчиков](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="bd337-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd337-106">Пример</span><span class="sxs-lookup"><span data-stu-id="bd337-106">Example</span></span>  
 <span data-ttu-id="bd337-107">Когда [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] будет установлен, клиентский компьютер настроен подключаемый модуль WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="bd337-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="bd337-108">Следующий пример скрипта проверяет наличие подключаемого модуля WPF для Firefox и затем отображает соответствующее сообщение о состоянии.</span><span class="sxs-lookup"><span data-stu-id="bd337-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
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
  
 <span data-ttu-id="bd337-109">При успешном выполнении проверки подключаемого модуля WPF для Firefox отображается следующее сообщение о состоянии:</span><span class="sxs-lookup"><span data-stu-id="bd337-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="bd337-110">В противном случае отображается следующее сообщение о состоянии:</span><span class="sxs-lookup"><span data-stu-id="bd337-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="bd337-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bd337-111">See Also</span></span>  
 [<span data-ttu-id="bd337-112">Проверка наличия установленной платформы .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="bd337-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="bd337-113">Проверка наличия установленной платформы .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="bd337-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [<span data-ttu-id="bd337-114">Общие сведения о приложениях браузера WPF XAML</span><span class="sxs-lookup"><span data-stu-id="bd337-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
