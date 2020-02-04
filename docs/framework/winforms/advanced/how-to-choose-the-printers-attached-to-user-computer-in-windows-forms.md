---
title: Как выбрать принтеры, подключенные к компьютеру пользователя
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 7fc2427468540ac0a1480f6140cbb34c3a0f1ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746513"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a>Практическое руководство. Выбор принтера, подключенного к компьютеру пользователя, в Windows Forms
Часто для печати пользователям требуется выбрать принтер, отличный от используемого по умолчанию. С помощью компонента <xref:System.Windows.Forms.PrintDialog> можно разрешить пользователям выбрать один из установленных принтеров. Компонент <xref:System.Windows.Forms.PrintDialog> позволяет зафиксировать <xref:System.Windows.Forms.DialogResult> компонента <xref:System.Windows.Forms.PrintDialog> и использовать его для выбора принтера.  
  
 В следующей процедуре выбирается текстовый файл для печати на принтер по умолчанию. После этого создается экземпляр класса <xref:System.Windows.Forms.PrintDialog> .  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>Выбор принтера и печать файла  
  
1. Выберите принтер для использования с компонентом <xref:System.Windows.Forms.PrintDialog>.  
  
     В следующем примере кода обрабатываются два события. В первом случае <xref:System.Windows.Forms.Control.Click> событие элемента управления <xref:System.Windows.Forms.Button>, создается экземпляр класса <xref:System.Windows.Forms.PrintDialog> и выбранный пользователем принтер захватывается в свойстве <xref:System.Windows.Forms.DialogResult>.  
  
     Во втором событии <xref:System.Drawing.Printing.PrintDocument.PrintPage> события компонента <xref:System.Drawing.Printing.PrintDocument> образец документа печатается на указанном принтере.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Визуальный C# элемент C++и визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Поддержка печати в Windows Forms](windows-forms-print-support.md)
