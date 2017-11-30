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
ms.openlocfilehash: 3012afc118420a83c869785d26c28f1eee969cb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Практическое руководство. Обнаружение установленного подключаемого модуля WPF для Firefox
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Подключаемого модуля для Firefox позволяет [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] , отменив XAML-файлы для выполнения в браузере Mozilla Firefox. В этом разделе содержится скрипт, написанный на языках HTML и JavaScript, который администраторы могут использовать для определения наличия подключаемого модуля WPF для Firefox.  
  
> [!NOTE]
>  Дополнительные сведения об установке, развертывании и обнаружении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], в разделе [установить платформу .NET Framework для разработчиков](../../../../docs/framework/install/guide-for-developers.md).  
  
## <a name="example"></a>Пример  
 Когда [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] будет установлен, клиентский компьютер настроен подключаемый модуль WPF для Firefox. Следующий пример скрипта проверяет наличие подключаемого модуля WPF для Firefox и затем отображает соответствующее сообщение о состоянии.  
  
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
  
 При успешном выполнении проверки подключаемого модуля WPF для Firefox отображается следующее сообщение о состоянии:  
  
 `The WPF plug-in for Firefox is installed.`  
  
 В противном случае отображается следующее сообщение о состоянии:  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a>См. также  
 [Проверка наличия установленной платформы .NET Framework 3.0](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [Проверка наличия установленной платформы .NET Framework 3.5](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
