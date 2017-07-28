---
title: "Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], предварительный просмотр"
  - "предварительный просмотр, отображение"
  - "печать [Windows Forms], предварительный просмотр"
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms
Элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> используется для отображения документа до того, как он будет напечатан.  
  
 Для этого необходимо указать экземпляр класса <xref:System.Drawing.Printing.PrintDocument>, представляющий документ, который должен быть напечатан.  Дополнительные сведения об использовании предварительного просмотра с компонентом <xref:System.Drawing.Printing.PrintDocument> см. в разделе [Практическое руководство. Печать в Windows Forms с использованием предварительного просмотра](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Чтобы использовать элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> во время выполнения, пользователи должны иметь установленный на компьютере локальный или сетевой принтер, так как это отчасти необходимо для определения компонентом <xref:System.Windows.Forms.PrintPreviewDialog>, как будет выглядеть документ при печати.  
  
 Элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> использует класс <xref:System.Drawing.Printing.PrinterSettings>.  Кроме того, элемент управления <xref:System.Windows.Forms.PrintPreviewDialog> использует класс <xref:System.Drawing.Printing.PageSettings>, так же как и компонент <xref:System.Windows.Forms.PrintPreviewDialog>.  Документ для печати, указанный в свойстве <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>, взаимодействует с экземплярами классов <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings>, которые используются для отображения документа в окне предварительного просмотра.  
  
### Просмотр страниц с помощью элемента управления PrintPreviewDialog  
  
-   Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый компонент <xref:System.Drawing.Printing.PrintDocument>.  
  
     В следующем примере кода обработчик событий <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> открывает экземпляр элемента управления <xref:System.Windows.Forms.PrintPreviewDialog>.  Документ, который требуется распечатать, указан с помощью свойства <xref:System.Windows.Forms.PrintDialog.Document%2A>.  В приведенном ниже примере не указан документ, который требуется распечатать.  
  
     В примере предполагается, что на форме существует элемент управления <xref:System.Windows.Forms.Button>, компонент <xref:System.Drawing.Printing.PrintDocument> с именем`myDocument` и элемент управления <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## См. также  
 [Компонент PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)   
 [Элемент управления PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)