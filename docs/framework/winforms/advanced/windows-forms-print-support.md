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
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011857"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="a87e6-102">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a87e6-102">Windows Forms Print Support</span></span>
<span data-ttu-id="a87e6-103">Печать в Windows Forms состоит главным образом с помощью [компонент PrintDocument](../controls/printdocument-component-windows-forms.md) компонента, чтобы пользователь мог напечатать и [управления PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) элемента управления, [PrintDialog Компонент](../controls/printdialog-component-windows-forms.md) и [компонент PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) компонентов для предоставления знакомый графический интерфейс для пользователей, привыкших к операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="a87e6-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="a87e6-104">Обычно создается новый экземпляр класса <xref:System.Drawing.Printing.PrintDocument> компонента, значение свойства, описывающие содержимое для печати с помощью <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings> классы и вызовите метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> способ печати документа.</span><span class="sxs-lookup"><span data-stu-id="a87e6-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="a87e6-105">В ходе печати из приложения на базе Windows <xref:System.Drawing.Printing.PrintDocument> компонента будет отображаться диалоговое окно прерывания печати для предупреждения пользователей к тому факту, печати и чтобы разрешить задание печати отменяется.</span><span class="sxs-lookup"><span data-stu-id="a87e6-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a87e6-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a87e6-106">In This Section</span></span>  
 [<span data-ttu-id="a87e6-107">Практическое руководство. Создание заданий печати стандартный Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a87e6-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="a87e6-108">Содержит сведения об использовании <xref:System.Drawing.Printing.PrintDocument> компонента для печати в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a87e6-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="a87e6-109">Практическое руководство. Захват данных пользователем в PrintDialog во время выполнения</span><span class="sxs-lookup"><span data-stu-id="a87e6-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="a87e6-110">Объясняется, как изменить выбранные параметры печати программно с помощью <xref:System.Windows.Forms.PrintDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a87e6-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="a87e6-111">Практическое руководство. Выбор принтера, подключенного к компьютеру пользователя в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a87e6-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="a87e6-112">Описывает изменение принтер с помощью <xref:System.Windows.Forms.PrintDialog> компонента во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a87e6-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="a87e6-113">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a87e6-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="a87e6-114">Описание вывода графики на принтер.</span><span class="sxs-lookup"><span data-stu-id="a87e6-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="a87e6-115">Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a87e6-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="a87e6-116">Описывается вывод текста на принтер.</span><span class="sxs-lookup"><span data-stu-id="a87e6-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="a87e6-117">Практическое руководство. Полный Windows Forms заданий печати</span><span class="sxs-lookup"><span data-stu-id="a87e6-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="a87e6-118">Описание для оповещения пользователей о завершении задания печати.</span><span class="sxs-lookup"><span data-stu-id="a87e6-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="a87e6-119">Практическое руководство. Печать формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a87e6-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="a87e6-120">Показано, как распечатать копию текущей формы.</span><span class="sxs-lookup"><span data-stu-id="a87e6-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="a87e6-121">Практическое руководство. Печать в Windows Forms с использованием предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="a87e6-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="a87e6-122">Показано, как использовать <xref:System.Windows.Forms.PrintPreviewDialog> для печати документа.</span><span class="sxs-lookup"><span data-stu-id="a87e6-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a87e6-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a87e6-123">Related Sections</span></span>  
 [<span data-ttu-id="a87e6-124">Компонент PrintDocument</span><span class="sxs-lookup"><span data-stu-id="a87e6-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="a87e6-125">Описываются сценарии использования <xref:System.Drawing.Printing.PrintDocument> компонента.</span><span class="sxs-lookup"><span data-stu-id="a87e6-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="a87e6-126">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a87e6-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="a87e6-127">Описываются сценарии использования <xref:System.Windows.Forms.PrintDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a87e6-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="a87e6-128">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="a87e6-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="a87e6-129">Описываются сценарии использования <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a87e6-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="a87e6-130">Компонент PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="a87e6-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="a87e6-131">Описываются сценарии использования <xref:System.Windows.Forms.PageSetupDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a87e6-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="a87e6-132">Содержит описание классов <xref:System.Drawing.Printing> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a87e6-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
