---
title: "How to: Print Graphics in Windows Forms | Microsoft Docs"
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
  - "graphics, printing"
  - "printing [Windows Forms], graphics"
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# How to: Print Graphics in Windows Forms
Часто в приложениях Windows возникает необходимость печатать рисунки.  Класс <xref:System.Drawing.Graphics> предоставляет методы для рисования объектов на таких устройствах, как экран или принтер.  
  
### Чтобы напечатать рисунок, выполните следующие действия.  
  
1.  Добавьте компонент <xref:System.Drawing.Printing.PrintDocument> в форму.  
  
2.  В обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage> используйте свойство <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs> для указания принтеру типа графики, которую требуется напечатать.  
  
     В следующем примере показан обработчик событий, который используется для создания синего эллипса внутри ограничивающего прямоугольника.  Прямоугольник имеет следующее расположение и размеры: начало в точке \(100, 150\) с шириной 250 и высотой 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Поместите в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## См. также  
 <xref:System.Drawing.Graphics>   
 <xref:System.Drawing.Brush>   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)