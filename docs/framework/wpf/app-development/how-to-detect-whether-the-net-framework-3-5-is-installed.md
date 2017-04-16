---
title: "Практическое руководство. Проверка наличия установленной платформы .NET Framework 3.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "обнаружение установки платформы .NET Framework 3.5 [WPF]"
  - "обнаружение установленной платформы .NET Framework [WPF]"
  - "определение, установлена ли платформа .NET Framework [WPF]"
  - "проверка, установлена ли платформа .NET Framework [WPF]"
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Проверка наличия установленной платформы .NET Framework 3.5
Прежде чем развертывать приложения [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] в системе, ориентированной на [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], необходимо сначала убедиться в наличии среды выполнения [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)].  В этом разделе предоставлен скрипт, написанный на языке HTML\/JavaScript, с помощью которого администраторы могут определить наличие [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] в системе.  
  
> [!NOTE]
>  Дополнительные сведения об установке, развертывании и обнаружении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] см. в разделе [Установка .NET Framework](../../../../docs/framework/install/guide-for-developers.md).  
  
## Пример  
 После установки [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] MSI добавляет ".NET CLR" и номер версии в строку UserAgent.  В следующем примере показан скрипт, встроенный в простую страницу HTML.  В скрипте выполняется поиск строки UserAgent, чтобы определить, установлена ли платформа [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], и отображается сообщение о состоянии по результатам поиска.  
  
> [!NOTE]
>  Данный скрипт предназначен для Internet Explorer.  Другие браузеры не могут включать информацию среды CLR .NET CLR в строку UserAgent.  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
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
  
 Если поиск версии ".NET CLR" завершился успешно, появляется сообщение о состоянии следующего типа:  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 В противном случае появляется сообщение о состоянии следующего типа:  
  
 `This machine does not have the correct version of the .NET Framework 3.5.  The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## См. также  
 [Проверка наличия установленной платформы .NET Framework 3.0](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)