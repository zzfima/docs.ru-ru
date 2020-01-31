---
title: Задание отступов, висячих отступов и маркированных абзацев с помощью элемента управления RichTextBox
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
ms.openlocfilehash: 4dcd5691f328eac6d94675c50ed41a7d7cc36596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743013"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a>Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> имеет множество параметров для форматирования отображаемого текста. Вы можете форматировать выбранные абзацы как маркированные списки, установив свойство <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>. Можно также использовать свойства <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>и <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>, чтобы задать отступы абзацев относительно левого и правого краев элемента управления и левого края других строк текста.  
  
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
  
1. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> целое число, представляющее расстояние в пикселях между левым краями элемента управления и левой границей текста.  
  
2. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> целое число, представляющее расстояние в пикселях между левым краями первой строки текста в абзаце и левым краями последующих строк в том же абзаце. Значение свойства <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> применяется только к строкам в абзаце, которые были заключены под первой строкой.  
  
3. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> целое число, представляющее расстояние в пикселях между правым ребром элемента управления и правым краю текста.  
  
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
    > Все эти свойства влияют на все абзацы, содержащие выделенный текст, а также на текст, который будет вводиться после текущей позиции курсора. Например, когда пользователь выделяет слово в абзаце и затем изменяет параметры отступа, новые параметры будут применяться ко всему абзацу, который содержит это слово, а также ко всем абзацам, которые будут введены после выделенного абзаца. Дополнительные сведения о программном выборе текста см. в разделе <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
