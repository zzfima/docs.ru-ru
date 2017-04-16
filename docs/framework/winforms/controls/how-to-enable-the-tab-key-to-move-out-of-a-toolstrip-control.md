---
title: "Практическое руководство. Выход из элемента управления ToolStrip с помощью клавиши TAB | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], перемещение между"
  - "TAB - клавиша, включение"
  - "ToolStrip - элемент управления [Windows Forms], перемещение от"
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Выход из элемента управления ToolStrip с помощью клавиши TAB
Следующая процедура позволяет пользователю переходить от <xref:System.Windows.Forms.ToolStrip> к следующему элементу управления в порядке перехода с помощью клавиши TAB.  
  
 Элемент управления <xref:System.Windows.Forms.ToolStrip> принимает первое нажатие клавиши TAB, а клавиши со стрелками используются для выбора элементов, включенных в <xref:System.Windows.Forms.ToolStrip>.  При повторном нажатии клавиши TAB фокус перемещается к следующему элементу управления в порядке перехода.  
  
### Переход от элемента управления ToolStrip к следующему элементу управления путем нажатия пользователем клавиши TAB  
  
-   Присвойте свойству <xref:System.Windows.Forms.ToolStrip.TabStop%2A> элемента <xref:System.Windows.Forms.ToolStrip> значение `true`.  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)