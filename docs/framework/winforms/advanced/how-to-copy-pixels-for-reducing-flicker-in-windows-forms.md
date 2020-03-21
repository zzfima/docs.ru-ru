---
title: 'Как: Копировать пикселей для уменьшения мерцания'
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
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182589"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="638b2-102">Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="638b2-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="638b2-103">Когда вы анимируете простой график, пользователи иногда могут столкнуться с мерцание или другие нежелательные визуальные эффекты.</span><span class="sxs-lookup"><span data-stu-id="638b2-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="638b2-104">Один из способов ограничить эту проблему заключается в использовании "bitblt" процесс на графике.</span><span class="sxs-lookup"><span data-stu-id="638b2-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="638b2-105">Bitblt — это «перенос бит-блока» цветовых данных из прямоугольника пикселей происхождения в прямоугольник пикселей назначения.</span><span class="sxs-lookup"><span data-stu-id="638b2-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="638b2-106">С Windows Forms, bitblt выполняется с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метода <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="638b2-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="638b2-107">В параметрах метода указанисточник источника и пункта (в виде точек), размера области, поднимила копироваться, и графического объекта, используемого для рисования новой формы.</span><span class="sxs-lookup"><span data-stu-id="638b2-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="638b2-108">В приведенном ниже примере форма нарисована на форме в обработчике <xref:System.Windows.Forms.Control.Paint> событий.</span><span class="sxs-lookup"><span data-stu-id="638b2-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="638b2-109">Затем <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод используется для дублирования формы.</span><span class="sxs-lookup"><span data-stu-id="638b2-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="638b2-110">Установка <xref:System.Windows.Forms.Control.DoubleBuffered%2A> свойства формы `true` сделает графический код в <xref:System.Windows.Forms.Control.Paint> случае двойного буфера.</span><span class="sxs-lookup"><span data-stu-id="638b2-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="638b2-111">Хотя при использовании приведенного ниже кода это не будет иметь заметного повышения производительности, это то, что нужно иметь в виду при работе с более сложным графическим кодом манипуляций.</span><span class="sxs-lookup"><span data-stu-id="638b2-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="638b2-112">Пример</span><span class="sxs-lookup"><span data-stu-id="638b2-112">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="638b2-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="638b2-113">Compiling the Code</span></span>  
 <span data-ttu-id="638b2-114">Приведенный выше код работает в <xref:System.Windows.Forms.Control.Paint> обработчике событий формы, так что графика сохраняется при перерисовке формы.</span><span class="sxs-lookup"><span data-stu-id="638b2-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="638b2-115">Таким образом, не вызывайте методы, <xref:System.Windows.Forms.Form.Load> связанные с графикой, в обработчике событий, поскольку нарисованное содержимое не будет перерисовано, если форма будет уменьшена или заслонена другой формой.</span><span class="sxs-lookup"><span data-stu-id="638b2-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638b2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="638b2-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="638b2-117">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="638b2-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="638b2-118">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="638b2-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
