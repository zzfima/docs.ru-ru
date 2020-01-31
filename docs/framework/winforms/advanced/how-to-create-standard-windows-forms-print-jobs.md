---
title: Создание стандартных заданий печати
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
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741517"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="444a9-102">Практическое руководство. Создание стандартных задания печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="444a9-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="444a9-103">Основой печати в Windows Forms является компонент <xref:System.Drawing.Printing.PrintDocument> — точнее, <xref:System.Drawing.Printing.PrintDocument.PrintPage> событие.</span><span class="sxs-lookup"><span data-stu-id="444a9-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="444a9-104">Написав код для работы с событием <xref:System.Drawing.Printing.PrintDocument.PrintPage>, можно указать, что печатать и как печатать.</span><span class="sxs-lookup"><span data-stu-id="444a9-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="444a9-105">Создание задания печати</span><span class="sxs-lookup"><span data-stu-id="444a9-105">To create a print job</span></span>  
  
1. <span data-ttu-id="444a9-106">Добавьте в форму компонент <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="444a9-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="444a9-107">Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="444a9-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="444a9-108">Вам потребуется выполнить код для собственной логики печати.</span><span class="sxs-lookup"><span data-stu-id="444a9-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="444a9-109">Кроме того, необходимо указать материал, который будет напечатан.</span><span class="sxs-lookup"><span data-stu-id="444a9-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="444a9-110">В следующем примере кода образец изображения в фигуре красного прямоугольника создается в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage>, чтобы он выводился как материал для печати.</span><span class="sxs-lookup"><span data-stu-id="444a9-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="444a9-111">(Визуальный C# элемент C++и визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="444a9-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="444a9-112">Также может потребоваться написать код для событий <xref:System.Drawing.Printing.PrintDocument.BeginPrint> и <xref:System.Drawing.Printing.PrintDocument.EndPrint>, возможно, в том числе целого числа, представляющего общее число страниц для печати, которое уменьшается при печати каждой страницы.</span><span class="sxs-lookup"><span data-stu-id="444a9-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="444a9-113">Вы можете добавить в форму компонент <xref:System.Windows.Forms.PrintDialog>, чтобы предоставить пользователям чистый и эффективный пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="444a9-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="444a9-114">Установка свойства <xref:System.Windows.Forms.PrintDialog.Document%2A> компонента <xref:System.Windows.Forms.PrintDialog> позволяет задавать свойства, связанные с печатаемым документом, с которым ведется работа в форме.</span><span class="sxs-lookup"><span data-stu-id="444a9-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="444a9-115">Дополнительные сведения о компоненте <xref:System.Windows.Forms.PrintDialog> см. в разделе [компонент PrintDialog](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="444a9-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="444a9-116">Дополнительные сведения о Windows Forms заданий печати, в том числе о создании задания печати программным способом, см. в разделе <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="444a9-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="444a9-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="444a9-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="444a9-118">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="444a9-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
