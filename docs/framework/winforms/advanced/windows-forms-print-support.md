---
title: Поддержка печати
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732491"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="bdfdb-102">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdfdb-102">Windows Forms Print Support</span></span>
<span data-ttu-id="bdfdb-103">Печать в Windows Forms состоит в основном с использованием компонента [PrintDocument](../controls/printdocument-component-windows-forms.md) , который позволяет пользователю печатать, и компоненты элемента управления [PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) , [компонента PrintDialog](../controls/printdialog-component-windows-forms.md) и [компонента PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) , чтобы обеспечить знакомый графический интерфейс для пользователей, привыкших к операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="bdfdb-104">Как правило, создается новый экземпляр компонента <xref:System.Drawing.Printing.PrintDocument>, устанавливаются свойства, описывающие, что печатать с помощью классов <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings>, и вызывается метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> для фактической печати документа.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="bdfdb-105">Во время печати из приложения Windows компонент <xref:System.Drawing.Printing.PrintDocument> покажет диалоговое окно "Прервать печать", чтобы предупредить пользователей о том, что происходит печать, и разрешить отмену задания печати.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bdfdb-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bdfdb-106">In This Section</span></span>  
 [<span data-ttu-id="bdfdb-107">Практическое руководство. Создание стандартных заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdfdb-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="bdfdb-108">Объясняется, как использовать компонент <xref:System.Drawing.Printing.PrintDocument> для печати из формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="bdfdb-109">Практическое руководство. Захват данных, введенных пользователем в PrintDialog во время выполнения</span><span class="sxs-lookup"><span data-stu-id="bdfdb-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="bdfdb-110">Объясняется, как программным способом изменить выбранные параметры печати с помощью компонента <xref:System.Windows.Forms.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="bdfdb-111">Практическое руководство. Выбор принтера, подключенного к компьютеру пользователя, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdfdb-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="bdfdb-112">Описывает изменение принтера для печати с использованием компонента <xref:System.Windows.Forms.PrintDialog> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="bdfdb-113">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdfdb-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="bdfdb-114">Описывает отправку графики на принтер.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="bdfdb-115">Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdfdb-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="bdfdb-116">Описывает отправку текста на принтер.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="bdfdb-117">Практическое руководство. Выполнение заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdfdb-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="bdfdb-118">Объясняет, как предупредить пользователей о завершении задания печати.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="bdfdb-119">Практическое руководство. Печать формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdfdb-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="bdfdb-120">Показывает, как распечатать копию текущей формы.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="bdfdb-121">Практическое руководство. Печать в Windows Forms с использованием предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="bdfdb-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="bdfdb-122">Показывает, как использовать <xref:System.Windows.Forms.PrintPreviewDialog> для печати документа.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bdfdb-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="bdfdb-123">Related Sections</span></span>  
 [<span data-ttu-id="bdfdb-124">Компонент PrintDocument</span><span class="sxs-lookup"><span data-stu-id="bdfdb-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="bdfdb-125">Объясняет использование компонента <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="bdfdb-126">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="bdfdb-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="bdfdb-127">Объясняет использование компонента <xref:System.Windows.Forms.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="bdfdb-128">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="bdfdb-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="bdfdb-129">Объясняет использование элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="bdfdb-130">PageSetupDialog Component</span><span class="sxs-lookup"><span data-stu-id="bdfdb-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="bdfdb-131">Объясняет использование компонента <xref:System.Windows.Forms.PageSetupDialog>.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="bdfdb-132">Описывает классы в пространстве имен <xref:System.Drawing.Printing>.</span><span class="sxs-lookup"><span data-stu-id="bdfdb-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
