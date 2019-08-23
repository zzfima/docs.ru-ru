---
title: Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: 5a18539153c64a5059d8079f6e245115b026bb91
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950150"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="577f6-102">Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="577f6-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="577f6-103">При анимации простого графика пользователи иногда могут столкнуться с мерцанием или другими нежелательными визуальными эффектами.</span><span class="sxs-lookup"><span data-stu-id="577f6-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="577f6-104">Одним из способов ограничения этой проблемы является использование на графике процесса "BitBlt".</span><span class="sxs-lookup"><span data-stu-id="577f6-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="577f6-105">BitBlt — это перенос битовых блоков цветовых данных из исходного прямоугольника пикселей в целевой прямоугольник пикселей.</span><span class="sxs-lookup"><span data-stu-id="577f6-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="577f6-106">При использовании Windows Forms BitBlt выполняется с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метода <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="577f6-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="577f6-107">В параметрах метода указываются источник и назначение (точки), размер копируемой области и графический объект, используемый для рисования новой фигуры.</span><span class="sxs-lookup"><span data-stu-id="577f6-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="577f6-108">В приведенном ниже примере фигура рисуется на форме в своем <xref:System.Windows.Forms.Control.Paint> обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="577f6-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="577f6-109"><xref:System.Drawing.Graphics.CopyFromScreen%2A> Затем метод используется для дублирования фигуры.</span><span class="sxs-lookup"><span data-stu-id="577f6-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="577f6-110">Присвоение <xref:System.Windows.Forms.Control.DoubleBuffered%2A> свойству формы значения `true` приведет к двойному буферизации графического кода <xref:System.Windows.Forms.Control.Paint> в событии.</span><span class="sxs-lookup"><span data-stu-id="577f6-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="577f6-111">Несмотря на то, что при использовании приведенного ниже кода не будет выигрыша в производительности различимый, при работе с более сложным графическим кодом следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="577f6-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="577f6-112">Пример</span><span class="sxs-lookup"><span data-stu-id="577f6-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="577f6-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="577f6-113">Compiling the Code</span></span>  
 <span data-ttu-id="577f6-114">Приведенный выше код выполняется в обработчике <xref:System.Windows.Forms.Control.Paint> событий формы, чтобы графические объекты сохранялись при перерисовке формы.</span><span class="sxs-lookup"><span data-stu-id="577f6-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="577f6-115">Таким образом, не следует вызывать связанные с графиком методы в <xref:System.Windows.Forms.Form.Load> обработчике событий, так как рисуемое содержимое не будет перерисовано при изменении размера формы или ее скрытии другой формой.</span><span class="sxs-lookup"><span data-stu-id="577f6-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577f6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="577f6-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="577f6-117">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="577f6-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="577f6-118">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="577f6-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
