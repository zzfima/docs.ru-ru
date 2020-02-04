---
title: Как печатать графику
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 2435b3bc14747a00d2a0fc03a9ebd21ae43c5369
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740645"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Практическое руководство. Печать графических изображений в Windows Forms
Часто требуется печатать графику в приложении Windows. Класс <xref:System.Drawing.Graphics> предоставляет методы для рисования объектов на устройстве, например на экране или принтере.  
  
### <a name="to-print-graphics"></a>Печать графики  
  
1. Добавьте в форму компонент <xref:System.Drawing.Printing.PrintDocument>.  
  
2. В обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage> используйте свойство <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs>, чтобы указать принтеру, какой тип графики печатать.  
  
     В следующем примере кода показан обработчик событий, используемый для создания синего эллипса в ограничивающем прямоугольнике. Прямоугольник имеет следующее расположение и измерения: начиная с 100, 150 со шириной 250 и высотой 250.  
  
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
  
     (Визуальный C# элемент C++и визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Поддержка печати в Windows Forms](windows-forms-print-support.md)
