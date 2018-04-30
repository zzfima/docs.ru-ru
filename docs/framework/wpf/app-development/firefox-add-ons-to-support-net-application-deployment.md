---
title: Надстройки Firefox для поддержки развертывания приложений .NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1066332b8c5b98b5cca45e7ffbea83bd8cee8775
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Надстройки Firefox для поддержки развертывания приложений .NET
Включение Windows Presentation Foundation (WPF) подключаемого модуля для Firefox и .NET Framework помощник по для Firefox [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]и приложения ClickOnce для работы с браузера Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Подключаемый модуль WPF для Firefox  
 Подключаемый модуль WPF для Firefox позволяет [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] и свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлы переход и запускаемых на верхнем уровне или в IFRAME HTML браузера Mozilla Firefox. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] — [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Приложения, опубликованные на веб-сервере и запустить в поддерживаемых браузерах. Свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] является файлом только для XAML, который переходит и в поддерживаемых браузерах, как в XML-файл.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Подключаемый модуль для Firefox устанавливается вместе с [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Windows 7 включает [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], но не включает [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] подключаемого модуля для Firefox. Не удается установить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] подключаемый модуль для браузера Firefox на Windows 7.  
  
 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] Не включает [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] подключаемого модуля для Firefox. Тем не менее если оба [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] будут установлены, подключаемый модуль WPF для Firefox устанавливается вместе с [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Поэтому [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] приложений будет работать, поскольку ведущее приложение WPF загрузит правильную версию платформы. Дополнительные сведения см. в разделе [узла WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant для Firefox  
 .NET Framework помощник по для Firefox позволяет автономных приложений ClickOnce для запуска в обозревателе Firefox. .NET Framework помощник по для Firefox функций идентично при установке до и после браузер Firefox. При запуске браузер Firefox и [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] будет установлено, Firefox находит и устанавливает помощник по .NET Framework для Firefox. Пользователи могут настраивать .NET Framework помощник по для Firefox осуществлять следующее:  
  
-   Выдавать приглашение перед запуском приложения ClickOnce.  
  
-   О всех установленных версий .NET Framework или только о последней версии.  
  
 .NET Framework помощник по для Firefox входит в состав [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Сведения об удалении помощник по .NET Framework для Firefox см. в разделе [удаление помощника по .NET Framework для Firefox](http://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>См. также  
 [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)  
 [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)  
 [Проверка наличия установленного подключаемого модуля WPF для Firefox](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
