---
title: Практическое руководство. Создание стандартных задания печати в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938233"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Практическое руководство. Создание стандартных задания печати в Windows Forms
Основой печати в Windows Forms является <xref:System.Drawing.Printing.PrintDocument> компонент — точнее <xref:System.Drawing.Printing.PrintDocument.PrintPage> , это событие. Написав код для <xref:System.Drawing.Printing.PrintDocument.PrintPage> работы с событием, можно указать, что печатать и как его печатать.  
  
### <a name="to-create-a-print-job"></a>Создание задания печати  
  
1. <xref:System.Drawing.Printing.PrintDocument> Добавьте компонент в форму.  
  
2. Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Вам потребуется выполнить код для собственной логики печати. Кроме того, необходимо указать материал, который будет напечатан.  
  
     В следующем примере кода образец изображения в фигуре красного прямоугольника создается в <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчике событий для выполнения печати материала.  
  
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
  
     (Визуальный C# элемент C++и визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
  
     Также может потребоваться написать код для <xref:System.Drawing.Printing.PrintDocument.BeginPrint> событий и <xref:System.Drawing.Printing.PrintDocument.EndPrint> , например, целое число, представляющее общее количество страниц для печати, которое уменьшается при печати каждой страницы.  
  
    > [!NOTE]
    > В форму можно добавить <xref:System.Windows.Forms.PrintDialog> компонент, чтобы предоставить пользователям чистый и эффективный пользовательский интерфейс. <xref:System.Windows.Forms.PrintDialog.Document%2A> Задание свойства <xref:System.Windows.Forms.PrintDialog> компонента позволяет задавать свойства, связанные с печатаемым документом, с которым вы работаете в форме. Дополнительные сведения о компоненте <xref:System.Windows.Forms.PrintDialog> см. в разделе [компонент PrintDialog](../controls/printdialog-component-windows-forms.md).  
  
     Дополнительные сведения о Windows Forms заданий печати, в том числе о создании задания печати программным способом, см. в разделе <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](windows-forms-print-support.md)
