---
title: Установка атрибутов шрифта для элемента управления RichTextBox
ms.date: 03/30/2017
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
ms.openlocfilehash: f27256c155223df576ee3c42e6bf65270c870b0f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744862"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> имеет множество параметров для форматирования отображаемого текста. Можно сделать выбранные символы полужирным, подчеркнутым или курсивом с помощью свойства <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>. Это свойство также может использоваться для изменения размера и начертания выбранных символов. Свойство <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> позволяет изменить цвет выбранных символов.  
  
### <a name="to-change-the-appearance-of-characters"></a>Изменение внешнего вида символов  
  
1. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> соответствующий шрифт.  
  
     Чтобы разрешить пользователям задавать семейство шрифтов, размер и гарнитуру в приложении, обычно используется компонент <xref:System.Windows.Forms.FontDialog>. Его обзор приведен в разделе [Общие сведения о компоненте FontDialog](fontdialog-component-overview-windows-forms.md).  
  
2. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> соответствующий цвет.  
  
     Чтобы разрешить пользователям задавать цвет в приложении, обычно используется компонент <xref:System.Windows.Forms.ColorDialog>. Его обзор приведен в разделе [Общие сведения о компоненте ColorDialog](colordialog-component-overview-windows-forms.md).  
  
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
    > Эти свойства влияют лишь на выделенный текст или, если никакой текст не выбран, текст, вводимый в текущей позиции курсора. Сведения о программном выборе текста см. в разделе <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
