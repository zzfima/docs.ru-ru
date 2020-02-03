---
title: Отображение полос прокрутки в элементе управления RichTextBox
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745561"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms
По умолчанию элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> отображает горизонтальные и вертикальные полосы прокрутки по мере необходимости. Существует семь возможных значений свойства <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> элемента управления <xref:System.Windows.Forms.RichTextBox>, которые описаны в таблице ниже.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Отображение полос прокрутки в элементе управления RichTextBox  
  
1. Установите свойство <xref:System.Windows.Forms.RichTextBox.Multiline%2A> в значение `true`. Без типа полосы прокрутки, включая горизонтальное, будет отображаться, если свойство <xref:System.Windows.Forms.RichTextBox.Multiline%2A> имеет значение `false`.  
  
2. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> соответствующее значение перечисления <xref:System.Windows.Forms.RichTextBoxScrollBars>.  
  
    |Значение|Description|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (по умолчанию)|Отображает горизонтальную или вертикальную полосу прокрутки или оба значения, только если текст превышает ширину или длину элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Никогда не отображает ни одного типа полосы прокрутки.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Отображает горизонтальную полосу прокрутки только в том случае, если текст превышает ширину элемента управления. (Чтобы это произошло, свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> должно быть присвоено значение `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Отображает вертикальную полосу прокрутки, только если текст превышает высоту элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Отображает горизонтальную полосу прокрутки, если свойство <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> имеет значение `false`. Полоса прокрутки отображается серым цветом, если текст не превышает ширину элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Всегда отображает вертикальную полосу прокрутки. Полоса прокрутки отображается серым цветом, если текст не превышает длину элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Всегда отображает вертикальную полосу прокрутки. Отображает горизонтальную полосу прокрутки, если свойство <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> имеет значение `false`. Полосы прокрутки отображаются серым цветом, если текст не превышает ширину или длину элемента управления.|  
  
3. Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.  
  
    |Значение|Description|  
    |-----------|-----------------|  
    |`false`|Текст в элементе управления не корректируется автоматически в соответствии с шириной элемента управления, поэтому он прокручивается вправо, пока не будет достигнут разрыв строки. Используйте это значение, если выбраны горизонтальные полосы прокрутки или оба.|  
    |`true` (по умолчанию)|Текст в элементе управления автоматически настраивается в соответствии с шириной элемента управления. Горизонтальная полоса прокрутки не будет отображаться. Используйте это значение, если для отображения одного или нескольких абзацев выбраны вертикальные полосы прокрутки или нет.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
