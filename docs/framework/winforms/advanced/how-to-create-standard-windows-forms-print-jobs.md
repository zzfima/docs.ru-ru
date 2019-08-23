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
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938233"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="4195b-102">Практическое руководство. Создание стандартных задания печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4195b-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="4195b-103">Основой печати в Windows Forms является <xref:System.Drawing.Printing.PrintDocument> компонент — точнее <xref:System.Drawing.Printing.PrintDocument.PrintPage> , это событие.</span><span class="sxs-lookup"><span data-stu-id="4195b-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="4195b-104">Написав код для <xref:System.Drawing.Printing.PrintDocument.PrintPage> работы с событием, можно указать, что печатать и как его печатать.</span><span class="sxs-lookup"><span data-stu-id="4195b-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="4195b-105">Создание задания печати</span><span class="sxs-lookup"><span data-stu-id="4195b-105">To create a print job</span></span>  
  
1. <span data-ttu-id="4195b-106"><xref:System.Drawing.Printing.PrintDocument> Добавьте компонент в форму.</span><span class="sxs-lookup"><span data-stu-id="4195b-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="4195b-107">Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="4195b-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="4195b-108">Вам потребуется выполнить код для собственной логики печати.</span><span class="sxs-lookup"><span data-stu-id="4195b-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="4195b-109">Кроме того, необходимо указать материал, который будет напечатан.</span><span class="sxs-lookup"><span data-stu-id="4195b-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="4195b-110">В следующем примере кода образец изображения в фигуре красного прямоугольника создается в <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчике событий для выполнения печати материала.</span><span class="sxs-lookup"><span data-stu-id="4195b-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="4195b-111">(Визуальный C# элемент C++и визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4195b-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="4195b-112">Также может потребоваться написать код для <xref:System.Drawing.Printing.PrintDocument.BeginPrint> событий и <xref:System.Drawing.Printing.PrintDocument.EndPrint> , например, целое число, представляющее общее количество страниц для печати, которое уменьшается при печати каждой страницы.</span><span class="sxs-lookup"><span data-stu-id="4195b-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4195b-113">В форму можно добавить <xref:System.Windows.Forms.PrintDialog> компонент, чтобы предоставить пользователям чистый и эффективный пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4195b-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="4195b-114"><xref:System.Windows.Forms.PrintDialog.Document%2A> Задание свойства <xref:System.Windows.Forms.PrintDialog> компонента позволяет задавать свойства, связанные с печатаемым документом, с которым вы работаете в форме.</span><span class="sxs-lookup"><span data-stu-id="4195b-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="4195b-115">Дополнительные сведения о компоненте <xref:System.Windows.Forms.PrintDialog> см. в разделе [компонент PrintDialog](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4195b-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="4195b-116">Дополнительные сведения о Windows Forms заданий печати, в том числе о создании задания печати программным способом, см. в разделе <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4195b-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4195b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4195b-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="4195b-118">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4195b-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
