---
title: "How to: Create Standard Windows Forms Print Jobs | Microsoft Docs"
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
  - "printing [Windows Forms]"
  - "printing [Windows Forms], creating print jobs"
  - "printing [Visual Basic], in Windows applications"
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# How to: Create Standard Windows Forms Print Jobs
Основой печати в Windows Forms является компонент <xref:System.Drawing.Printing.PrintDocument>, а точнее, событие <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  Чтобы определить объект печати и способ печати, требуется написать код для обработчика события <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
### Чтобы создать задание печати, выполните следующие действия.  
  
1.  Добавьте компонент <xref:System.Drawing.Printing.PrintDocument> в форму.  
  
2.  Напишите обработчик события <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
     Потребуется включить в код собственную логику печати.  Помимо этого потребуется указать материал, который нужно напечатать.  
  
     В следующем примере в качестве материала для печати в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage> создается образец рисунка в виде красного прямоугольника.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     Кроме того, можно написать обработчики событий <xref:System.Drawing.Printing.PrintDocument.BeginPrint> и <xref:System.Drawing.Printing.PrintDocument.EndPrint>, чтобы, например, добавить целое число, представляющее общее число страниц для печати, которое уменьшается при печати каждой страницы.  
  
    > [!NOTE]
    >  Для предоставления пользователям простого и эффективного пользовательского интерфейса можно добавить в форму компонент <xref:System.Windows.Forms.PrintDialog>.  Задавая свойство <xref:System.Windows.Forms.PrintDialog.Document%2A> компонента <xref:System.Windows.Forms.PrintDialog>, можно настроить параметры печати для документа, с которым работает форма.  Дополнительные сведения о компоненте <xref:System.Windows.Forms.PrintDialog> см. в разделе [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Дополнительные сведения об особенностях заданий печати в Windows Forms, в том числе о способах создания заданий печати программными средствами, см. в разделе <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## См. также  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)