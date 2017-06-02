---
title: "Практическое руководство. Отображение компонента PrintDialog | Microsoft Docs"
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
  - "Печать - диалоговое окно, отображение"
  - "PrintDialog - компонент [Windows Forms], отображение"
  - "печать [Windows Forms], отображение диалоговое окно Печать"
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Отображение компонента PrintDialog
Компонент <xref:System.Windows.Forms.PrintDialog> является стандартным диалоговым окном печати в Windows, хорошо знакомым пользователям.  Поскольку пользователям будет удобно работать с этим окном, использование компонента <xref:System.Windows.Forms.PrintDialog> очень полезно.  
  
### Чтобы отобразить компонент PrintDialog  
  
-   Вызовите метод <xref:System.Windows.Forms.Form.ShowDialog%2A> в коде приложения.  
  
     После отображения этого компонента пользователи смогут с его помощью определять свойства задания печати.  Они сохраняются в классе [PrinterSettings](frlrfSystemDrawingPrintingPrinterSettingsMembersTopic) \(и классе [PageSettings](frlrfSystemDrawingPrintingPageSettingsMembersTopic), если пользователь получает доступ к [Компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) через компонент <xref:System.Windows.Forms.PrintDialog>\), связанном с этим заданием печати.  Затем можно вызывать эти свойства, которые задаются для определения специфики заданий печати.  
  
## См. также  
 [How to: Create Standard Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)   
 [How to: Capture User Input from a PrintDialog at Run Time](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)   
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)