---
title: "Практическое руководство. Проверка наличия установленной платформы .NET Framework 3.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WinFX Runtime user-agent string
- presence of WPT [WPF], detecting
- detecting WPF presence [WPF]
ms.assetid: 7f71d652-1749-4379-945a-aa2e3994cb43
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6990ca4bff7c8756f8d7f25ff0153b3a5d41a4f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-whether-the-net-framework-30-is-installed"></a><span data-ttu-id="4ce47-102">Практическое руководство. Проверка наличия установленной платформы .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="4ce47-102">How to: Detect Whether the .NET Framework 3.0 Is Installed</span></span>
<span data-ttu-id="4ce47-103">Прежде чем развертывать [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] приложений в системе, их необходимо сначала убедиться, что [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] наличии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4ce47-103">Before administrators can deploy [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] applications on a system, they must first confirm that the [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] runtime is present.</span></span> <span data-ttu-id="4ce47-104">В этом разделе содержится скрипт, написанный на языке HTML/JavaScript, администраторы могут использовать для определения ли [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] присутствует в системе.</span><span class="sxs-lookup"><span data-stu-id="4ce47-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ce47-105">Более подробные сведения об установке, развертывании и обнаружении [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], см. обсуждение в [развертывания Microsoft .NET Framework версии 3.0](http://go.microsoft.com/fwlink/?LinkId=96739).</span><span class="sxs-lookup"><span data-stu-id="4ce47-105">For more detailed information on installing, deploying, and detecting the [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], see the discussion in [Deploying Microsoft .NET Framework Version 3.0](http://go.microsoft.com/fwlink/?LinkId=96739).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="detect-the-net-clr-user-agent-string"></a><span data-ttu-id="4ce47-106">Определить строку агента пользователя «.NET CLR»</span><span class="sxs-lookup"><span data-stu-id="4ce47-106">Detect the ".NET CLR" User-Agent String</span></span>  
 <span data-ttu-id="4ce47-107">Если [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] является установки MSI-ФАЙЛ добавляет «CLR.NET» и номер версии строки UserAgent.</span><span class="sxs-lookup"><span data-stu-id="4ce47-107">When [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="4ce47-108">В следующем примере показано в скрипте, внедренном в простой HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="4ce47-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="4ce47-109">В скрипте выполняется поиск строки UserAgent, чтобы определить, является ли [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] устанавливается и отображается сообщение о состоянии по результатам поиска.</span><span class="sxs-lookup"><span data-stu-id="4ce47-109">The script searches the UserAgent string to determine whether [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] is installed, and displays a status message on the results of the search.</span></span>  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.0</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.0.04425.00";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.0: "   
          + dotNETRuntimeVersion  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.0."  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="4ce47-110">При успешном выполнении поиска для версии «.NET CLR» появится сообщение о состоянии следующего типа:</span><span class="sxs-lookup"><span data-stu-id="4ce47-110">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.0: 3.0.04425.00`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727; .NET CLR 3.0.04425.00).`  
  
 <span data-ttu-id="4ce47-111">В противном случае появится сообщение о состоянии следующего типа:</span><span class="sxs-lookup"><span data-stu-id="4ce47-111">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have correct version of the .NET Framework 3.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; .NET CLR 1.1.4322; InfoPath.1; .NET CLR 2.0.50727).`
