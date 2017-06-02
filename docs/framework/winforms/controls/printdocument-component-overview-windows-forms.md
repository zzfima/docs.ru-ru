---
title: "Общие сведения о компоненте PrintDocument (Windows Forms) | Microsoft Docs"
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
  - "PrintDocument"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintDocument - компонент [Windows Forms], сведения о компоненте PrintDocument"
  - "печать [Windows Forms], компонент PrintDocument"
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Общие сведения о компоненте PrintDocument (Windows Forms)
Компонент форм Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) используется для задания свойств, описывающих печатаемый объект, и для организации печати документа в приложениях Windows.  Его можно использовать в сочетании с компонентом [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) для управления всеми аспектами печати документа.  
  
## Использование компонента PrintDocument  
 Ниже описаны два основных сценария, в которых используется компонент <xref:System.Drawing.Printing.PrintDocument>.  
  
-   Простые задания печати, например печать отдельного текстового файла.  В этом случае компонент <xref:System.Drawing.Printing.PrintDocument> добавляется в форму Windows Forms, а затем добавляется программный алгоритм, печатающий файл в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  Для печати документа программный алгоритм должен завершаться методом <xref:System.Drawing.Printing.PrintDocument.Print%2A>.  Этот метод посылает на принтер объект <xref:System.Drawing.Graphics>, который содержится в свойстве <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs>.  Пример печати текстового документа с использованием компонента <xref:System.Drawing.Printing.PrintDocument> см. в разделе [How to: Print a Multi\-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Более сложные задания печати, например в тех случаях, когда требуется повторно применить написанный программный алгоритм.  В этом случае необходимо произвести новый компонент из компонента <xref:System.Drawing.Printing.PrintDocument> и переопределить \(см. [Переопределение](../Topic/Overrides%20\(Visual%20Basic\).md) для Visual Basic или [Переопределение](../Topic/override%20\(C%23%20Reference\).md) для C\#\) событие <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
 Добавленный в форму компонент <xref:System.Drawing.Printing.PrintDocument> появляется в нижней области конструктора Windows Forms.  
  
## См. также  
 <xref:System.Drawing.Graphics>   
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)