---
title: "Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c898dc24c9a4418e3af45fce507e6befcf905a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Общие сведения об элементе управления PrintPreviewDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> управления является стандартным диалоговым окном, используемый для отображения как [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) будет выглядеть при печати. Он используется в приложении Windows в качестве простого решения вместо настройки собственного диалогового. Элемент управления содержит кнопки для печати, увеличения масштаба, отображения одной или нескольких страниц и закрытия диалогового окна.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Ключевое свойство элемента управления <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, который задает документ для предварительного просмотра. Документ должен быть <xref:System.Drawing.Printing.PrintDocument> объекта. Чтобы открыть диалоговое окно, необходимо вызвать его <xref:System.Windows.Forms.Form.ShowDialog%2A> метод. Сглаживание можно увеличить гладкую текст, но оно может привести к замедлению отображения; Чтобы использовать его, установите <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> свойства `true`.  
  
 Некоторые свойства доступны через <xref:System.Windows.Forms.PrintPreviewControl> , <xref:System.Windows.Forms.PrintPreviewDialog> содержит. (Необходимо добавить это <xref:System.Windows.Forms.PrintPreviewControl> форме; он автоматически внутри <xref:System.Windows.Forms.PrintPreviewDialog> при добавлении диалогового окна в форму.) Примеры свойств, доступных через <xref:System.Windows.Forms.PrintPreviewControl> , <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> свойства, которые определяют число страниц, отображаемых по горизонтали и вертикали в элементе управления. Вы можете получить доступ к <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> свойство как `PrintPreviewDialog1.PrintPreviewControl.Columns` в [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` в [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], или `printPreviewDialog1->PrintPreviewControl->Columns` в [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Общие сведения об элементе управления PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Элементы управления и компоненты диалоговых окон](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
