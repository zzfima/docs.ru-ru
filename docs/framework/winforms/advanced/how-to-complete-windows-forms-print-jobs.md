---
title: "How to: Complete Windows Forms Print Jobs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "print jobs, completing in Windows Forms"
  - "printing [Windows Forms], print jobs"
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# How to: Complete Windows Forms Print Jobs
Часто текстовые процессоры и другие приложения, использующие печать, обеспечивают возможность отображения для пользователей сообщения о завершении задания печати.  Можно предоставить эту функцию в формах Windows Forms, обрабатывая событие <xref:System.Drawing.Printing.PrintDocument.EndPrint> компонента <xref:System.Drawing.Printing.PrintDocument>.  
  
 Для представленной ниже процедуры требуется, чтобы было создано приложение Windows с компонентом <xref:System.Drawing.Printing.PrintDocument>, который является стандартным способом включения печати из приложения Windows.  Дополнительные сведения о печати из Windows Forms с помощью компонента <xref:System.Drawing.Printing.PrintDocument> см. в разделе [How to: Create Standard Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).  
  
### Чтобы завершить задание печати, выполните следующие действия.  
  
1.  Установите свойство <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> компонента <xref:System.Drawing.Printing.PrintDocument>.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.EndPrint>.  
  
     В приведенном ниже примере представлено окно сообщения с уведомлением о завершении печати документа.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
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
  
## См. также  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)