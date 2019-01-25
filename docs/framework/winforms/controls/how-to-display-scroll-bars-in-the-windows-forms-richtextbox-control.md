---
title: Как выполнить Отображение полос прокрутки в Windows Forms элемента управления RichTextBox
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 6b6cfb8c21c8f3a48bb85a0591f3390d5b5575b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610400"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Как выполнить Отображение полос прокрутки в Windows Forms элемента управления RichTextBox
По умолчанию в Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления отображает горизонтальные и вертикальные полосы прокрутки при необходимости. Существует семь возможных значений для <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> свойство <xref:System.Windows.Forms.RichTextBox> элемента управления, которые описаны в следующей таблице.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Для отображения полос прокрутки в элементе управления RichTextBox  
  
1.  Задайте для свойства <xref:System.Windows.Forms.RichTextBox.Multiline%2A> значение `true`. Тип не полосы прокрутки, включая горизонтальной, отобразится в том случае, если <xref:System.Windows.Forms.RichTextBox.Multiline%2A> свойству `false`.  
  
2.  Задайте <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> свойства соответствующее значение из <xref:System.Windows.Forms.RichTextBoxScrollBars> перечисления.  
  
    |Значение|Описание:|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (по умолчанию)|Отображает полосы прокрутки по горизонтали или вертикали, так и в, только в том случае, если длина текста превышает ширину или длина элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Не отображаются ни полосы прокрутки.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Отображает горизонтальную полосу прокрутки, только если длина текста превышает ширину элемента управления. (Это произошло, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству должно быть присвоено `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Отображает вертикальную полосу только в том случае, если текст выходит высоту элемента управления прокрутки.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Отображение горизонтальной прокрутки полосы при <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству `false`. Полоса прокрутки отображается серым цветом, если текст не превышает ширину элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Вертикальная полоса прокрутки отображается всегда. Полоса прокрутки отображается серым цветом, если текст не превышает длину элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Вертикальная полоса прокрутки отображается всегда. Отображение горизонтальной прокрутки полосы при <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству `false`. Полосы прокрутки отображаются затененный, когда текст не превышает пределы элемента управления.|  
  
3.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.  
  
    |Значение|Описание|  
    |-----------|-----------------|  
    |`false`|Текст в элементе управления не изменяется автоматически в соответствии с шириной элемента управления, поэтому он будет прокручивать экран вправо до достижения конца строки. Это значение используется в том случае, если вы выбрали горизонтальных полос прокрутки или оба, выше.|  
    |`true` (по умолчанию)|Текст в элементе управления автоматически изменяется в соответствии с шириной элемента управления. Горизонтальная полоса прокрутки не появится. Это значение используется в том случае, если вы выбрали вертикальных полос прокрутки или нет "," выше, для отображения один или несколько абзацев.|  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
