---
title: "Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip | Microsoft Docs"
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
  - "контекстные меню, добавление пунктов меню"
  - "ContextMenuStrips, добавление пунктов меню"
  - "контекстные меню, добавление элементов"
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip
В <xref:System.Windows.Forms.ContextMenuStrip> можно добавить один или несколько пунктов меню одновременно  
  
### Добавление отдельного пункта меню в ContextMenuStrip  
  
-   Используйте метод <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> для добавления одного пункта меню в <xref:System.Windows.Forms.ContextMenuStrip>.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### Добавление нескольких пунктов меню в ContextMenuStrip  
  
-   Используйте метод <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> для добавления нескольких пунктов меню в <xref:System.Windows.Forms.ContextMenuStrip>.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## См. также  
 [Элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)