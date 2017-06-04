---
title: "Интерфейс IWpfHostSupport | Microsoft Docs"
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
  - "IWpfHostSupport - интерфейс"
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Интерфейс IWpfHostSupport
Приложения, в которых размещается содержимое [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] средствами PresentationHost.exe, реализуют этот интерфейс для предоставления точки интегрирования между ведущим приложением и PresentationHost.exe.  
  
## Заметки  
 Приложения [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], например, браузеры, могут размещать содержимое [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)], включая [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободные XAML.  Для размещения содержимого [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] приложения [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] создают экземпляр [элемента управления WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911).  Чтобы разместить объект, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] создает экземпляр PresentationHost.exe, который предоставляет размещаемое содержимое [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] ведущему приложению для отображения в [элементе управления WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911).  
  
 Интеграция, обеспечиваемая `IWpfHostSupport`, позволяет PresentationHost.exe выполнить следующие действия:  
  
-   определить и зарегистрировать устройства необработанного ввода \(HID\-устройства\), в которых заинтересовано ведущее приложение;  
  
-   получить сообщения с входными данными от зарегистрированного устройства необработанного ввода и переслать соответствующие сообщения в ведущее приложение;  
  
-   сделать запрос ведущему приложению для получения сведений о ходе выполнения и пользовательского интерфейса ошибок.  
  
> [!NOTE]
>  Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере  
  
## Члены  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Получение необработанных устройств ввода](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|Позволяют программе PresentationHost.exe обнаруживать необработанные устройства ввода \(устройства пользовательского интерфейса\), в которых заинтересовано главное приложение.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|Вызывается с помощью PresentationHost.exe всякий раз, когда получено сообщение и не возвращается E\_NOTIMPL.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|По умолчанию PresentationHost.exe предоставляет свой собственный ход развертывания и пользовательский интерфейс ошибок развертывания, которые отображаются при развертывании содержимого WPF.|