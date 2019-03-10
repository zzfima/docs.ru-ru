---
title: Практическое руководство. Печать графических изображений в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: cb8c9f291103915c82fb31af5c6668fbd0648f66
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721323"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="25a8c-102">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25a8c-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="25a8c-103">Часто требуется печать графических изображений в приложении Windows.</span><span class="sxs-lookup"><span data-stu-id="25a8c-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="25a8c-104"><xref:System.Drawing.Graphics> Класс предоставляет методы для рисования объектов на таких устройствах, как экран или принтер.</span><span class="sxs-lookup"><span data-stu-id="25a8c-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="25a8c-105">Чтобы печать графических изображений</span><span class="sxs-lookup"><span data-stu-id="25a8c-105">To print graphics</span></span>  
  
1.  <span data-ttu-id="25a8c-106">Добавление <xref:System.Drawing.Printing.PrintDocument> форму компонента.</span><span class="sxs-lookup"><span data-stu-id="25a8c-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="25a8c-107">В <xref:System.Drawing.Printing.PrintDocument.PrintPage> обработчик событий, используйте <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> свойство <xref:System.Drawing.Printing.PrintPageEventArgs> класса, чтобы сообщить принтеру на какого рода графики для печати.</span><span class="sxs-lookup"><span data-stu-id="25a8c-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="25a8c-108">В следующем примере кода показан обработчик событий, используемый для создания синего эллипса внутри ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="25a8c-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="25a8c-109">Прямоугольник имеет следующее расположение и размеры: начиная со 100, 150, 250 в ширину и высоту 250.</span><span class="sxs-lookup"><span data-stu-id="25a8c-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="25a8c-110">(Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="25a8c-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25a8c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="25a8c-111">See also</span></span>
- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="25a8c-112">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25a8c-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
