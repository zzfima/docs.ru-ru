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
ms.locfileid: "33522880"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>Практическое руководство. Перенаправление данных, введенные пользователем в PrintDialog во время выполнения
Хотя можно задать параметры, относящиеся к печати во время разработки, иногда может потребоваться изменить эти параметры во время выполнения, скорее всего, из-за параметров, заданных пользователем. Ввод данных для печати документ с помощью <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument> компонентов.  
  
### <a name="to-change-print-options-programmatically"></a>Чтобы изменить параметры печати программными средствами  
  
1.  Добавить <xref:System.Windows.Forms.PrintDialog> и <xref:System.Drawing.Printing.PrintDocument> форму компонента.  
  
2.  Задать <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство <xref:System.Windows.Forms.PrintDialog> для <xref:System.Drawing.Printing.PrintDocument> добавленного в форму.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  Отображение <xref:System.Windows.Forms.PrintDialog> компонента с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Пользовательские настройки печати, из диалогового окна будут скопированы <xref:System.Drawing.Printing.PrinterSettings> свойство <xref:System.Drawing.Printing.PrintDocument> компонента.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 [Поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
