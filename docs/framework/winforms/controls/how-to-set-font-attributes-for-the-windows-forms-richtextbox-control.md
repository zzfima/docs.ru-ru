---
title: "Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fe122f509890715c398bef728a98ff874b61817
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms
Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления поддерживает разнообразные варианты форматирования текста, он отображает. Внесения выделенных символов полужирным, подчеркнутым или курсивом, с помощью <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> свойство. Это свойство также может использоваться для изменения размера и начертания выбранных символов. <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> Свойства можно изменить цвет выделенных символов.  
  
### <a name="to-change-the-appearance-of-characters"></a>Изменение внешнего вида символов  
  
1.  Задать <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> свойства в соответствующий шрифт.  
  
     Чтобы пользователи могли установить семейство шрифтов, размер и начертание шрифта в приложение, обычно используется <xref:System.Windows.Forms.FontDialog> компонента. Его обзор приведен в разделе [Общие сведения о компоненте FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).  
  
2.  Задать <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> свойства неподходящим.  
  
     Чтобы пользователи могли установить цвет в приложении, обычно используется <xref:System.Windows.Forms.ColorDialog> компонента. Его обзор приведен в разделе [Общие сведения о компоненте ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).  
  
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
    >  Эти свойства влияют лишь на выделенный текст или, если никакой текст не выбран, текст, вводимый в текущей позиции курсора. Сведения о выделение текста программными средствами см. в разделе <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.RichTextBox>  
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
