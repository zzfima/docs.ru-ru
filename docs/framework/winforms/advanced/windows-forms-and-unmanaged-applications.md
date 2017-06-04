---
title: "Windows Forms and Unmanaged Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ActiveX controls [Windows Forms]"
  - "COM interop, Windows Forms"
  - "COM [Windows Forms]"
  - "Windows Forms, unmanaged"
  - "Windows Forms, interop"
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms and Unmanaged Applications
Приложения и элементы управления Windows Forms могут взаимодействовать с неуправляемыми приложениями, но с некоторыми оговорками.  В следующих разделах описываются сценарии и конфигурации, которые поддерживаются и не поддерживаются элементами управления и приложениями Windows Forms.  
  
## В этом подразделе  
 [Общие сведения о Windows Forms и неуправляемых приложениях](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Общие сведения о том, как использовать и реализовывать элементы управления Windows Forms, которые работают с неуправляемыми приложениями.  
  
 [Практическое руководство. Поддержка COM\-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Пример кода, который демонстрирует использование метода <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName> для запуска формы Windows Forms в неуправляемом приложении.  
  
 [Практическое руководство. Поддержка COM\-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Пример кода, демонстрирующий выполнение формы Windows Forms в отдельном потоке.  
  
 См. также [Пошаговое руководство. Поддержка COM\-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## Ссылка  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>  
 Используется для создания отдельного потока для формы Windows Forms.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>  
 Запускает цикл сообщений для потока.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Выполняет маршалинг вызовов из неуправляемого приложения в форму.  
  
## Связанные подразделы  
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Общие сведения об использовании типов .NET Framework в неуправляемых приложениях.