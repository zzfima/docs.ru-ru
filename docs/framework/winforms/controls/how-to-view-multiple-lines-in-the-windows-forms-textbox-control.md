---
title: Как выполнить Просмотр нескольких строк в элементе управления Windows Forms TextBox
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
ms.openlocfilehash: 11047b9308905b153662c5449abeeae8c23af26c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565635"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Как выполнить Просмотр нескольких строк в элементе управления Windows Forms TextBox
По умолчанию в Windows Forms <xref:System.Windows.Forms.TextBox> элемент управления выводит одну строку текста и не отображает полосы прокрутки. Если текст длиннее, чем свободное пространство, отображается только часть текста. Это поведение по умолчанию можно изменить, задав <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, и <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующие значения свойств.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Для отображения возврата каретки в элементе управления TextBox  
  
-   Для отображения возврата каретки в многострочном <xref:System.Windows.Forms.TextBox>, используйте <xref:System.Environment.NewLine%2A> свойство.  
  
     Имейте в виду, что интерпретация escape-символы (\\) зависит от конкретного языка. Visual Basic использует `Chr$(13) & Chr$(10)` для сочетания символов возврата и перевода строки каретки.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Чтобы просмотреть несколько строк в элементе управления TextBox  
  
1.  Задайте для свойства <xref:System.Windows.Forms.TextBox.Multiline%2A> значение `true`. Если <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> является `true` (по умолчанию), затем будет отображаться как один или несколько абзацев текст в элементе управления; в противном случае он будет отображаться в виде списка, в которой некоторые строки могут быть обрезаны на границе элемента управления.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующее значение.  
  
    |Значение|Описание:|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Используйте это значение, если текст будет выровнен по абзаца, вмещаться элементе управления. Пользователь может использовать указатель мыши для перемещения внутри элемента управления, если текст слишком велика, чтобы отобразить все сразу.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Используйте это значение, если вы хотите отобразить список строк, некоторые из которых может превышать ширину <xref:System.Windows.Forms.TextBox> элемента управления.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Это значение используется в том случае, если список может быть больше времени, чем высота элемента управления.|  
  
3.  Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.  
  
    |Значение|Описание|  
    |-----------|-----------------|  
    |`false`|Текст в элементе управления будет не переносится автоматически, поэтому он будет прокручивать экран вправо до достижения конца строки. Используйте это значение, если вы выбрали <xref:System.Windows.Forms.ScrollBars.Horizontal> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.Both>выше.|  
    |`true` (по умолчанию)|Горизонтальная полоса прокрутки не появится. Используйте это значение, если вы выбрали <xref:System.Windows.Forms.ScrollBars.Vertical> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.None>выше, чтобы отобразить один или несколько абзацев.|  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление положением курсора в элементе управления Windows Forms TextBox](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Создать только для чтения текстовое поле](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделите текст в элементе управления Windows Forms TextBox](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
