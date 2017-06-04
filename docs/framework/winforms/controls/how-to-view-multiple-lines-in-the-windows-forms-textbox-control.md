---
title: "Практическое руководство. Многострочные элементы управления TextBox в Windows Forms | Microsoft Docs"
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
  - "возврат каретки"
  - "CRLF"
  - "конец строки"
  - "перевод строки"
  - "MultiLine - свойство (элемент управления TextBox)"
  - "NewLine"
  - "ScrollBars - свойство, в элементе управления TextBox"
  - "TextBox - элемент управления [Windows Forms], просмотр нескольких строк"
  - "WordWrap - свойство"
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Многострочные элементы управления TextBox в Windows Forms
По умолчанию в элементе управления Windows Forms <xref:System.Windows.Forms.TextBox> отображается одна строка текста без полос прокрутки.  Если длина текста превышает размер доступного пространства, отображается лишь часть текста.  Эту стандартную настройку можно изменить, присваивая соответствующие значения свойствам <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> и <xref:System.Windows.Forms.TextBox.ScrollBars%2A>.  
  
### Отображение возврата каретки в элементе управления TextBox  
  
-   Для отображения возврата каретки в многострочном элементе управления <xref:System.Windows.Forms.TextBox> используется свойство <xref:System.Environment.NewLine%2A>.  
  
     Обратите внимание, что интерпретация escape\-символов \(\\\) зависит от языка.  В Visual Basic в качестве сочетания символов возврата каретки и перевода строки используется сочетание `Chr$(13) & Chr$(10)`.  
  
### Просмотр нескольких строк в элементе управления TextBox  
  
1.  Установите для свойства <xref:System.Windows.Forms.TextBox.Multiline%2A> значение `true`.  Если свойство <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> имеет значение `true` \(принимается по умолчанию\), то текст в элементе управления будет отображаться в виде одного или нескольких абзацев; в противном случае он отображается в виде списка строк, причем некоторые строки могут быть обрезаны по краю элемента управления.  
  
2.  Присвойте соответствующее значение свойству <xref:System.Windows.Forms.TextBox.ScrollBars%2A>.  
  
    |Значение|Описание|  
    |--------------|--------------|  
    |<xref:System.Windows.Forms.ScrollBars>|Это значение следует использовать, если текст будет иметь вид абзаца и преимущественно вмещаться в элемент управления.  Пользователь может использовать указатель мыши для перемещения по тексту внутри элемента управления, если текст не удается сразу отобразить полностью.|  
    |<xref:System.Windows.Forms.ScrollBars>|Это значение следует использовать, если требуется отобразить список строк, в котором длина некоторых строк может превышать ширину элемента управления <xref:System.Windows.Forms.TextBox>.|  
    |<xref:System.Windows.Forms.ScrollBars>|Это значение следует использовать, если список может быть больше, чем позволяет вместить элемент управления по высоте.|  
  
3.  Присвойте соответствующее значение свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>.  
  
    |Значение|Описание|  
    |--------------|--------------|  
    |`false`|Текст в элементе управления не переносится автоматически; он прокручивается вправо, пока не будет достигнут конец строки.  Это значение используется, если было выбрано отображение с горизонтальной полосой прокрутки \(<xref:System.Windows.Forms.ScrollBars>, см. выше\) или с обеими полосами \(<xref:System.Windows.Forms.ScrollBars>\).|  
    |`true` \(по умолчанию\)|Горизонтальная полоса прокрутки не отображается.  Это значение используется, если для отображения одного или нескольких абзацев был выбран режим с вертикальными полосами прокрутки \(<xref:System.Windows.Forms.ScrollBars>, см. выше\) или без полос прокрутки \(<xref:System.Windows.Forms.ScrollBars>\).|  
  
## См. также  
 <xref:System.Windows.Forms.TextBox>   
 [Общие сведения об элементе управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Практическое руководство. Создание текстового поля только для чтения](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Практическое руководство. Добавление кавычек в строку](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Элемент управления TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)