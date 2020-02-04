---
title: Отображать предварительный просмотр в Windows Forms приложениях
titleSuffix: ''
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
ms.openlocfilehash: ac02339ad86e491cd047dcd4b0c8841374b3bb2e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745569"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms
С помощью элемента управления <xref:System.Windows.Forms.PrintPreviewDialog> можно разрешить пользователям отображать документ, часто перед его печатью.  
  
 Для этого необходимо указать экземпляр класса <xref:System.Drawing.Printing.PrintDocument>. Это документ для печати. Дополнительные сведения об использовании предварительного просмотра с компонентом <xref:System.Drawing.Printing.PrintDocument> см. [в разделе инструкции. Печать в Windows Forms с помощью предварительного просмотра](../advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
> Чтобы использовать элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> во время выполнения, на компьютере пользователя должен быть установлен принтер, как локально, так и через сеть, поскольку это частично, как компонент <xref:System.Windows.Forms.PrintPreviewDialog> определяет, как будет выглядеть документ при печати.  
  
 Элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> использует класс <xref:System.Drawing.Printing.PrinterSettings>. Кроме того, элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> использует класс <xref:System.Drawing.Printing.PageSettings>, точно так же, как и компонент <xref:System.Windows.Forms.PrintPreviewDialog>. Документ печати, указанный в свойстве <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления, относится к экземплярам классов <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings>, и они используются для отрисовки документа в окне предварительного просмотра.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Просмотр страниц с помощью элемента управления PrintPreviewDialog  
  
- Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый <xref:System.Drawing.Printing.PrintDocument> .  
  
     В следующем примере кода обработчик событий <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> открывает экземпляр элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>. Документ печати задается в свойстве <xref:System.Windows.Forms.PrintDialog.Document%2A>. В приведенном ниже примере не указан документ Print.  
  
     В примере требуется, чтобы в форме был элемент управления <xref:System.Windows.Forms.Button>, <xref:System.Drawing.Printing.PrintDocument> компонент с именем `myDocument`и элемент управления <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
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
  
     (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Компонент PrintDocument](printdocument-component-windows-forms.md)
- [Элемент управления PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Поддержка печати в Windows Forms](../advanced/windows-forms-print-support.md)
- [Windows Forms](../index.md)
