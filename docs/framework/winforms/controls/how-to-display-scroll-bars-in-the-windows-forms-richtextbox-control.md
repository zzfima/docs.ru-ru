---
title: "Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms | Microsoft Docs"
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
  - "RichTextBox - элемент управления [Windows Forms], отображение полос прокрутки"
  - "полосы прокрутки, отображение в элементах управления"
  - "текстовые поля, отображение полос прокрутки"
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms
По умолчанию в элементе управления Windows Forms <xref:System.Windows.Forms.RichTextBox> в случае необходимости отображаются горизонтальная и вертикальная полосы прокрутки.  Существует семь возможных значений свойства <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> элемента управления <xref:System.Windows.Forms.RichTextBox>, которые описаны в расположенной ниже таблице.  
  
### Чтобы отобразить полосы прокрутки в элементе управления RichTextBox  
  
1.  Установите для свойства <xref:System.Windows.Forms.RichTextBox.Multiline%2A> значение `true`.  Если свойство <xref:System.Windows.Forms.RichTextBox.Multiline%2A> имеет значение `false`, то полосы прокрутки, включая горизонтальную, отображаться не будут.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> соответствующее значение перечисления <xref:System.Windows.Forms.RichTextBoxScrollBars>.  
  
    |Значение|Описание|  
    |--------------|--------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars> \(по умолчанию\)|Горизонтальная и вертикальная полосы прокрутки отображаются только в том случае, если текст выходит за пределы элемента управления соответственно в ширину или в высоту.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Полосы прокрутки не отображаются ни при каких условиях.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Горизонтальная полоса прокрутки отображается только в том случае, если текст выходит за вертикальный край элемента управления.  \(Для этого свойство <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> должно иметь значение `false`.\)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Вертикальная полоса прокрутки отображается только в том случае, если текст выходит за нижний край элемента управления.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Горизонтальная полоса прокрутки отображается, если свойство <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> имеет значение `false`.  Если текст не выходит за правый край элемента управления, полоса прокрутки будет отображена, но недоступна.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Вертикальная полоса прокрутки отображается всегда.  Если текст не выходит за нижний край элемента управления, полоса прокрутки будет отображена, но недоступна.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Вертикальная полоса прокрутки отображается всегда.  Горизонтальная полоса прокрутки отображается, если свойство <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> имеет значение `false`.  Если текст не выходит за пределы элемента управления, полосы прокрутки будут отображены, но недоступны.|  
  
3.  Присвойте соответствующее значение свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>.  
  
    |Значение|Описание|  
    |--------------|--------------|  
    |`false`|Выключает автоматический перенос по словам. Текст в элементе управления будет прокручиваться вправо, пока не будет достигнут конец строки.  Это значение используется, если было выбрано отображение горизонтальной полосы прокрутки или обеих полос \(см. выше\).|  
    |`true` \(по умолчанию\)|Включает автоматический перенос по словам — текст в элементе управления всегда будет умещаться в нем в ширину.  Горизонтальная полоса прокрутки не отображается.  Это значение используется, если для одного или нескольких абзацев было выбрано отображение с вертикальными полосами прокрутки или без полос прокрутки.|  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>   
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)