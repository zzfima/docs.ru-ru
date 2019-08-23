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
ms.openlocfilehash: 8252906de9a574f49617609a4cb08a1e8aa6a992
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929008"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms
<xref:System.Windows.Forms.PrintPreviewDialog> Элемент управления можно использовать для предоставления пользователям возможности отображать документ, часто перед его печатью.  
  
 Для этого необходимо указать экземпляр <xref:System.Drawing.Printing.PrintDocument> класса; это документ для печати. Дополнительные сведения об использовании предварительного просмотра с <xref:System.Drawing.Printing.PrintDocument> компонентом см. в разделе как [ Печать в Windows Forms с помощью предварительного](../advanced/how-to-print-in-windows-forms-using-print-preview.md)просмотра.  
  
> [!NOTE]
> Чтобы использовать <xref:System.Windows.Forms.PrintPreviewDialog> элемент управления во время выполнения, на компьютере пользователя должен быть установлен принтер (локально или через сеть), поскольку он частично определяет, <xref:System.Windows.Forms.PrintPreviewDialog> как именно этот документ будет выглядеть при печати.  
  
 <xref:System.Windows.Forms.PrintPreviewDialog> Элемент управления<xref:System.Drawing.Printing.PrinterSettings> использует класс. Кроме того, <xref:System.Windows.Forms.PrintPreviewDialog> элемент управления <xref:System.Drawing.Printing.PageSettings> использует класс так же, как <xref:System.Windows.Forms.PrintPreviewDialog> и компонент. Документ <xref:System.Windows.Forms.PrintPreviewDialog> печати, указанный в <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> свойстве элемента управления, относится <xref:System.Drawing.Printing.PrinterSettings> к экземплярам классов и <xref:System.Drawing.Printing.PageSettings> и используется для отрисовки документа в окне предварительного просмотра.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Просмотр страниц с помощью элемента управления PrintPreviewDialog  
  
- Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый <xref:System.Drawing.Printing.PrintDocument> .  
  
     В следующем примере <xref:System.Windows.Forms.Button> кода обработчик <xref:System.Windows.Forms.Control.Click> событий элемента управления <xref:System.Windows.Forms.PrintPreviewDialog> открывает экземпляр элемента управления. Документ печати задается в <xref:System.Windows.Forms.PrintDialog.Document%2A> свойстве. В приведенном ниже примере не указан документ Print.  
  
     В примере требуется <xref:System.Windows.Forms.Button> , чтобы форма соработала элемент управления <xref:System.Drawing.Printing.PrintDocument> , <xref:System.Windows.Forms.PrintPreviewDialog> компонент `myDocument`с именем и элемент управления.  
  
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
  
## <a name="see-also"></a>См. также

- [Компонент PrintDocument](printdocument-component-windows-forms.md)
- [Элемент управления PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Поддержка печати в Windows Forms](../advanced/windows-forms-print-support.md)
- [Windows Forms](../index.md)
