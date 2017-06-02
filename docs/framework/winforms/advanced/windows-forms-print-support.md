---
title: "Windows Forms Print Support | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, printing"
  - "printing [Windows Forms]"
  - "forms, printing (using designer)"
  - "printing, Windows Forms, support"
  - "printing [Windows Forms], print support"
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms Print Support
Печать в формах Windows Forms состоит в основном из использования компонента [Компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) для поддержки печати пользователем и элемента управления [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) с компонентами [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) и [Компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) для предоставления знакомого графического интерфейса пользователям, привыкшим к операционной системе Windows.  
  
 Обычно создается новый экземпляр компонента <xref:System.Drawing.Printing.PrintDocument>, задаются свойства, которые описывают объект печати с помощью классов <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings>, а также вызывается метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> для печати документа.  
  
 В течение сеанса печати из приложения Windows компонент <xref:System.Drawing.Printing.PrintDocument> отображает диалоговое окно прерывания печати, которое оповещает пользователей о начале печати и предоставляет возможность отменить задание.  
  
## В этом подразделе  
 [How to: Create Standard Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 Объясняется использование компонента <xref:System.Drawing.Printing.PrintDocument> для печати из форм Windows Forms  
  
 [How to: Capture User Input from a PrintDialog at Run Time](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Объясняется, как изменить выбранные параметры печати программными средствами с помощью компонента <xref:System.Windows.Forms.PrintDialog>.  
  
 [Практическое руководство. Выбор принтера, подключенного к компьютеру пользователя, в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Описывается смена принтера с помощью компонента <xref:System.Windows.Forms.PrintDialog> во время выполнения.  
  
 [How to: Print Graphics in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 Описывается вывод графики на принтер.  
  
 [How to: Print a Multi\-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Описывается вывод текста на принтер.  
  
 [How to: Complete Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 Объясняются способы оповещения пользователей о завершении задания печати.  
  
 [How to: Print a Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 Показывается, как напечатать копию текущей формы.  
  
 [Практическое руководство. Печать в Windows Forms с использованием предварительного просмотра](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 Показывается, как использовать элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> для печати документа.  
  
## Связанные подразделы  
 [Компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 Объясняется использование компонента <xref:System.Drawing.Printing.PrintDocument>.  
  
 [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 Объясняется использование компонента <xref:System.Windows.Forms.PrintDialog>.  
  
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 Объясняется использование элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
 [Компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 Объясняется использование компонента <xref:System.Windows.Forms.PageSetupDialog>.  
  
 <xref:System.Drawing.Printing>  
 Описываются классы в пространстве имен <xref:System.Drawing.Printing>.