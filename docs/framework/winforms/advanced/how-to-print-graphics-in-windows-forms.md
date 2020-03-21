---
title: 'Как: Печать Графика'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182534"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Практическое руководство. Печать графических изображений в Windows Forms
Часто требуется печатать графику в приложении на базе Windows. Класс <xref:System.Drawing.Graphics> предоставляет методы рисования объектов на устройстве, таких как экран или принтер.  
  
### <a name="to-print-graphics"></a>Для печати графики  
  
1. Добавьте <xref:System.Drawing.Printing.PrintDocument> компонент в форму.  
  
2. В <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчике <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> событий используйте свойство <xref:System.Drawing.Printing.PrintPageEventArgs> класса, чтобы проинструктировать принтер о том, какую графику печатать.  
  
     Следующий пример кода показывает обработчик событий, используемый для создания синего эллипса в связующего прямоугольнике. Прямоугольник имеет следующее расположение и размеры: начиная с 100, 150 с шириной 250 и высотой 250.  
  
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
  
     (Визуальный C и Визуальный C ) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
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
