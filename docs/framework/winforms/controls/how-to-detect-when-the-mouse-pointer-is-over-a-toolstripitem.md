---
title: "Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem | Microsoft Docs"
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
  - "мышь, обнаружение движения на панелях инструментов"
  - "панели инструментов [Windows Forms], обнаружение движения мыши"
  - "ToolStrip - элемент управления [Windows Forms], обнаружение движения мыши"
  - "ToolStripItem - класс, обнаружение движения мыши"
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem
Отслеживание наведения указателя мыши на элемент <xref:System.Windows.Forms.ToolStripItem>.  
  
### Чтобы обнаружить наведение указателя мыши на элемент ToolStripItem  
  
-   Используйте свойство <xref:System.Windows.Forms.ToolStripItem.Selected%2A> для элементов, в которых параметр <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> имеет значение `true`.  
  
     Это избавит вас от необходимости синхронизации событий <xref:System.Windows.Forms.ToolStripItem.MouseEnter> и <xref:System.Windows.Forms.ToolStripItem.MouseLeave>.  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)