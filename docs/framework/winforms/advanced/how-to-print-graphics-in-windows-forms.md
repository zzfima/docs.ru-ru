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
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="cd1c6-102">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd1c6-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="cd1c6-103">Часто требуется печатать графику в приложении на базе Windows.</span><span class="sxs-lookup"><span data-stu-id="cd1c6-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="cd1c6-104">Класс <xref:System.Drawing.Graphics> предоставляет методы рисования объектов на устройстве, таких как экран или принтер.</span><span class="sxs-lookup"><span data-stu-id="cd1c6-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="cd1c6-105">Для печати графики</span><span class="sxs-lookup"><span data-stu-id="cd1c6-105">To print graphics</span></span>  
  
1. <span data-ttu-id="cd1c6-106">Добавьте <xref:System.Drawing.Printing.PrintDocument> компонент в форму.</span><span class="sxs-lookup"><span data-stu-id="cd1c6-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="cd1c6-107">В <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчике <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> событий используйте свойство <xref:System.Drawing.Printing.PrintPageEventArgs> класса, чтобы проинструктировать принтер о том, какую графику печатать.</span><span class="sxs-lookup"><span data-stu-id="cd1c6-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="cd1c6-108">Следующий пример кода показывает обработчик событий, используемый для создания синего эллипса в связующего прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="cd1c6-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="cd1c6-109">Прямоугольник имеет следующее расположение и размеры: начиная с 100, 150 с шириной 250 и высотой 250.</span><span class="sxs-lookup"><span data-stu-id="cd1c6-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="cd1c6-110">(Визуальный C и Визуальный C ) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="cd1c6-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd1c6-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cd1c6-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="cd1c6-112">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd1c6-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
