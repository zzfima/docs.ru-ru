---
title: Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: 9d095e3561cd346e6dbd99d1be7468f6ad5725a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960458"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a>Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms
Элемент управления <xref:System.Windows.Forms.RichTextBox> Windows Forms имеет множество параметров для форматирования отображаемого текста. Вы можете отформатировать выбранные абзацы как маркированные списки <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> , задав свойство. Можно также использовать <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>свойства, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>и <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> для установки отступов абзацев относительно левого и правого краев элемента управления и левого края других строк текста.  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a>Форматирование абзаца в виде маркированного списка  
  
1. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> значение `true`.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a>Чтобы задать отступ абзаца  
  
1. Задайте для <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> свойства целое число, представляющее расстояние в пикселях между левым краями элемента управления и левой границей текста.  
  
2. Задайте для <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> свойства целое число, представляющее расстояние в пикселях между левым краями первой строки текста в абзаце и левым краями последующих строк в одном абзаце. Значение <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> свойства применяется только к строкам в абзаце, которые были заключены под первой строкой.  
  
3. Задайте для <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> свойства целое число, представляющее расстояние в пикселях между правым ребром элемента управления и правым краю текста.  
  
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
    > Все эти свойства влияют на все абзацы, содержащие выделенный текст, а также на текст, который будет вводиться после текущей позиции курсора. Например, когда пользователь выделяет слово в абзаце и затем изменяет параметры отступа, новые параметры будут применяться ко всему абзацу, который содержит это слово, а также ко всем абзацам, которые будут введены после выделенного абзаца. Дополнительные сведения о выборе текста программным способом <xref:System.Windows.Forms.TextBoxBase.Select%2A>см. в разделе.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
