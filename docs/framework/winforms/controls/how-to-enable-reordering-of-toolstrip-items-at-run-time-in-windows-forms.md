---
title: "Практическое руководство. Разрешение переупорядочения элементов ToolStrip во время выполнения в Windows Forms | Microsoft Docs"
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
  - "AllowItemReorder - свойство"
  - "примеры [Windows Forms], панели инструментов"
  - "панели инструментов [Windows Forms], упорядочивание элементов управления"
  - "ToolStrip - элемент управления [Windows Forms], примеры"
  - "ToolStrip - элемент управления [Windows Forms], переупорядочение элементов"
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Разрешение переупорядочения элементов ToolStrip во время выполнения в Windows Forms
Пользователю можно предоставить возможность переупорядочивать элементы управления <xref:System.Windows.Forms.ToolStripItem>, расположенные на <xref:System.Windows.Forms.ToolStrip>.  
  
### Разрешение переупорядочения элементов ToolStripItem во время выполнения  
  
-   Установите для свойства <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> значение `true`.  По умолчанию параметр <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> имеет значение `false`.  
  
     Чтобы перетащить элемент <xref:System.Windows.Forms.ToolStripItem> в другое место на <xref:System.Windows.Forms.ToolStrip>, пользователь должен удерживать нажатыми клавишу ALT и левую кнопку мыши.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)