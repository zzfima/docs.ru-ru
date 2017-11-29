---
title: "Практическое руководство. Печать формы с помощью компонента PrintForm (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5edad4f04b98dcf0dfa328f111db5dcb423036e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a><span data-ttu-id="351a0-102">Практическое руководство. Печать формы с помощью компонента PrintForm (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="351a0-102">How to: Print a Form by Using the PrintForm Component (Visual Basic)</span></span>
<span data-ttu-id="351a0-103">Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> позволяет быстро напечатать изображение формы точно, как на экране, без использования компонента <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="351a0-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="351a0-104">Следующие процедуры показывают, как вывести форму для печати на принтер, в окно предварительного просмотра печати и в EPS-файл.</span><span class="sxs-lookup"><span data-stu-id="351a0-104">The following procedures show how to print a form to a printer, to a print preview window, and to an Encapsulated PostScript file.</span></span>  
  
 <span data-ttu-id="351a0-105">Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать в [Центре загрузки](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="351a0-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-a-form-to-the-default-printer"></a><span data-ttu-id="351a0-106">Печать формы на принтере по умолчанию</span><span class="sxs-lookup"><span data-stu-id="351a0-106">To print a form to the default printer</span></span>  
  
1.  <span data-ttu-id="351a0-107">В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.</span><span class="sxs-lookup"><span data-stu-id="351a0-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="351a0-108">Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.</span><span class="sxs-lookup"><span data-stu-id="351a0-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="351a0-109">В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="351a0-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="351a0-110">Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).</span><span class="sxs-lookup"><span data-stu-id="351a0-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a><span data-ttu-id="351a0-111">Отображение формы в окне предварительного просмотра</span><span class="sxs-lookup"><span data-stu-id="351a0-111">To display a form in a print preview window</span></span>  
  
1.  <span data-ttu-id="351a0-112">В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.</span><span class="sxs-lookup"><span data-stu-id="351a0-112">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="351a0-113">Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.</span><span class="sxs-lookup"><span data-stu-id="351a0-113">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="351a0-114">В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.</span><span class="sxs-lookup"><span data-stu-id="351a0-114">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.</span></span>  
  
3.  <span data-ttu-id="351a0-115">Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).</span><span class="sxs-lookup"><span data-stu-id="351a0-115">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a><span data-ttu-id="351a0-116">Печать формы в файл</span><span class="sxs-lookup"><span data-stu-id="351a0-116">To print a form to a file</span></span>  
  
1.  <span data-ttu-id="351a0-117">В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.</span><span class="sxs-lookup"><span data-stu-id="351a0-117">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="351a0-118">Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.</span><span class="sxs-lookup"><span data-stu-id="351a0-118">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="351a0-119">В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToFile>.</span><span class="sxs-lookup"><span data-stu-id="351a0-119">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToFile>.</span></span>  
  
3.  <span data-ttu-id="351a0-120">При необходимости выберите <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> и введите полный путь и имя целевого файла.</span><span class="sxs-lookup"><span data-stu-id="351a0-120">Optionally, select the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> property and type the full path and file name for the destination file.</span></span>  
  
     <span data-ttu-id="351a0-121">Если пропустить этот шаг, пользователю будет предложено ввести имя файла во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="351a0-121">If you skip this step, the user will be prompted for a file name at run time.</span></span>  
  
4.  <span data-ttu-id="351a0-122">Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).</span><span class="sxs-lookup"><span data-stu-id="351a0-122">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="351a0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="351a0-123">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>  
 [<span data-ttu-id="351a0-124">Практическое руководство. Печать клиентской области формы</span><span class="sxs-lookup"><span data-stu-id="351a0-124">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [<span data-ttu-id="351a0-125">Практическое руководство. Печать клиентской и неклиентской области формы</span><span class="sxs-lookup"><span data-stu-id="351a0-125">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [<span data-ttu-id="351a0-126">Практическое руководство. Печать прокручиваемой формы</span><span class="sxs-lookup"><span data-stu-id="351a0-126">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)  
 [<span data-ttu-id="351a0-127">Компонент PrintForm</span><span class="sxs-lookup"><span data-stu-id="351a0-127">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
