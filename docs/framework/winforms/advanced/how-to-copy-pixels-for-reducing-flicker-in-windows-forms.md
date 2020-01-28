---
title: Как копировать пиксели для снижения мерцания
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
ms.openlocfilehash: 299041e7038d5bd5b9824d668b3f47d842030ac7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746483"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="da1eb-102">Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da1eb-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="da1eb-103">При анимации простого графика пользователи иногда могут столкнуться с мерцанием или другими нежелательными визуальными эффектами.</span><span class="sxs-lookup"><span data-stu-id="da1eb-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="da1eb-104">Одним из способов ограничения этой проблемы является использование на графике процесса "BitBlt".</span><span class="sxs-lookup"><span data-stu-id="da1eb-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="da1eb-105">BitBlt — это перенос битовых блоков цветовых данных из исходного прямоугольника пикселей в целевой прямоугольник пикселей.</span><span class="sxs-lookup"><span data-stu-id="da1eb-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="da1eb-106">С Windows Forms BitBlt выполняется с помощью метода <xref:System.Drawing.Graphics.CopyFromScreen%2A> класса <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="da1eb-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="da1eb-107">В параметрах метода указываются источник и назначение (точки), размер копируемой области и графический объект, используемый для рисования новой фигуры.</span><span class="sxs-lookup"><span data-stu-id="da1eb-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="da1eb-108">В приведенном ниже примере фигура рисуется на форме в своем <xref:System.Windows.Forms.Control.Paint> обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="da1eb-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="da1eb-109">Затем для дублирования фигуры используется метод <xref:System.Drawing.Graphics.CopyFromScreen%2A>.</span><span class="sxs-lookup"><span data-stu-id="da1eb-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da1eb-110">Присвоение свойству <xref:System.Windows.Forms.Control.DoubleBuffered%2A> формы значения `true` приведет к двойному буферизации графического кода в событии <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="da1eb-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="da1eb-111">Несмотря на то, что при использовании приведенного ниже кода не будет выигрыша в производительности различимый, при работе с более сложным графическим кодом следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="da1eb-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da1eb-112">Пример</span><span class="sxs-lookup"><span data-stu-id="da1eb-112">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="da1eb-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="da1eb-113">Compiling the Code</span></span>  
 <span data-ttu-id="da1eb-114">Приведенный выше код выполняется в обработчике событий <xref:System.Windows.Forms.Control.Paint> формы, чтобы графические объекты сохранялись при перерисовке формы.</span><span class="sxs-lookup"><span data-stu-id="da1eb-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="da1eb-115">Таким образом, не следует вызывать методы, связанные с графикой, в обработчике событий <xref:System.Windows.Forms.Form.Load>, поскольку рисуемое содержимое не будет перерисовано при изменении размера формы или ее скрытии другой формой.</span><span class="sxs-lookup"><span data-stu-id="da1eb-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da1eb-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="da1eb-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="da1eb-117">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da1eb-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="da1eb-118">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="da1eb-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
