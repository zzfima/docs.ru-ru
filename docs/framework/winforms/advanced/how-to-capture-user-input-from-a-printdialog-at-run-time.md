---
title: Практическое руководство. Перенаправление данных, введенных пользователем в PrintDialog во время выполнения
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
ms.openlocfilehash: 2aaf988f362baf9cd80eb16e4a08f7f65a5077bb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311426"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="13ba0-102">Практическое руководство. Перенаправление данных, введенных пользователем в PrintDialog во время выполнения</span><span class="sxs-lookup"><span data-stu-id="13ba0-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="13ba0-103">Хотя можно задать параметры, относящиеся к печати во время разработки, иногда требуется изменить эти параметры во время выполнения, скорее всего, из-за выборов, сделанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="13ba0-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="13ba0-104">Ввод данных для печати документа с помощью <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument> компонентов.</span><span class="sxs-lookup"><span data-stu-id="13ba0-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="13ba0-105">Чтобы изменить параметры печати программными средствами</span><span class="sxs-lookup"><span data-stu-id="13ba0-105">To change print options programmatically</span></span>  
  
1. <span data-ttu-id="13ba0-106">Добавить <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument> форму компонента.</span><span class="sxs-lookup"><span data-stu-id="13ba0-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="13ba0-107">Задайте <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство <xref:System.Windows.Forms.PrintDialog> для <xref:System.Drawing.Printing.PrintDocument> добавления в форму.</span><span class="sxs-lookup"><span data-stu-id="13ba0-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3. <span data-ttu-id="13ba0-108">Отображение <xref:System.Windows.Forms.PrintDialog> компонент с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="13ba0-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4. <span data-ttu-id="13ba0-109">Пользователя вариантами печати из диалогового окна будут скопированы в <xref:System.Drawing.Printing.PrinterSettings> свойство <xref:System.Drawing.Printing.PrintDocument> компонента.</span><span class="sxs-lookup"><span data-stu-id="13ba0-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ba0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="13ba0-110">See also</span></span>

- [<span data-ttu-id="13ba0-111">Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13ba0-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="13ba0-112">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="13ba0-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
