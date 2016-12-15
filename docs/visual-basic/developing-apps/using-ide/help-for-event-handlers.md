---
title: "Справка для обработчиков событий в коде Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CheckedListBox1_SelectedIndexChanged"
  - "Calendar1_SelectionChanged"
  - "Form1_Load"
  - "DropDownList1_SelectedIndexChanged"
  - "TextBox1_TextChanged"
  - "ListBox1_SelectedIndexChanged"
  - "TreeView1_AfterSelect"
  - "MaskedTextBox1_MaskInputRejected"
  - "Menu1_MenuItemClick"
  - "TabPage1_Click"
  - "LinkButton1_Click"
  - "CheckBoxList1_SelectedIndexChanged"
  - "ProgressBar1_Click"
  - "ToolStripButton1_Click"
  - "ImageButton1_Click"
  - "RadioButtonList1_SelectedIndexChanged"
  - "PictureBox1_Click"
  - "Label1_Click"
  - "ToolStrip1_ItemClicked"
  - "RichTextBox1_TextChanged"
  - "ListView1_SelectedIndexChanged"
  - "PrintPreviewControl1_Click"
  - "ComboBox1_SelectedIndexChanged"
  - "Button1_Click"
  - "Page_Load"
  - "TrackBar1_Scroll"
  - "WebBrowser1_DocumentCompleted"
  - "TreeView1_SelectedNodeChanged"
  - "CheckBox1_CheckedChanged"
  - "RadioButton1_CheckedChanged"
  - "NotifyIcon1_MouseDown"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "обработчики событий, получение справка при нажатии клавиши F1 в коде Visual Basic"
ms.assetid: 2c92decf-844e-4ba4-82c7-f2fc0adc3002
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Справка для обработчиков событий в коде Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Чтобы получить справку по конкретному обработчику событий в редакторе кода, поместите курсор на предложение `Handles` в конце процедуры обработки события и нажмите клавишу F1.  Например, в предложении `Form1_Load` ниже следует поместить курсор в элемент `MyBase.Load`.  
  
```  
Private Sub Form1_Load(ByVal sender As System.Object,   
    ByVal e As System.EventArgs) Handles MyBase.Load  
  
End Sub  
```  
  
## См. также  
 [События](../Topic/Handling%20and%20Raising%20Events.md)   
 [Event Handlers Overview](../Topic/Event%20Handlers%20Overview%20\(Windows%20Forms\).md)