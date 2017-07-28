---
title: "Надстройки Firefox для поддержки развертывания приложений .NET | Microsoft Docs"
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
  - "развертывание приложений .NET, развертывание с надстройками Firefox"
  - ".NET Framework Assistant для Firefox"
  - "Надстройки Firefox для развертывания приложений .NET"
  - "подключаемый модуль WPF для Firefox"
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Надстройки Firefox для поддержки развертывания приложений .NET
Подключаемый модуль [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] для Firefox и расширение .NET Framework Assistant для Firefox позволяют приложениям [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], свободному [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и приложениям ClickOnce работать с браузером Mozilla Firefox.  
  
## Подключаемый модуль WPF для Firefox  
 Подключаемый модуль WPF для Firefox обеспечивает возможность перехода к приложениям [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] и файлам свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а также их запуска в окне верхнего уровня или в кадре IFRAME HTML браузера Mozilla Firefox.  [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] — это приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], которое можно опубликовать на веб\-сервере и запустить в поддерживаемых браузерах.  Свободный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] — это файл, содержащий только разметку XAML, к которому можно переходить в поддерживаемых браузерах и отображать в этих браузерах, точно так же как XML\-файл.  
  
 Подключаемый модуль [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для Firefox устанавливается вместе с платформой [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)].  Windows 7 включает платформу [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], но не содержит подключаемый модуль [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для Firefox. Подключаемый модуль [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для Firefox нельзя установить в Windows 7.  
  
 Платформа [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] не содержит подключаемый модуль [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для Firefox. Однако при одновременной установке платформ [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] подключаемый модуль WPF для Firefox устанавливается вместе с платформой [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)].  Поэтому приложения [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] будут по\-прежнему работать, поскольку ведущее приложение WPF загрузит правильную версию платформы.  Дополнительные сведения см. в разделе [Ведущее приложение WPF \(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## .NET Framework Assistant для Firefox  
 Расширение .NET Framework Assistant для Firefox обеспечивает работу автономных приложений ClickOnce в браузере Firefox.  Функционирование .NET Framework Assistant для Firefox не зависит от того, когда было установлено это расширение — до или после установки браузера Firefox.  Если браузер Firefox запускается на компьютере с установленной платформой [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], Firefox находит и устанавливает расширение .NET Framework Assistant для Firefox.  .NET Framework Assistant для Firefox можно настроить для выполнения следующих задач.  
  
-   Вывод запрос перед запуском приложения ClickOnce.  
  
-   Вывод сообщения о всех установленных версиях .NET Framework или только о последней версии.  
  
 .NET Framework Assistant для Firefox входит в состав платформы [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)].  Сведения об удалении .NET Framework Assistant для Firefox см. в статье [Удаление .NET Framework Assistant для Firefox](http://go.microsoft.com/fwlink/?LinkId=177944).  
  
## См. также  
 [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)   
 [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)   
 [Обнаружение установленного подключаемого модуля WPF для Firefox](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)