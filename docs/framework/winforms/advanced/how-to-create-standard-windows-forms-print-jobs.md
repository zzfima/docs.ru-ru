---
title: Создание стандартных рабочих мест для печати
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
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182570"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="e2145-102">Практическое руководство. Создание стандартных задания печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e2145-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="e2145-103">Основой печати в формах <xref:System.Drawing.Printing.PrintDocument> Windows является компонент, в частности, <xref:System.Drawing.Printing.PrintDocument.PrintPage> событие.</span><span class="sxs-lookup"><span data-stu-id="e2145-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="e2145-104">Написав код для <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработки события, можно указать, что печатать и как его распечатать.</span><span class="sxs-lookup"><span data-stu-id="e2145-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="e2145-105">Для создания задания печати</span><span class="sxs-lookup"><span data-stu-id="e2145-105">To create a print job</span></span>  
  
1. <span data-ttu-id="e2145-106">Добавьте <xref:System.Drawing.Printing.PrintDocument> компонент в форму.</span><span class="sxs-lookup"><span data-stu-id="e2145-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="e2145-107">Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="e2145-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="e2145-108">Вам придется кодировать свою собственную логику печати.</span><span class="sxs-lookup"><span data-stu-id="e2145-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="e2145-109">Кроме того, вы должны будете указать материал, который будет напечатан.</span><span class="sxs-lookup"><span data-stu-id="e2145-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="e2145-110">В следующем примере кода образец изображения в форме красного прямоугольника создается в обработчике <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий, чтобы выступать в качестве материала, который будет напечатан.</span><span class="sxs-lookup"><span data-stu-id="e2145-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="e2145-111">(Визуальный C и Визуальный C ) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="e2145-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="e2145-112">Вы также можете написать <xref:System.Drawing.Printing.PrintDocument.BeginPrint> код <xref:System.Drawing.Printing.PrintDocument.EndPrint> для событий и событий, возможно, включая целый ряд, представляющий общее количество страниц для печати, которые decremented как каждая страница печатает.</span><span class="sxs-lookup"><span data-stu-id="e2145-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e2145-113">Вы можете <xref:System.Windows.Forms.PrintDialog> добавить компонент в форму, чтобы обеспечить пользователям чистый и эффективный пользовательский интерфейс (Пользовательского интерфейса).</span><span class="sxs-lookup"><span data-stu-id="e2145-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="e2145-114">Установка <xref:System.Windows.Forms.PrintDialog.Document%2A> свойства <xref:System.Windows.Forms.PrintDialog> компонента позволяет устанавливать свойства, связанные с печатным документом, с которым вы работаете, на вашей форме.</span><span class="sxs-lookup"><span data-stu-id="e2145-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="e2145-115">Для получения дополнительной <xref:System.Windows.Forms.PrintDialog> информации о компоненте, см [PrintDialog Компонент](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e2145-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="e2145-116">Для получения дополнительной информации о специфике Windows Формы печати рабочих мест, <xref:System.Drawing.Printing.PrintPageEventArgs>в том числе, как создать работу печати программно, см.</span><span class="sxs-lookup"><span data-stu-id="e2145-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2145-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2145-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="e2145-118">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e2145-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
