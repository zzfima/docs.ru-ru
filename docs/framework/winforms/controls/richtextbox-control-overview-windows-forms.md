---
title: "Общие сведения об элементе управления RichTextBox (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RichTextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "RichTextBox - элемент управления [Windows Forms], об элементе управления RichTextBox"
  - "текстовые поля, сведения о текстовых полях"
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Общие сведения об элементе управления RichTextBox (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> используется для отображения, ввода и изменения текста с форматированием.  Элемент управления <xref:System.Windows.Forms.RichTextBox> выполняет те же функции, что и элемент управления <xref:System.Windows.Forms.TextBox>, но помимо этого он позволяет отображать шрифты, цвета и ссылки, загружать текст и вложенные изображения из файлов, а также искать заданные знаки.  Элемент управления <xref:System.Windows.Forms.RichTextBox> обычно используется для предоставления возможностей изменения и отображения текста, схожих с возможностями текстовых редакторов, таких как Microsoft Word.  Элемент управления <xref:System.Windows.Forms.RichTextBox>, как и <xref:System.Windows.Forms.TextBox>, позволяет отображать полосы прокрутки, однако в отличие от <xref:System.Windows.Forms.TextBox>, он по умолчанию отображает и горизонтальную, и вертикальную полосы прокрутки в зависимости от необходимости, а также поддерживает дополнительные параметры их настройки.  
  
## Работа с элементом управления RichTextBox  
 Как и для элемента управления <xref:System.Windows.Forms.TextBox>, отображаемый текст задается свойством <xref:System.Windows.Forms.RichTextBox.Text%2A>.  В элементе управления <xref:System.Windows.Forms.RichTextBox> содержится множество свойств для форматирования текста.  Сведения об этих свойствах см. в разделах [Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) и [Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md).  Для управления файлами используются методы <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> и <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>, отображающие и сохраняющие множество форматов файлов, в том числе обычный текст, обычный текст Юникод и форматируемый текст \(RTF\).  Возможные форматы файлов представлены в [Перечислении RichTextBoxStreamType](frlrfSystemWindowsFormsRichTextBoxStreamTypeClassTopic).  С помощью метода <xref:System.Windows.Forms.RichTextBox.Find%2A> выполняется поиск текстовых строк или определенных символов.  
  
 Элемент управления <xref:System.Windows.Forms.RichTextBox> можно также использовать для создания веб\-ссылок; для этого надо задать для свойства <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> значение `true` и создать код для обработки события <xref:System.Windows.Forms.RichTextBox.LinkClicked>.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение ссылок веб\-типа с помощью элемента управления RichTextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md).  Можно запретить пользователю управлять частью текста или всем текстом в элементе управления, задав для свойства <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> значение `true`.  
  
 Большую часть операций редактирования в элементе управления <xref:System.Windows.Forms.RichTextBox> можно отменить и восстановить с помощью вызова методов <xref:System.Windows.Forms.TextBoxBase.Undo%2A> и <xref:System.Windows.Forms.RichTextBox.Redo%2A>.  Метод <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> позволяет определить, можно ли заново применить выполненное последним и отмененное действие, к элементу управления.  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)