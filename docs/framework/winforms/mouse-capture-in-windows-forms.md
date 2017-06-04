---
title: "Mouse Capture in Windows Forms | Microsoft Docs"
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
  - "mouse, capture"
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Mouse Capture in Windows Forms
*Захватом мыши* называется управление всем вводом мыши одним элементом управления.  Когда элемент управления захватил мышь, он получает входные данные мыши независимо от того, находится ли курсор в границах элемента или нет.  
  
## Установка захвата мыши  
 В формах Windows Forms мышь захватывается элементом управления, когда пользователь нажимает кнопку мыши, установив указатель на элементе управления, и освобождается элементом управления, когда пользователь отпускает кнопку мыши.  
  
 Свойство <xref:System.Windows.Forms.Control.Capture%2A> класса <xref:System.Windows.Forms.Control> указывает, захватил ли элемент управления мышь.  Чтобы определить, когда элемент управления теряет захват мыши, достаточно обрабатывать событие <xref:System.Windows.Forms.Control.MouseCaptureChanged>.  
  
 Захватить мышь может только окно переднего плана.  Если это попытается сделать окно заднего плана, то оно получит сообщения о событиях мыши, происходящих, когда указатель мыши находится над видимой частью окна.  Кроме того, даже если окно переднего плана захватило мышь, можно щелкнуть другое окно, чтобы сделать его окном переднего плана.  При захвате мыши сочетания клавиш не работают.  
  
## См. также  
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)