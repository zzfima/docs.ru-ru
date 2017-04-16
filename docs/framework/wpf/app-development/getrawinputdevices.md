---
title: "Получение необработанных устройств ввода | Microsoft Docs"
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
  - "GetRawInputDevices - метод"
  - "необработанный ввод [WPF]"
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Получение необработанных устройств ввода
Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода \(устройства HID\), которые интересуют ведущее приложение.  
  
## Синтаксис  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### Параметры  
 `ppEnum`  
  
 \[out\] Указатель на [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) для перечисления устройств необработанного ввода.  
  
## Значение свойства, возвращаемое значение  
 HRESULT:  
  
 S\_OK — [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) будет использоваться только в PresentationHost.exe, если возвращается значение S\_OK.  
  
 E\_NOTIMPL  
  
## Заметки  
 Устройства необработанного ввода — это ряд устройств, включающий клавиатуры, мышь и менее распространенные устройства, такие как устройства удаленного управления.  
  
 После получения списка устройств необработанного ввода программа PresentationHost.exe регистрируется в устройствах для получения уведомлений WM\_INPUT.  
  
## См. также  
 [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/winui\/winui\/windowsuserinterface\/userinput\/rawinput\/rawinputreference\/rawinputfunctions\/getrawinputdevicelist.asp](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)   
 [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)