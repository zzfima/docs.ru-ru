---
title: Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 5588aad5b2e38716c628947c6e06365e7053eb5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms
По умолчанию в Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления отображает горизонтальные и вертикальные полосы прокрутки при необходимости. Существует семь возможных значений для <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> свойства <xref:System.Windows.Forms.RichTextBox> элемента управления, которые описаны в следующей таблице.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Для отображения полос прокрутки в элементе управления RichTextBox  
  
1.  Задайте для свойства <xref:System.Windows.Forms.RichTextBox.Multiline%2A> значение `true`. Нет типа полосы прокрутки, включая горизонтальной, отображается в том случае, если <xref:System.Windows.Forms.RichTextBox.Multiline%2A> свойству `false`.  
  
2.  Задать <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> соответствующее значение свойства <xref:System.Windows.Forms.RichTextBoxScrollBars> перечисления.  
  
    |Значение|Описание|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (по умолчанию)|Отображение полос прокрутки по горизонтальной или вертикальной (или оба) только в том случае, если длина текста превышает ширину или длина элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Не отображаются ни полосы прокрутки.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Отображает полосу только если длина текста превышает ширину элемента управления горизонтальной прокрутки. (Чтобы это происходило, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству необходимо присвоить значение `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Вертикальная полоса прокрутки отображается только при текст выходит высоту элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Отображение горизонтальной полосы наблюдают прокрутки <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству `false`. Полоса прокрутки отображается серым цветом, если текст не превышает ширину элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Вертикальная полоса прокрутки отображается всегда. Полоса прокрутки отображается серым цветом, если текст не превышает длину элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Вертикальная полоса прокрутки отображается всегда. Отображение горизонтальной полосы наблюдают прокрутки <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству `false`. Полосы прокрутки отображаются выделена серым цветом, если текст не должна превышать пределы элемента управления.|  
  
3.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.  
  
    |Значение|Описание|  
    |-----------|-----------------|  
    |`false`|Текст в элементе управления не настраивается автоматически по ширине элемента управления, поэтому будет прокрутите окно вправо до достижения конца строки. Это значение используется при выборе горизонтальные полосы прокрутки, или в оба выше.|  
    |`true` (по умолчанию)|Текст в элементе управления автоматически корректируется по ширине элемента управления. Горизонтальная полоса прокрутки отображаться не будут. Это значение используется в том случае, если вы выбрали вертикальных полос прокрутки или нет, выше, для отображения один или несколько абзацев.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
