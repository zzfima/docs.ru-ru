---
title: Общие сведения об элементе управления RichTextBox (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 53c4cd41cf203886c93291debc7bca4f395f9698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="richtextbox-control-overview-windows-forms"></a>Общие сведения об элементе управления RichTextBox (Windows Forms)
Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления используется для отображения, ввода и изменения текста с форматированием. <xref:System.Windows.Forms.RichTextBox> Элемент управления выполняет все, что <xref:System.Windows.Forms.TextBox> делает элемент управления, но можно также отображать шрифты, цвета и ссылки; загрузить текст и изображения из файла; и поиск определенных символов. <xref:System.Windows.Forms.RichTextBox> Элемент управления обычно используется для работы с текстом и отображения функций, как для текстовых редакторов, таких как Microsoft Word. Как <xref:System.Windows.Forms.TextBox> управления <xref:System.Windows.Forms.RichTextBox> элемент управления может отображать полосы прокрутки; но в отличие от <xref:System.Windows.Forms.TextBox> элемента управления, его значение по умолчанию является отображение горизонтальные и вертикальные полосы прокрутки при необходимости, и его параметры дополнительной полосы прокрутки.  
  
## <a name="working-with-the-richtextbox-control"></a>Работа с элементом управления RichTextBox  
 Как и в <xref:System.Windows.Forms.TextBox> управления, отображаемый текст задается <xref:System.Windows.Forms.RichTextBox.Text%2A> свойство. <xref:System.Windows.Forms.RichTextBox> Управления имеется множество свойств для форматирования текста. Дополнительные сведения об этих свойствах см. в разделе [Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) и [Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Для работы с файлами, <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> и <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> методы можно отображать и записи нескольких файловых форматах, включая обычный текст, текст в Юникоде и форматированный текст (RTF). Возможные форматы, перечислены в <xref:System.Windows.Forms.RichTextBoxStreamType>. Можно использовать <xref:System.Windows.Forms.RichTextBox.Find%2A> метод для поиска строк текста или определенные символы.  
  
 Можно также использовать <xref:System.Windows.Forms.RichTextBox> управления версиями для веб-ссылок, задав <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> свойства `true` и написание кода для обработки <xref:System.Windows.Forms.RichTextBox.LinkClicked> событий. Дополнительные сведения см. в разделе [Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Можно запретить управление некоторые или все из текста в элементе управления, задав пользователя <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> свойства `true`.  
  
 Можно отменять и повторять большинство операций редактирования в <xref:System.Windows.Forms.RichTextBox> управления путем вызова <xref:System.Windows.Forms.TextBoxBase.Undo%2A> и <xref:System.Windows.Forms.RichTextBox.Redo%2A> методы. <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> Метод позволяет определить ли последняя операция пользователем повторно применить к элементу управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.RichTextBox>  
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
