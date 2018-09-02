---
title: Практическое руководство. Печать клиентской области формы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- client area [Visual Basic], printing
ms.assetid: c06c9c0e-bc07-48cd-9596-e29a2ff96236
ms.openlocfilehash: b2f13d1ec151a5fd1967b522a601e0e19de04cbb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419288"
---
# <a name="how-to-print-the-client-area-of-a-form-visual-basic"></a><span data-ttu-id="c6139-102">Практическое руководство. Печать клиентской области формы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6139-102">How to: Print the Client Area of a Form (Visual Basic)</span></span>
<span data-ttu-id="c6139-103">Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> позволяет быстро напечатать изображение формы без использования компонента <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="c6139-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="c6139-104">Ниже показано, как напечатать клиентскую область формы без строки заголовка, границ и полос прокрутки.</span><span class="sxs-lookup"><span data-stu-id="c6139-104">The following procedure shows how to print just the client area of a form, without the title bar, borders, and scroll bars.</span></span>  
  
 <span data-ttu-id="c6139-105">Элементы управления PowerPack больше не включены в Visual Studio, но их можно скачать [центра загрузки](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="c6139-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-client-area-of-a-form"></a><span data-ttu-id="c6139-106">Печать клиентской области формы</span><span class="sxs-lookup"><span data-stu-id="c6139-106">To print the client area of a form</span></span>  
  
1.  <span data-ttu-id="c6139-107">В **панели элементов**щелкните вкладку **Visual Basic PowerPacks** , а затем перетащите компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> в форму.</span><span class="sxs-lookup"><span data-stu-id="c6139-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="c6139-108">Компонент <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> будет добавлен в область компонентов.</span><span class="sxs-lookup"><span data-stu-id="c6139-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="c6139-109">В окне **Свойства** присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> значение <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="c6139-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="c6139-110">Добавьте следующий код в соответствующий обработчик событий (например, в обработчик событий `Click` для **Print**`Button`).</span><span class="sxs-lookup"><span data-stu-id="c6139-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.ClientAreaOnly)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c6139-111">В некоторых операционных системах текст или графика, нарисованная с использованием метода <xref:System.Drawing.Graphics> , могут быть напечатаны неправильно.</span><span class="sxs-lookup"><span data-stu-id="c6139-111">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="c6139-112">В этом случае используйте совместимый метод печати: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`.</span><span class="sxs-lookup"><span data-stu-id="c6139-112">In this case, use the compatible printing method: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption CompatibleModeClientAreaOnly).`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6139-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c6139-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="c6139-114">Компонент PrintForm</span><span class="sxs-lookup"><span data-stu-id="c6139-114">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="c6139-115">Практическое руководство. Печать клиентской и неклиентской области формы</span><span class="sxs-lookup"><span data-stu-id="c6139-115">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [<span data-ttu-id="c6139-116">Практическое руководство. Печать прокручиваемой формы</span><span class="sxs-lookup"><span data-stu-id="c6139-116">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
