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
# <a name="how-to-complete-windows-forms-print-jobs"></a>Практическое руководство. Выполнение заданий печати в Windows Forms
Часто текстовые процессоры и другие приложения, связанные с печатью, предоставляют возможность отображения сообщения пользователям о завершении задания печати. Эту функциональность можно предоставить в формах Windows, обсуив <xref:System.Drawing.Printing.PrintDocument.EndPrint> событие компонента. <xref:System.Drawing.Printing.PrintDocument>  
  
 Следующая процедура требует, чтобы вы создали приложение <xref:System.Drawing.Printing.PrintDocument> на базе Windows с компонентом на нем, который является стандартным способом включения печати из приложения на базе Windows. Для получения дополнительной информации о <xref:System.Drawing.Printing.PrintDocument> печати из форм Windows с помощью компонента, см. [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md)  
  
### <a name="to-complete-a-print-job"></a>Для завершения работы по печати  
  
1. Установите <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> свойство <xref:System.Drawing.Printing.PrintDocument> компонента.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.EndPrint> .  
  
     В следующем примере кода отображается окно сообщений, указывающая на то, что документ закончил печать.  
  
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
  
     (Визуальный C и Визуальный C ) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](windows-forms-print-support.md)
