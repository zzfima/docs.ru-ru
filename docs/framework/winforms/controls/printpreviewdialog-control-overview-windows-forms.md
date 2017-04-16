---
title: "Общие сведения об элементе управления PrintPreviewDialog (Windows Forms) | Microsoft Docs"
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
  - "PrintPreviewDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintPreviewDialog - элемент управления (использование конструктора), сведения о PrintPreviewDialog"
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> — это стандартное диалоговое окно, используемое для просмотра объекта [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) в том виде, как он будет напечатан.  Он может использоваться в приложениях Windows в качестве готового решения, избавляя от необходимости создания собственного диалогового окна.  В нем имеются кнопки для печати, изменения масштаба, отображения одной или нескольких страниц, а также для закрытия диалогового окна.  
  
## Ключевые свойства и методы  
 Ключевым свойством этого элемента управления является свойство <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, определяющее документ, который требуется просмотреть.  Этот документ должен являться объектом <xref:System.Drawing.Printing.PrintDocument>.  Для отображения диалогового окна вызывается метод <xref:System.Windows.Forms.Form.ShowDialog%2A>.  Сглаживание служит для отображения текста без неровностей, однако оно может привести к замедлению отображения. Чтобы применить сглаживание, следует задать для свойства <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> значение `true`.  
  
 Доступ к некоторым свойствам можно получить с помощью элемента управления <xref:System.Windows.Forms.PrintPreviewControl>, содержащегося в компоненте <xref:System.Windows.Forms.PrintPreviewDialog>.  \(Компонент <xref:System.Windows.Forms.PrintPreviewControl> не требуется добавлять в форму; он автоматически включается в элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> при добавлении диалогового окна в форму.\) Примерами свойств, доступных с помощью элемента управления <xref:System.Windows.Forms.PrintPreviewControl>, являются свойства <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, которые определяют число страниц, отображающихся в элементе управления по вертикали или по горизонтали.  Чтобы получить доступ к свойству <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> воспользуйтесь свойством `PrintPreviewDialog1.PrintPreviewControl.Columns` в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], свойством `printPreviewDialog1.PrintPreviewControl.Columns` в [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] или свойством `printPreviewDialog1->PrintPreviewControl->Columns` в [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## См. также  
 <xref:System.Windows.Forms.PrintPreviewDialog>   
 [Общие сведения об элементе управления PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)   
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Элементы управления и компоненты диалоговых окон](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)