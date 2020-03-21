---
title: Полная печать вакансий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182602"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="8beb6-102">Практическое руководство. Выполнение заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8beb6-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="8beb6-103">Часто текстовые процессоры и другие приложения, связанные с печатью, предоставляют возможность отображения сообщения пользователям о завершении задания печати.</span><span class="sxs-lookup"><span data-stu-id="8beb6-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="8beb6-104">Эту функциональность можно предоставить в формах Windows, обсуив <xref:System.Drawing.Printing.PrintDocument.EndPrint> событие компонента. <xref:System.Drawing.Printing.PrintDocument></span><span class="sxs-lookup"><span data-stu-id="8beb6-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="8beb6-105">Следующая процедура требует, чтобы вы создали приложение <xref:System.Drawing.Printing.PrintDocument> на базе Windows с компонентом на нем, который является стандартным способом включения печати из приложения на базе Windows.</span><span class="sxs-lookup"><span data-stu-id="8beb6-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="8beb6-106">Для получения дополнительной информации о <xref:System.Drawing.Printing.PrintDocument> печати из форм Windows с помощью компонента, см. [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="8beb6-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="8beb6-107">Для завершения работы по печати</span><span class="sxs-lookup"><span data-stu-id="8beb6-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="8beb6-108">Установите <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> свойство <xref:System.Drawing.Printing.PrintDocument> компонента.</span><span class="sxs-lookup"><span data-stu-id="8beb6-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="8beb6-109">Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.EndPrint> .</span><span class="sxs-lookup"><span data-stu-id="8beb6-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="8beb6-110">В следующем примере кода отображается окно сообщений, указывающая на то, что документ закончил печать.</span><span class="sxs-lookup"><span data-stu-id="8beb6-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
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
  
     <span data-ttu-id="8beb6-111">(Визуальный C и Визуальный C ) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="8beb6-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8beb6-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8beb6-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="8beb6-113">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8beb6-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
