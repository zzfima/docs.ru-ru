---
title: "Общие сведения об элементе управления PrintPreviewControl (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d50e772cf870d47314a25347f4909367062ffb94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="50dd4-102">Общие сведения об элементе управления PrintPreviewControl (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="50dd4-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="50dd4-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> используется для отображения [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) как будет выглядеть при печати.</span><span class="sxs-lookup"><span data-stu-id="50dd4-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="50dd4-104">У элемента управления <xref:System.Windows.Forms.PrintPreviewControl> нет кнопок и других элементов пользовательского интерфейса, поэтому обычно он используется только в том случае, если нужно реализовать собственный интерфейс предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="50dd4-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="50dd4-105">Стандартный пользовательский интерфейс, используйте <xref:System.Windows.Forms.PrintPreviewDialog> управления; см. раздел [Обзор элемента управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) Общие сведения.</span><span class="sxs-lookup"><span data-stu-id="50dd4-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="50dd4-106">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="50dd4-106">Key Properties</span></span>  
 <span data-ttu-id="50dd4-107">Ключевое свойство элемента управления <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, который задает документ для предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="50dd4-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="50dd4-108">Документ должен быть <xref:System.Drawing.Printing.PrintDocument> объекта.</span><span class="sxs-lookup"><span data-stu-id="50dd4-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="50dd4-109">Общие сведения о создании документов для печати см. в разделе [Общие сведения о компоненте PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) и [поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span><span class="sxs-lookup"><span data-stu-id="50dd4-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="50dd4-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> И <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> свойства определяют число страниц, отображаемых по горизонтали и вертикали в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="50dd4-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="50dd4-111">Сглаживание можно увеличить гладкую текст, но оно может привести к замедлению отображения; Чтобы использовать его, установите <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="50dd4-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50dd4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="50dd4-112">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [<span data-ttu-id="50dd4-113">Общие сведения об элементе управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="50dd4-113">PrintPreviewDialog Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [<span data-ttu-id="50dd4-114">Элемент управления PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="50dd4-114">PrintPreviewControl Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [<span data-ttu-id="50dd4-115">Элементы управления и компоненты диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="50dd4-115">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
