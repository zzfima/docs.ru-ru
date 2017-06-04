---
title: "Drag-and-Drop Operations and Clipboard Support | Microsoft Docs"
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
  - "drag and drop"
  - "drag and drop, Windows Forms"
  - "Clipboard, Windows Forms"
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Drag-and-Drop Operations and Clipboard Support
Пользовательские операции перетаскивания в приложении Windows можно включить путем обработки последовательности событий, в частности событий <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> и <xref:System.Windows.Forms.Control.DragDrop>.  
  
 Реализовать поддержку пользовательских операций вырезания, копирования, вставки и передачу данных пользователя в буфер обмена в приложении Windows также можно с помощью обычных вызовов методов.  
  
## В этом подразделе  
 [Walkthrough: Performing a Drag\-and\-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 Описание запуска операции перетаскивания.  
  
 [How to: Perform Drag\-and\-Drop Operations Between Applications](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 Демонстрация выполнения операций перетаскивания в разных приложениях.  
  
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 Описание программного способа вставки данных в буфер обмена.  
  
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 Описание способов получения доступа к данным, хранимым в буфере обмена.  
  
## Связанные подразделы  
 [Drag\-and\-Drop Functionality in Windows Forms](../../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 Описание методов, событий и классов, используемых для реализации поведения перетаскивания.  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 Описание особенностей события, которое запрашивает разрешение на продолжение операции перетаскивания.  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 Описание особенностей метода, который является основным для запуска операции перетаскивания.  
  
 <xref:System.Windows.Forms.Clipboard>  
 См. также [Практическое руководство. Отправка данных в активную дочернюю форму MDI](http://msdn.microsoft.com/library/y0hkh2c8%20\(v=vs.110\)).