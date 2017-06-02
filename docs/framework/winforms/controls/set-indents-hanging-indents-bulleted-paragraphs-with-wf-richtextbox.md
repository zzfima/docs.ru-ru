---
title: "Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms | Microsoft Docs"
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
  - "RTF-файлы, форматирование в элементе управления RichTextBox"
  - "примеры [Windows Forms], текстовые поля"
  - "RichTextBox - элемент управления [Windows Forms], установка отступов и маркеров"
  - "RTF-файлы, форматирование в элементе управления RichTextBox"
  - "текстовые поля, маркеры"
  - "текстовые поля, установка отступов"
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> поддерживает разнообразные варианты форматирования отображаемого в нем текста.  С помощью свойства <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> можно форматировать выделенные абзацы в виде маркированных списков.  Также можно использовать свойства <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> и <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> для установки отступа абзаца относительно левого и правого краев элемента управления, а также относительно левого края остальных строк текста.  
  
### Чтобы отформатировать абзац в виде маркированного списка  
  
1.  Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> значение `true`.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### Чтобы задать отступ абзаца  
  
1.  Присвойте свойству <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> целое значение, равное требуемому расстоянию в пикселях между левым краем элемента управления и левым краем текста.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> целое значение, равное требуемому расстоянию в пикселях между началом первой строки абзаца и началом остальных строк того же абзаца.  Значение свойства <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> применяется только к строкам абзаца, следующим за первой строкой.  
  
3.  Присвойте свойству <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> целое значение, равное требуемому расстоянию в пикселях между правым краем элемента управления и правым краем текста.  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  Все эти свойства влияют на абзацы, в которых выделены какие\-либо фрагменты, а также на текст, который будет вводиться после текущей позиции курсора.  Например, если пользователь выделяет слово в абзаце и затем изменяет параметры отступа, то новые параметры будут применены ко всему абзацу с выделенным словом, а также ко всем абзацам, которые будут введены после этого абзаца.  Сведения о выборе текста программно см. в разделе [Метод TextBoxBase.Select](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic).  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)