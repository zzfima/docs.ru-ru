---
title: Практическое руководство. Перенаправление данных, введенные пользователем в PrintDialog во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 554c3c43f8ac4d41ddfc8651472d0b7fbed960bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="56c6e-102">Практическое руководство. Перенаправление данных, введенные пользователем в PrintDialog во время выполнения</span><span class="sxs-lookup"><span data-stu-id="56c6e-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="56c6e-103">Хотя можно задать параметры, относящиеся к печати во время разработки, иногда может потребоваться изменить эти параметры во время выполнения, скорее всего, из-за параметров, заданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="56c6e-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="56c6e-104">Ввод данных для печати документ с помощью <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument> компонентов.</span><span class="sxs-lookup"><span data-stu-id="56c6e-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="56c6e-105">Чтобы изменить параметры печати программными средствами</span><span class="sxs-lookup"><span data-stu-id="56c6e-105">To change print options programmatically</span></span>  
  
1.  <span data-ttu-id="56c6e-106">Добавить <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument> форму компонента.</span><span class="sxs-lookup"><span data-stu-id="56c6e-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="56c6e-107">Задать <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство <xref:System.Windows.Forms.PrintDialog> для <xref:System.Drawing.Printing.PrintDocument> добавленного в форму.</span><span class="sxs-lookup"><span data-stu-id="56c6e-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  <span data-ttu-id="56c6e-108">Отображение <xref:System.Windows.Forms.PrintDialog> компонента с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="56c6e-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  <span data-ttu-id="56c6e-109">Пользовательские настройки печати, из диалогового окна будут скопированы <xref:System.Drawing.Printing.PrinterSettings> свойство <xref:System.Drawing.Printing.PrintDocument> компонента.</span><span class="sxs-lookup"><span data-stu-id="56c6e-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c6e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="56c6e-110">See Also</span></span>  
 [<span data-ttu-id="56c6e-111">Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56c6e-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 [<span data-ttu-id="56c6e-112">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56c6e-112">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
