---
title: Общие сведения об элементе управления PrintPreviewControl
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741434"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Общие сведения об элементе управления PrintPreviewControl (Windows Forms)
<xref:System.Windows.Forms.PrintPreviewControl> Windows Forms используется для отображения [PrintDocument](printdocument-component-windows-forms.md) , как он будет выглядеть при печати. У элемента управления <xref:System.Windows.Forms.PrintPreviewControl> нет кнопок и других элементов пользовательского интерфейса, поэтому обычно он используется только в том случае, если нужно реализовать собственный интерфейс предварительного просмотра. Если нужен стандартный пользовательский интерфейс, используйте элемент управления <xref:System.Windows.Forms.PrintPreviewDialog>; Общие сведения см. в разделе [Общие сведения об элементе управления PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md) .  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевым свойством элемента управления является <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, которое задает предварительный просмотр документа. Документ должен быть объектом <xref:System.Drawing.Printing.PrintDocument>. Общие сведения о создании документов для печати см. в разделе [Общие сведения о компоненте PrintDocument](printdocument-component-overview-windows-forms.md) и [Windows Forms поддержка печати](../advanced/windows-forms-print-support.md). Свойства <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> и <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> определяют количество страниц, отображаемых на элементе управления по горизонтали и вертикали. Сглаживание может сделать текст более плавным, но он также может замедлить отображение. чтобы использовать его, присвойте свойству <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> значение `true`.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.PrintPreviewControl>
- [Общие сведения об элементе управления PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md)
- [Элемент управления PrintPreviewControl](printpreviewcontrol-control-windows-forms.md)
- [Элементы управления и компоненты диалоговых окон](dialog-box-controls-and-components-windows-forms.md)
