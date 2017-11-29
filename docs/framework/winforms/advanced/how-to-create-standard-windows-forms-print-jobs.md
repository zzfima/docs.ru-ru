---
title: "Практическое руководство. Создание стандартных задания печати в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2b0ce30f76fe7f8cbdc156c4a8ff5abffafae10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="0d63f-102">Практическое руководство. Создание стандартных задания печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d63f-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="0d63f-103">Основой печати в Windows Forms является <xref:System.Drawing.Printing.PrintDocument> компонента — в частности, <xref:System.Drawing.Printing.PrintDocument.PrintPage> событие.</span><span class="sxs-lookup"><span data-stu-id="0d63f-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="0d63f-104">Путем написания кода для обработки <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий, можно указать печати и способ печати.</span><span class="sxs-lookup"><span data-stu-id="0d63f-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="0d63f-105">Чтобы создать задание печати</span><span class="sxs-lookup"><span data-stu-id="0d63f-105">To create a print job</span></span>  
  
1.  <span data-ttu-id="0d63f-106">Добавить <xref:System.Drawing.Printing.PrintDocument> форму компонента.</span><span class="sxs-lookup"><span data-stu-id="0d63f-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="0d63f-107">Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="0d63f-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="0d63f-108">Необходимо будет кода собственную логику печати.</span><span class="sxs-lookup"><span data-stu-id="0d63f-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="0d63f-109">Кроме того нужно указать материала для печати.</span><span class="sxs-lookup"><span data-stu-id="0d63f-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="0d63f-110">В следующем примере создается образец рисунка в форму красный прямоугольник в <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчика событий в качестве материала для печати.</span><span class="sxs-lookup"><span data-stu-id="0d63f-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="0d63f-111">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="0d63f-111">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="0d63f-112">Можно также написать код для <xref:System.Drawing.Printing.PrintDocument.BeginPrint> и <xref:System.Drawing.Printing.PrintDocument.EndPrint> события, например, целочисленное значение, представляющее общее число страниц для печати, уменьшается на единицу при печати каждой страницы.</span><span class="sxs-lookup"><span data-stu-id="0d63f-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d63f-113">Можно добавить <xref:System.Windows.Forms.PrintDialog> форму для предоставления пользователям простого и эффективного пользовательского интерфейса (UI) компонента.</span><span class="sxs-lookup"><span data-stu-id="0d63f-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="0d63f-114">Установка <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство <xref:System.Windows.Forms.PrintDialog> включает компонент, можно задать свойства, относящиеся к печати документов, вы работаете с в форме.</span><span class="sxs-lookup"><span data-stu-id="0d63f-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="0d63f-115">Дополнительные сведения о <xref:System.Windows.Forms.PrintDialog> компонента, в разделе [компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0d63f-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="0d63f-116">Дополнительные сведения об особенностях Windows Forms см. задания печати, включая способы создания заданий печати программными средствами, <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="0d63f-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d63f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0d63f-117">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="0d63f-118">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d63f-118">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
