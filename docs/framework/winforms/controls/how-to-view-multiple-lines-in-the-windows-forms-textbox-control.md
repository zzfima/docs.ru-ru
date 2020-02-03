---
title: Просмотр нескольких строк в элементе управления TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728284"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Практическое руководство. Многострочные элементы управления TextBox в Windows Forms
По умолчанию элемент управления Windows Forms <xref:System.Windows.Forms.TextBox> отображает одну строку текста и не отображает полосы прокрутки. Если текст превышает доступное пространство, отображается только часть текста. Это поведение по умолчанию можно изменить, задав для свойств <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>и <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующие значения.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Отображение возврата каретки в элементе управления TextBox  
  
- Чтобы отобразить возврат каретки в многострочном <xref:System.Windows.Forms.TextBox>, используйте свойство <xref:System.Environment.NewLine%2A>.  
  
     Имейте в виду, что интерпретация escape-символов (\\) зависит от языка. Visual Basic использует `Chr$(13) & Chr$(10)` для сочетания символов возврата каретки и перевода строки.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Просмотр нескольких строк в элементе управления TextBox  
  
1. Установите свойство <xref:System.Windows.Forms.TextBox.Multiline%2A> в значение `true`. Если <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `true` (по умолчанию), то текст в элементе управления будет отображаться как один или несколько абзацев. в противном случае он будет отображаться в виде списка, в котором некоторые строки могут быть обрезаны по границе элемента управления.  
  
2. Присвойте свойству <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующее значение.  
  
    |Значение|Description|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Используйте это значение, если текст будет абзацем, который почти всегда соответствует элементу управления. Пользователь может использовать указатель мыши для перемещения внутри элемента управления, если текст слишком длинный, чтобы отобразить все одновременно.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Используйте это значение, если требуется отобразить список строк, некоторые из которых могут быть длиннее ширины элемента управления <xref:System.Windows.Forms.TextBox>.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Используйте это значение, если список может быть длиннее, чем высота элемента управления.|  
  
3. Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.  
  
    |Значение|Description|  
    |-----------|-----------------|  
    |`false`|Текст в элементе управления не будет автоматически заключаться в оболочку, поэтому он будет прокручиваться вправо до тех пор, пока не будет достигнут разрыв строки. Используйте это значение, если выбраны <xref:System.Windows.Forms.ScrollBars.Horizontal> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.Both>выше.|  
    |`true` (по умолчанию)|Горизонтальная полоса прокрутки не будет отображаться. Используйте это значение, если для отображения одного или нескольких абзацев выбраны <xref:System.Windows.Forms.ScrollBars.Vertical> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.None>выше.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля только для чтения](how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Добавление кавычек в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
