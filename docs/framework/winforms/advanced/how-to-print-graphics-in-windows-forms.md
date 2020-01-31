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
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="9db92-102">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9db92-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="9db92-103">Часто требуется печатать графику в приложении Windows.</span><span class="sxs-lookup"><span data-stu-id="9db92-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="9db92-104">Класс <xref:System.Drawing.Graphics> предоставляет методы для рисования объектов на устройстве, например на экране или принтере.</span><span class="sxs-lookup"><span data-stu-id="9db92-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="9db92-105">Печать графики</span><span class="sxs-lookup"><span data-stu-id="9db92-105">To print graphics</span></span>  
  
1. <span data-ttu-id="9db92-106">Добавьте в форму компонент <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="9db92-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="9db92-107">В обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage> используйте свойство <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs>, чтобы указать принтеру, какой тип графики печатать.</span><span class="sxs-lookup"><span data-stu-id="9db92-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="9db92-108">В следующем примере кода показан обработчик событий, используемый для создания синего эллипса в ограничивающем прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="9db92-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="9db92-109">Прямоугольник имеет следующее расположение и измерения: начиная с 100, 150 со шириной 250 и высотой 250.</span><span class="sxs-lookup"><span data-stu-id="9db92-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="9db92-110">(Визуальный C# элемент C++и визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9db92-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9db92-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="9db92-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="9db92-112">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9db92-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
