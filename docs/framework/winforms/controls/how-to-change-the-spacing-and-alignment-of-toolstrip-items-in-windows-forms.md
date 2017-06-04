---
title: "Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms | Microsoft Docs"
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
  - "панели инструментов [Windows Forms], выравнивание элементов"
  - "ToolStrip - элемент управления [Windows Forms], выравнивание элементов"
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms
Элемент управления <xref:System.Windows.Forms.ToolStrip> обеспечивает полную поддержку возможностей структуры, таких как изменение размеров, создание интервалов между элементами <xref:System.Windows.Forms.ToolStripItem>, размещение элементов управления на <xref:System.Windows.Forms.ToolStrip>, и создание интервалов между элементами управления и <xref:System.Windows.Forms.ToolStrip>.  
  
 Так как свойство <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> имеет значение по умолчанию `true`, размеры элементов управления изменяются автоматически до тех пор, пока свойству <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> не будет присвоено значение `false`.  
  
### Изменение размеров элемента управления ToolStripItem вручную  
  
1.  Свойству <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> связанного элемента управления присвойте значение `false`.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
  
    ```  
  
2.  Свойству <xref:System.Windows.Forms.ToolStripItem.Size%2A> связанного элемента управления <xref:System.Windows.Forms.ToolStripItem> присвойте любое значение.  
  
### Установка интервалов элемента управления ToolStripItem  
  
1.  Укажите необходимые значения \(в пикселях\) для свойства <xref:System.Windows.Forms.ToolStripItem.Margin%2A> связанного элемента управления.  
  
     Значения свойства <xref:System.Windows.Forms.ToolStripItem.Margin%2A> определяют интервал между элементом и соседствующими с ним элементами в следующем порядке: слева, сверху, справа и снизу.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
  
    ```  
  
### Выравнивание элемента ToolStripItem по правому краю полосы ToolStrip  
  
1.  Свойству <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> связанного элемента управления присвойте значение <xref:System.Windows.Forms.ToolStripItemAlignment>.  По умолчанию свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> имеет значение <xref:System.Windows.Forms.ToolStripItemAlignment>, и элементы управления выравниваются по левому краю полосы <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
  
    ```  
  
### Размещение элементов ToolStrip на полосе ToolStrip  
  
-   Присвойте свойству <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> любое значение <xref:System.Windows.Forms.ToolStripLayoutStyle>.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.Control.Layout>   
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>   
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>   
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)