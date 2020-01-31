---
title: Создание стандартных заданий печати
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
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741517"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Практическое руководство. Создание стандартных задания печати в Windows Forms
Основой печати в Windows Forms является компонент <xref:System.Drawing.Printing.PrintDocument> — точнее, <xref:System.Drawing.Printing.PrintDocument.PrintPage> событие. Написав код для работы с событием <xref:System.Drawing.Printing.PrintDocument.PrintPage>, можно указать, что печатать и как печатать.  
  
### <a name="to-create-a-print-job"></a>Создание задания печати  
  
1. Добавьте в форму компонент <xref:System.Drawing.Printing.PrintDocument>.  
  
2. Напишите код для обработки события <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Вам потребуется выполнить код для собственной логики печати. Кроме того, необходимо указать материал, который будет напечатан.  
  
     В следующем примере кода образец изображения в фигуре красного прямоугольника создается в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage>, чтобы он выводился как материал для печати.  
  
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
  
     Также может потребоваться написать код для событий <xref:System.Drawing.Printing.PrintDocument.BeginPrint> и <xref:System.Drawing.Printing.PrintDocument.EndPrint>, возможно, в том числе целого числа, представляющего общее число страниц для печати, которое уменьшается при печати каждой страницы.  
  
    > [!NOTE]
    > Вы можете добавить в форму компонент <xref:System.Windows.Forms.PrintDialog>, чтобы предоставить пользователям чистый и эффективный пользовательский интерфейс. Установка свойства <xref:System.Windows.Forms.PrintDialog.Document%2A> компонента <xref:System.Windows.Forms.PrintDialog> позволяет задавать свойства, связанные с печатаемым документом, с которым ведется работа в форме. Дополнительные сведения о компоненте <xref:System.Windows.Forms.PrintDialog> см. в разделе [компонент PrintDialog](../controls/printdialog-component-windows-forms.md).  
  
     Дополнительные сведения о Windows Forms заданий печати, в том числе о создании задания печати программным способом, см. в разделе <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Drawing.Printing.PrintDocument>
- [Поддержка печати в Windows Forms](windows-forms-print-support.md)
