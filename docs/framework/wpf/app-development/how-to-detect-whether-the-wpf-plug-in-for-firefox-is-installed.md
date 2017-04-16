---
title: "Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox | Microsoft Docs"
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
  - "проверка подключаемого модуля для Firefox [WPF]"
  - "обнаружение установки Firefox [WPF]"
  - "обнаружение установленного подключаемого модуля WPF для Firefox [WPF]"
  - "Firefox [WPF], обнаружение установки"
  - "модуль для Firefox [WPF]"
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox
Подключаемый модуль [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] для Firefox позволяет открывать файлы [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободные файлы XAML в браузере Mozilla Firefox.  В этом разделе содержится скрипт, написанный на языках HTML и JavaScript, который администраторы могут использовать для определения наличия в системе подключаемого модуля WPF для Firefox.  
  
> [!NOTE]
>  Дополнительные сведения об установке, развертывании и обнаружении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] см. в разделе [Установка .NET Framework](../../../../docs/framework/install/guide-for-developers.md).  
  
## Пример  
 При установке [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] на клиентском компьютере устанавливается и настраивается подключаемый модуль WPF для Firefox.  Следующий пример скрипта проверяет наличие подключаемого модуля WPF для Firefox и выводит соответствующее сообщение о состоянии.  
  
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
  
 Если проверка наличия подключаемого модуля WPF для Firefox пройдена успешно, отображается следующее сообщение о состоянии:  
  
 `The WPF plug-in for Firefox is installed.`  
  
 В противном случае отображается следующее сообщение о состоянии:  
  
 `The WPF plug-in for Firefox is not installed.  Please install or reinstall the .NET Framework 3.5.`  
  
## См. также  
 [Проверка наличия установленной платформы .NET Framework 3.0](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)   
 [Проверка наличия установленной платформы .NET Framework 3.5](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)   
 [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)