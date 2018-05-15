---
title: Поддержка печати в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 4ea04d0b6bb8ffa7182d5166ebd66b809adeed34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="39ced-102">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39ced-102">Windows Forms Print Support</span></span>
<span data-ttu-id="39ced-103">Печать в Windows Forms состоит в основном из использования [компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) компонента, чтобы пользователь мог напечатать и [управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) управления [PrintDialog Компонент](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) и [компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) компоненты для обеспечения знакомый графический интерфейс для пользователей, привыкших к операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="39ced-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="39ced-104">Обычно создается новый экземпляр <xref:System.Drawing.Printing.PrintDocument> набор компонентов, свойств, описывающих печатаемое содержимое с помощью <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings> классы и вызовите метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> способ печати документа.</span><span class="sxs-lookup"><span data-stu-id="39ced-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="39ced-105">В ходе работы при печати из приложения Windows <xref:System.Drawing.Printing.PrintDocument> компонент отображает диалоговое окно прерывания печати, которое оповестить пользователей о начале печати и чтобы разрешить задание печати отменяется.</span><span class="sxs-lookup"><span data-stu-id="39ced-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39ced-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="39ced-106">In This Section</span></span>  
 [<span data-ttu-id="39ced-107">Практическое руководство. Создание стандартных заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39ced-107">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="39ced-108">Описание способов использования <xref:System.Drawing.Printing.PrintDocument> компонента для печати в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="39ced-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="39ced-109">Практическое руководство. Захват данных, введенных пользователем в PrintDialog во время выполнения</span><span class="sxs-lookup"><span data-stu-id="39ced-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="39ced-110">Объясняется, как изменить выбранные параметры печати программными средствами с помощью <xref:System.Windows.Forms.PrintDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="39ced-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="39ced-111">Практическое руководство. Выбор принтера, подключенного к компьютеру пользователя, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39ced-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="39ced-112">Описывает изменение принтер для печати с помощью <xref:System.Windows.Forms.PrintDialog> компонента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="39ced-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="39ced-113">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39ced-113">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="39ced-114">Справка по выводу графики на принтер.</span><span class="sxs-lookup"><span data-stu-id="39ced-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="39ced-115">Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39ced-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="39ced-116">Справка по выводу текста на принтер.</span><span class="sxs-lookup"><span data-stu-id="39ced-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="39ced-117">Практическое руководство. Выполнение заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39ced-117">How to: Complete Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="39ced-118">Справка по оповещению пользователей о завершении задания печати.</span><span class="sxs-lookup"><span data-stu-id="39ced-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="39ced-119">Практическое руководство. Печать формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="39ced-119">How to: Print a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 <span data-ttu-id="39ced-120">Показано, как напечатать копию текущей формы.</span><span class="sxs-lookup"><span data-stu-id="39ced-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="39ced-121">Практическое руководство. Печать в Windows Forms с использованием предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="39ced-121">How to: Print in Windows Forms Using Print Preview</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="39ced-122">Показано, как использовать <xref:System.Windows.Forms.PrintPreviewDialog> для печати документа.</span><span class="sxs-lookup"><span data-stu-id="39ced-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="39ced-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="39ced-123">Related Sections</span></span>  
 [<span data-ttu-id="39ced-124">Компонент PrintDocument</span><span class="sxs-lookup"><span data-stu-id="39ced-124">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="39ced-125">Объясняется использование <xref:System.Drawing.Printing.PrintDocument> компонента.</span><span class="sxs-lookup"><span data-stu-id="39ced-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="39ced-126">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="39ced-126">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="39ced-127">Объясняется использование <xref:System.Windows.Forms.PrintDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="39ced-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="39ced-128">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="39ced-128">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="39ced-129">Объясняется использование <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="39ced-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="39ced-130">Компонент PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="39ced-130">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="39ced-131">Объясняется использование <xref:System.Windows.Forms.PageSetupDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="39ced-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="39ced-132">Описываются классы в <xref:System.Drawing.Printing> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="39ced-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
