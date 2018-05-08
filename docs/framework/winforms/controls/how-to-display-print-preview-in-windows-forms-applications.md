---
title: Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 1c1291ea675d823fab3052b0fa365cb2d4c31088
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms
Можно использовать <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления, чтобы разрешить пользователям часто отображение документа, прежде чем он станет для печати.  
  
 Чтобы сделать это, необходимо указать экземпляр <xref:System.Drawing.Printing.PrintDocument> класса; это документ для печати. Дополнительные сведения об использовании предварительного просмотра с <xref:System.Drawing.Printing.PrintDocument> компонента, в разделе [как: печать в Windows Forms с помощью предварительный](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Для использования <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления во время выполнения пользователи должны иметь установленный на своем компьютере, локально или через сеть, принтер, как это отчасти как <xref:System.Windows.Forms.PrintPreviewDialog> компонент определяет, как будет выглядеть при печати документа.  
  
 <xref:System.Windows.Forms.PrintPreviewDialog> Управления использует <xref:System.Drawing.Printing.PrinterSettings> класса. Кроме того <xref:System.Windows.Forms.PrintPreviewDialog> управления использует <xref:System.Drawing.Printing.PageSettings> класса, так же как и <xref:System.Windows.Forms.PrintPreviewDialog> компонент. Печать документа, указанного в <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> взаимодействует с экземплярами обоих <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings> классов и они используются для отображения документа в окне предварительного просмотра.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Просмотр страниц с помощью элемента управления PrintPreviewDialog  
  
-   Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый <xref:System.Drawing.Printing.PrintDocument> .  
  
     В следующем примере кода <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий открывает экземпляр <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления. Печать документа указывается в <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство. В следующем примере указано ни одного печати документа.  
  
     В этом примере предполагается, что имеет форму <xref:System.Windows.Forms.Button> управления <xref:System.Drawing.Printing.PrintDocument> компонент с именем `myDocument`и <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>См. также  
 [Компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
