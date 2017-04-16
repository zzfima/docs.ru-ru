---
title: "FilterInputMessage | Microsoft Docs"
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
  - "FilterInputMessage - метод"
  - "необработанный ввод [WPF]"
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# FilterInputMessage
Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E\_NOTIMPL.  
  
## Синтаксис  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### Параметры  
 `pMsg`  
  
 \[in\] Сообщение WM\_INPUT отправлено в окно, которое получает необработанные входные данные.  
  
## Значение свойства, возвращаемое значение  
 HRESULT:  
  
 S\_OK — фильтр не обработал сообщение, и дальнейшая обработка разрешена.  
  
 S\_FALSE — фильтр обработал это сообщение, и дальнейшая обработка не выполняется.  
  
 E\_NOTIMPL — если возвращено это значение, то [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) повторно не вызывается.  Это значение может быть возвращено из ведущего приложения, которое заинтересовано только в предоставлении пользовательских интерфейсов хода выполнения и ошибок в PresentationHost.exe и не заинтересовано в перенаправлении необработанных входных сообщений из PresentationHost.exe.  
  
## Заметки  
 PresentationHost.exe является целевым объектом различных необработанных устройств ввода, включая клавиатуру, мышь и удаленное управление.  В некоторых случаях поведение в ведущем приложении зависит от входных данных, которые в противном случае будет использоваться PresentationHost.exe.  Например, ведущее приложение может зависеть от получения определенных входных сообщений, чтобы определить необходимость отображения конкретных элементов пользовательского интерфейса.  
  
 Чтобы разрешить ведущему приложению получать необходимые входные сообщения для предоставления этих расширений функциональности, PresentationHost.exe перенаправляет соответствующие необработанные входные сообщения в размещенное приложение путем вызова [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).  
  
 Размещенное приложение получает необработанные входные сообщения путем регистрации в наборе необработанных устройств ввода \(HID\-устройств\),  возвращаемых [Получение необработанных устройств ввода](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).  
  
## См. также  
 [Уведомление WM\_INPUT](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)