---
title: Практическое руководство. Полный Windows Forms заданий печати
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 1ae20e4fdc3a4fc3de8c462c355bcc700eddf22e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711737"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Практическое руководство. Полный Windows Forms заданий печати
Часто текстовые редакторы и другие приложения, использующие печать предоставит возможность отобразить сообщение для пользователей, что задание на печать завершена. Можно предоставить эти функции в формах Windows путем обработки <xref:System.Drawing.Printing.PrintDocument.EndPrint> событие <xref:System.Drawing.Printing.PrintDocument> компонента.  
  
 Следующая процедура требует, что вы создали приложения на основе Windows с помощью <xref:System.Drawing.Printing.PrintDocument> компонентом, который является стандартным способом включения печати из приложения на основе Windows. Дополнительные сведения о печати из Windows Forms с помощью <xref:System.Drawing.Printing.PrintDocument> компонента, см. в разделе [как: Создание заданий печати стандартный Windows Forms](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Чтобы выполнить задание печати  
  
1.  Задайте <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> свойство <xref:System.Drawing.Printing.PrintDocument> компонента.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.EndPrint> .  
  
     В следующем примере кода отображается окно сообщения, указывающее, что завершении печати документа.  
  
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
  
     (Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](windows-forms-print-support.md)
