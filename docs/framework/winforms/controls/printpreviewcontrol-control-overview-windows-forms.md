---
title: Общие сведения об элементе управления PrintPreviewControl (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 330172a2ccf285cb75432572a558363e71de7ab1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Общие сведения об элементе управления PrintPreviewControl (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> используется для отображения [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) как будет выглядеть при печати. У элемента управления <xref:System.Windows.Forms.PrintPreviewControl> нет кнопок и других элементов пользовательского интерфейса, поэтому обычно он используется только в том случае, если нужно реализовать собственный интерфейс предварительного просмотра. Стандартный пользовательский интерфейс, используйте <xref:System.Windows.Forms.PrintPreviewDialog> управления; см. раздел [Обзор элемента управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) Общие сведения.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевое свойство элемента управления <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, который задает документ для предварительного просмотра. Документ должен быть <xref:System.Drawing.Printing.PrintDocument> объекта. Общие сведения о создании документов для печати см. в разделе [Общие сведения о компоненте PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) и [поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md). <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> И <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> свойства определяют число страниц, отображаемых по горизонтали и вертикали в элементе управления. Сглаживание можно увеличить гладкую текст, но оно может привести к замедлению отображения; Чтобы использовать его, установите <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> свойства `true`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [Общие сведения об элементе управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [Элемент управления PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [Элементы управления и компоненты диалоговых окон](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
