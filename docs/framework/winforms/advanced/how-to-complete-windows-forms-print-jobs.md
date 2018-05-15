---
title: Практическое руководство. Выполнение заданий печати в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 74a8e3721df72415437dd0c39b3298d67c19990b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="4c668-102">Практическое руководство. Выполнение заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c668-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="4c668-103">Часто процессоры и другие приложения, использующие печать предоставляют параметр, чтобы отобразить сообщение о завершении задания печати пользователям.</span><span class="sxs-lookup"><span data-stu-id="4c668-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="4c668-104">Можно предоставить эти функции в Windows Forms путем обработки <xref:System.Drawing.Printing.PrintDocument.EndPrint> событие <xref:System.Drawing.Printing.PrintDocument> компонента.</span><span class="sxs-lookup"><span data-stu-id="4c668-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="4c668-105">Следующая процедура требует создания приложения Windows с <xref:System.Drawing.Printing.PrintDocument> компонентом, который является стандартным способом включения печати из приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="4c668-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="4c668-106">Дополнительные сведения о печати в Windows Forms с помощью <xref:System.Drawing.Printing.PrintDocument> компонента, в разделе [как: создание стандартных заданий Windows Forms печати](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4c668-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="4c668-107">Чтобы завершить задание печати</span><span class="sxs-lookup"><span data-stu-id="4c668-107">To complete a print job</span></span>  
  
1.  <span data-ttu-id="4c668-108">Задать <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> свойство <xref:System.Drawing.Printing.PrintDocument> компонента.</span><span class="sxs-lookup"><span data-stu-id="4c668-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  <span data-ttu-id="4c668-109">Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.EndPrint>.</span><span class="sxs-lookup"><span data-stu-id="4c668-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="4c668-110">В следующем примере кода выводится сообщение отображается, позволяющее определить, завершена печать документа.</span><span class="sxs-lookup"><span data-stu-id="4c668-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     <span data-ttu-id="4c668-111">(Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4c668-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4c668-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4c668-112">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="4c668-113">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c668-113">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
