---
title: "Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms | Microsoft Docs"
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
  - "шрифты, изменение атрибутов в элементе управления RichTextBox"
  - "форматирование [Windows Forms]"
  - "RichTextBox - элемент управления [Windows Forms], задание атрибутов шрифтов"
  - "RTF-файлы, форматирование в элементе управления RichTextBox"
  - "текст [Windows Forms]"
  - "текстовые поля, форматирование текста"
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> поддерживает разнообразные варианты форматирования отображаемого в нем текста.  Выбранные знаки можно выделить жирным, подчеркиванием или курсивом при помощи свойства <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>.  Это свойство можно также использовать для изменения размера и начертания выбранных знаков.  Свойство <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> позволяет изменять цвет выбранных знаков.  
  
### Изменение внешнего вида знаков  
  
1.  Присвойте соответствующее значение шрифта свойству <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>.  
  
     Чтобы обеспечить пользователям приложения возможность выбора семейства шрифтов, размера и начертания шрифта, обычно используется компонент <xref:System.Windows.Forms.FontDialog>.  Для получения общих сведений см. [Общие сведения о компоненте FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).  
  
2.  Присвойте соответствующее значение цвета свойству <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>.  
  
     Чтобы обеспечить пользователям приложения возможность выбора цвета, обычно используется компонент <xref:System.Windows.Forms.ColorDialog>.  Для получения общих сведений см. [Общие сведения о компоненте ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  Эти свойства влияют лишь на выделенный текст или, если текст не выделен, на тот текст, который будет вводиться в текущей позиции курсора.  Сведения о выборе текста программно см. в разделе [Метод TextBoxBase.Select](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic).  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)