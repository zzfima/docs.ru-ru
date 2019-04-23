---
title: Практическое руководство. Создание стандартных задания печати в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: 816da93218e20f73f16c14769ed1a549dd3d8eb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335411"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="36c92-102">Практическое руководство. Создание стандартных задания печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36c92-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="36c92-103">Печать в Windows Forms лежит <xref:System.Drawing.Printing.PrintDocument> компонент — в частности, <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий.</span><span class="sxs-lookup"><span data-stu-id="36c92-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="36c92-104">Путем написания кода для обработки <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий, можно указать, что нужно вывести и способ печати.</span><span class="sxs-lookup"><span data-stu-id="36c92-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="36c92-105">Чтобы создать задание на печать</span><span class="sxs-lookup"><span data-stu-id="36c92-105">To create a print job</span></span>  
  
1. <span data-ttu-id="36c92-106">Добавление <xref:System.Drawing.Printing.PrintDocument> форму компонента.</span><span class="sxs-lookup"><span data-stu-id="36c92-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="36c92-107">Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="36c92-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="36c92-108">Как будет нужно код логики печати.</span><span class="sxs-lookup"><span data-stu-id="36c92-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="36c92-109">Кроме того необходимо указать материала для печати.</span><span class="sxs-lookup"><span data-stu-id="36c92-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="36c92-110">В следующем примере кода создается образец рисунка в форму красного прямоугольника в <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчик событий в качестве материала для печати.</span><span class="sxs-lookup"><span data-stu-id="36c92-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="36c92-111">(Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="36c92-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="36c92-112">Можно также написать код для <xref:System.Drawing.Printing.PrintDocument.BeginPrint> и <xref:System.Drawing.Printing.PrintDocument.EndPrint> события, например, целое число, представляющее общее число страниц для печати, уменьшается на единицу при печати каждой страницы.</span><span class="sxs-lookup"><span data-stu-id="36c92-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="36c92-113">Вы можете добавить <xref:System.Windows.Forms.PrintDialog> форму для обеспечения простого и эффективного пользовательского интерфейса (UI) для пользователей компонента.</span><span class="sxs-lookup"><span data-stu-id="36c92-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="36c92-114">Установка <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство <xref:System.Windows.Forms.PrintDialog> включает компонент, можно задать свойства, относящиеся к печати документа при работе с в форму.</span><span class="sxs-lookup"><span data-stu-id="36c92-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="36c92-115">Дополнительные сведения о <xref:System.Windows.Forms.PrintDialog> компонента, см. в разделе [компонент PrintDialog](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="36c92-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="36c92-116">Дополнительные сведения об особенностях Windows Forms задания печати, включая создание задание на печать программным способом, см. в разделе <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="36c92-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c92-117">См. также</span><span class="sxs-lookup"><span data-stu-id="36c92-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="36c92-118">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36c92-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
