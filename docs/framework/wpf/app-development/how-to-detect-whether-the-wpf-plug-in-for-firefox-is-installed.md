---
title: Как выполнить Обнаружение установленного подключаемого модуля WPF для Firefox
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: f017aec8788d9ed38476262bba457f4621217519
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677983"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="f0056-102">Как выполнить Обнаружение установленного подключаемого модуля WPF для Firefox</span><span class="sxs-lookup"><span data-stu-id="f0056-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="f0056-103">Позволяет Windows Presentation Foundation (WPF) подключаемого модуля для Firefox [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободных файлов XAML для выполнения в браузере Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="f0056-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="f0056-104">В этом разделе содержится скрипт, написанный на языках HTML и JavaScript, который администраторы могут использовать, чтобы определить, установлен ли подключаемый модуль WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="f0056-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0056-105">Дополнительные сведения об установке, развертывании и обнаружении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], см. в разделе [установка .NET Framework для разработчиков](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="f0056-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0056-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f0056-106">Example</span></span>  
 <span data-ttu-id="f0056-107">Когда [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] — установлен, клиентский компьютер настроен с помощью подключаемого модуля WPF для Firefox.</span><span class="sxs-lookup"><span data-stu-id="f0056-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="f0056-108">В нижеприведенном примере сценария проверяет для подключаемого модуля WPF для Firefox, а затем отображает соответствующее сообщение о состоянии.</span><span class="sxs-lookup"><span data-stu-id="f0056-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
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
  
 <span data-ttu-id="f0056-109">При успешном выполнении проверки подключаемого модуля WPF для Firefox отображается следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="f0056-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="f0056-110">В противном случае отображается следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="f0056-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="f0056-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f0056-111">See also</span></span>
- [<span data-ttu-id="f0056-112">Проверка наличия установленной платформы .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="f0056-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="f0056-113">Проверка наличия установленной платформы .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="f0056-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="f0056-114">Общие сведения о приложениях браузера WPF XAML</span><span class="sxs-lookup"><span data-stu-id="f0056-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
