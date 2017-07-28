---
title: "Практическое руководство. Изменение внешнего вида текста и изображений элемента управления ToolStrip в Windows Forms | Microsoft Docs"
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
  - "примеры [Windows Forms], панели инструментов"
  - "панели инструментов [Windows Forms], внешний вид"
  - "панели инструментов [Windows Forms], изображения"
  - "панели инструментов [Windows Forms], текст"
  - "ToolStrip - элемент управления [Windows Forms], внешний вид"
  - "ToolStrip - элемент управления [Windows Forms], изображения"
  - "ToolStrip - элемент управления [Windows Forms], текст"
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Изменение внешнего вида текста и изображений элемента управления ToolStrip в Windows Forms
Можно управлять отображением текста и рисунков в <xref:System.Windows.Forms.ToolStripItem> и их выравниванием относительно друг друга в <xref:System.Windows.Forms.ToolStrip>.  
  
### Чтобы определить, что отображается в элементе управления ToolStripItem  
  
-   Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> нужное значение.  Возможные значения — `Image`, `ImageAndText`, `None` и `Text`.  Значение по умолчанию — `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
  
    ```  
  
### Чтобы выровнять текст в элементе управления ToolStripItem  
  
-   Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> нужное значение.  Возможные значения — любые сочетания значений top \(сверху\), middle \(в середине по вертикали\) и bottom \(снизу\) с left \(слева\), center \(в середине по горизонтали\) и right \(справа\).  Значение по умолчанию — `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### Чтобы выровнять рисунок в элементе управления ToolStripItem  
  
-   Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> нужное значение.  Возможные значения — любые сочетания значений top \(сверху\), middle \(в середине по вертикали\) и bottom \(снизу\) с left \(слева\), center \(в середине по горизонтали\) и right \(справа\).  Значение по умолчанию — `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### Чтобы управлять выравниванием текста и рисунков относительно друг друга  
  
-   Установите свойству <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> нужное значение.  Возможные значения — `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage` и `TextBeforeImage`.  По умолчанию используется значение `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)