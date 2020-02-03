---
title: Общие сведения об элементе управления RichTextBox
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742405"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Общие сведения об элементе управления RichTextBox (Windows Forms)
Элемент управления <xref:System.Windows.Forms.RichTextBox> Windows Forms используется для отображения, ввода и манипулирования текстом с форматированием. Элемент управления <xref:System.Windows.Forms.RichTextBox> делает все, что делает элемент управления <xref:System.Windows.Forms.TextBox>, но также может отображать шрифты, цвета и ссылки. Загрузка текста и внедренных изображений из файла; и найти указанные символы. Элемент управления <xref:System.Windows.Forms.RichTextBox> обычно используется для работы с текстом и вывода функций, аналогичных приложениям обработки текстов, таким как Microsoft Word. Как и элемент управления <xref:System.Windows.Forms.TextBox>, элемент управления <xref:System.Windows.Forms.RichTextBox> может отображать полосы прокрутки; но в отличие от элемента управления <xref:System.Windows.Forms.TextBox> его параметром по умолчанию является отображение горизонтальных и вертикальных полос прокрутки по мере необходимости, а также дополнительных параметров полосы прокрутки.  
  
## <a name="working-with-the-richtextbox-control"></a>Работа с элементом управления RichTextBox  
 Как и в случае с элементом управления <xref:System.Windows.Forms.TextBox>, отображаемый текст задается свойством <xref:System.Windows.Forms.RichTextBox.Text%2A>. Элемент управления <xref:System.Windows.Forms.RichTextBox> имеет множество свойств для форматирования текста. Дополнительные сведения об этих свойствах см. в разделе [Практическое руководство. Задание атрибутов шрифта для элемента управления RichTextBox в Windows Forms](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) и [Практическое руководство. Задание отступов, выступов и маркеров абзацев с помощью элемента управления RichTextBox в Windows Forms](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Для работы с файлами методы <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> и <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> могут отображать и записывать несколько форматов файлов, включая обычный текст, обычный текст в Юникоде и формат RTF. Возможные форматы файлов перечислены в <xref:System.Windows.Forms.RichTextBoxStreamType>. Для поиска строк текста или отдельных символов можно использовать метод <xref:System.Windows.Forms.RichTextBox.Find%2A>.  
  
 Для веб-ссылок можно также использовать элемент управления <xref:System.Windows.Forms.RichTextBox>, задав свойству <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> значение `true` и записав код для работы с событием <xref:System.Windows.Forms.RichTextBox.LinkClicked>. Дополнительные сведения см. в разделе [Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Можно запретить пользователю манипулировать некоторым или любым текстом в элементе управления, установив для свойства <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> значение `true`.  
  
 Вы можете отменить и повторить большинство операций правки в элементе управления <xref:System.Windows.Forms.RichTextBox>, вызвав методы <xref:System.Windows.Forms.TextBoxBase.Undo%2A> и <xref:System.Windows.Forms.RichTextBox.Redo%2A>. Метод <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> позволяет определить, можно ли повторно применить последнюю операцию, отмененную пользователем, к элементу управления.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
