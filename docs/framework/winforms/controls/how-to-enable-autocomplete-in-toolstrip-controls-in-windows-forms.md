---
title: "Практическое руководство. Включение автозаполнения для элементов управления ToolStrip в Windows Forms | Microsoft Docs"
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
  - "AutoComplete, включение в панелях инструментов"
  - "AutoComplete, примеры"
  - "примеры [Windows Forms], панели инструментов"
  - "панели инструментов [Windows Forms], AutoComplete"
  - "ToolStrip - элемент управления [Windows Forms], AutoComplete"
  - "ToolStripComboBox - класс, примеры"
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Включение автозаполнения для элементов управления ToolStrip в Windows Forms
В следующей процедуре компонент <xref:System.Windows.Forms.ToolStripLabel> используется совместно с компонентом <xref:System.Windows.Forms.ToolStripComboBox>, который можно раскрыть, чтобы отобразить список элементов, таких как недавно посещенные веб\-узлы.  Если введенный пользователем символ совпадает с первым символом одного из элементов списка, этот элемент отображается автоматически.  
  
> [!NOTE]
>  Автозаполнение для элементов управления `ToolStrip` выполняется так же, как и для традиционных элементов управления, таких как <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.TextBox>.  
  
### Включение автозаполнения для элемента управления ToolStrip  
  
1.  Создайте элемент управления <xref:System.Windows.Forms.ToolStrip> и добавьте в него элементы.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
  
    ```  
  
2.  Свойству <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> метки и поля со списком присвойте значение <xref:System.Windows.Forms.ToolStripItemOverflow>. Это сделает список доступным вне зависимости от размеров формы.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
3.  Добавьте записи в коллекцию элементов элемента управления <xref:System.Windows.Forms.ToolStripComboBox>.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
  
    ```  
  
4.  Свойству <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> поля со списком присвойте значение <xref:System.Windows.Forms.AutoCompleteMode>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
  
    ```  
  
5.  Свойству <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> поля со списком присвойте значение <xref:System.Windows.Forms.AutoCompleteSource>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripLabel>   
 <xref:System.Windows.Forms.ToolStripComboBox>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)