---
title: "Общие сведения об элементе управления PrintPreviewControl (Windows Forms) | Microsoft Docs"
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
  - "PrintPreviewControl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "предварительный просмотр"
  - "PrintPreviewControl - элемент управления"
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения об элементе управления PrintPreviewControl (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> используется для отображения объекта [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) в том виде, как он будет напечатан.  В элементе управления <xref:System.Windows.Forms.PrintPreviewControl> отсутствуют кнопки и другие элементы пользовательского интерфейса, поэтому он обычно используется только при необходимости разработки собственного интерфейса пользователя для предварительного просмотра.  При необходимости создать стандартный интерфейс пользователя воспользуйтесь элементом управления <xref:System.Windows.Forms.PrintPreviewDialog>; общие сведения о нем см. в разделе [Общие сведения об элементе управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md).  
  
## Ключевые свойства  
 Ключевым свойством этого элемента управления является свойство <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, задающее документ, который требуется просмотреть.  Этот документ должен являться объектом <xref:System.Drawing.Printing.PrintDocument>.  Общие сведения о создании документов для печати см. в разделах [Общие сведения о компоненте PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) и [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).  Свойства <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> определяют число страниц, отображающихся в элементе управления по вертикали или по горизонтали.  Сглаживание служит для отображения текста без неровностей, однако оно может привести к замедлению отображения; чтобы применить сглаживание, следует задать для свойства <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> значение `true`.  
  
## См. также  
 <xref:System.Windows.Forms.PrintPreviewControl>   
 [Общие сведения об элементе управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)   
 [Элемент управления PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)   
 [Элементы управления и компоненты диалоговых окон](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)