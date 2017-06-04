---
title: "How to: Capture User Input from a PrintDialog at Run Time | Microsoft Docs"
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
  - "print options, changing at run time"
  - "printing [Windows Forms], options"
  - "print options"
  - "run time, changing print options"
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# How to: Capture User Input from a PrintDialog at Run Time
Параметры, относящиеся к печати, можно задать во время разработки, но иногда необходимо изменить их во время выполнения, как правило, из\-за решений, принятых пользователем.  Входные данные пользователя для печати документа можно получить с помощью компонентов <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument>.  
  
### Чтобы изменить параметры печати программными средствами, выполните следующие действия.  
  
1.  Добавьте в форму компоненты <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument>.  
  
2.  Установите для свойства <xref:System.Windows.Forms.PrintDialog.Document%2A> компонента <xref:System.Windows.Forms.PrintDialog> в значение документа <xref:System.Drawing.Printing.PrintDocument>, добавленного в форму.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  Отобразите компонент <xref:System.Windows.Forms.PrintDialog> с помощью метода <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Параметры печати, заданные пользователем в диалоговом окне, будут скопированы в свойство <xref:System.Drawing.Printing.PrinterSettings> компонента <xref:System.Drawing.Printing.PrintDocument>.  
  
## См. также  
 [How to: Print a Multi\-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)