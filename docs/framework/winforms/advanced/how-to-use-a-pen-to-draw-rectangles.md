---
title: Практическое руководство. Рисование прямоугольников с помощью пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: a29cae5a360185b7fa5e70fc0181c0cfaac8fc09
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463193"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="ff9f5-102">Практическое руководство. Рисование прямоугольников с помощью пера</span><span class="sxs-lookup"><span data-stu-id="ff9f5-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="ff9f5-103">Рисование прямоугольников, вам потребуется <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="ff9f5-104"><xref:System.Drawing.Graphics> Предоставляет <xref:System.Drawing.Graphics.DrawRectangle%2A> метод и <xref:System.Drawing.Pen> объект сохраняет функции, строки, таких как цвет и ширину.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff9f5-105">Пример</span><span class="sxs-lookup"><span data-stu-id="ff9f5-105">Example</span></span>  
 <span data-ttu-id="ff9f5-106">В следующем примере рисуется прямоугольник с его верхнего левого угла в (10, 10).</span><span class="sxs-lookup"><span data-stu-id="ff9f5-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="ff9f5-107">Прямоугольник имеет ширину 100 и высотой 50.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="ff9f5-108">Второй аргумент, переданный <xref:System.Drawing.Pen.%23ctor%2A> конструктор указывает, что толщина пера равно 5 пикселям.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="ff9f5-109">При рисовании прямоугольника перо располагается по центру прямоугольника границ.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="ff9f5-110">Поскольку ширины пера равно 5, сторон прямоугольника являются формируемого 5 пикселов шириной 1 пиксель рисуется по самой границе, рисуются 2 пикселя внутри, и 2 пикселя рисуются с внешней стороны.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="ff9f5-111">Дополнительные сведения о см. в разделе [как: Значение толщины и выравнивания пера](how-to-set-pen-width-and-alignment.md).</span><span class="sxs-lookup"><span data-stu-id="ff9f5-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="ff9f5-112">На следующем рисунке показан полученный прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="ff9f5-113">Пунктирные линии показывают, где был бы нарисован прямоугольник, если ширина пера был один пиксель.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="ff9f5-114">Увеличенное верхнего левого угла прямоугольника показывает, что жирные черные линии центрируются по эти пунктирные линии.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![Снимок экрана, показывающий изображенного прямоугольника с черным и пунктирные линии.](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff9f5-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ff9f5-116">Compiling the Code</span></span>  
 <span data-ttu-id="ff9f5-117">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="ff9f5-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9f5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ff9f5-118">See also</span></span>
- [<span data-ttu-id="ff9f5-119">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="ff9f5-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
