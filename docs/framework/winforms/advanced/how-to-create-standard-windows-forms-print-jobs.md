---
title: Практическое руководство. Создание стандартных задания печати в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0090748ebdc52217176021c877949e62687e8a55
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Практическое руководство. Создание стандартных задания печати в Windows Forms
Основой печати в Windows Forms является <xref:System.Drawing.Printing.PrintDocument> компонента — в частности, <xref:System.Drawing.Printing.PrintDocument.PrintPage> событие. Путем написания кода для обработки <xref:System.Drawing.Printing.PrintDocument.PrintPage> событий, можно указать печати и способ печати.  
  
### <a name="to-create-a-print-job"></a>Чтобы создать задание печати  
  
1.  Добавить <xref:System.Drawing.Printing.PrintDocument> форму компонента.  
  
2.  Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
     Необходимо будет кода собственную логику печати. Кроме того нужно указать материала для печати.  
  
     В следующем примере создается образец рисунка в форму красный прямоугольник в <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчика событий в качестве материала для печати.  
  
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
  
     (Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
  
     Можно также написать код для <xref:System.Drawing.Printing.PrintDocument.BeginPrint> и <xref:System.Drawing.Printing.PrintDocument.EndPrint> события, например, целочисленное значение, представляющее общее число страниц для печати, уменьшается на единицу при печати каждой страницы.  
  
    > [!NOTE]
    >  Можно добавить <xref:System.Windows.Forms.PrintDialog> форму для предоставления пользователям простого и эффективного пользовательского интерфейса (UI) компонента. Установка <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство <xref:System.Windows.Forms.PrintDialog> включает компонент, можно задать свойства, относящиеся к печати документов, вы работаете с в форме. Дополнительные сведения о <xref:System.Windows.Forms.PrintDialog> компонента, в разделе [компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).  
  
     Дополнительные сведения об особенностях Windows Forms см. задания печати, включая способы создания заданий печати программными средствами, <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Поддержка печати в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
