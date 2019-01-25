---
title: Как выполнить Рисование фундаментальных сплайнов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 9f2fd0f54c95ff2185c1a1d17785d300c97f7f4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739804"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="59bd2-102">Как выполнить Рисование фундаментальных сплайнов</span><span class="sxs-lookup"><span data-stu-id="59bd2-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="59bd2-103">Фундаментальный сплайн представляет кривую, проходящую через заданные точки.</span><span class="sxs-lookup"><span data-stu-id="59bd2-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="59bd2-104">Чтобы нарисовать фундаментальный сплайн, создайте <xref:System.Drawing.Graphics> и передать адрес массив точек для <xref:System.Drawing.Graphics.DrawCurve%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="59bd2-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="59bd2-105">Рисование колоколообразной фундаментального сплайна</span><span class="sxs-lookup"><span data-stu-id="59bd2-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="59bd2-106">Следующий пример выводит колоколообразной фундаментальный сплайн, проходящий через пять определенных точек.</span><span class="sxs-lookup"><span data-stu-id="59bd2-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="59bd2-107">На следующем рисунке кривой и пять точек.</span><span class="sxs-lookup"><span data-stu-id="59bd2-107">The following illustration shows the curve and five points.</span></span>  
  
     <span data-ttu-id="59bd2-108">![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span><span class="sxs-lookup"><span data-stu-id="59bd2-108">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="59bd2-109">Рисование замкнутую кривую Кардинала</span><span class="sxs-lookup"><span data-stu-id="59bd2-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="59bd2-110">Используйте <xref:System.Drawing.Graphics.DrawClosedCurve%2A> метод <xref:System.Drawing.Graphics> классе для рисования замкнутый фундаментальный сплайн.</span><span class="sxs-lookup"><span data-stu-id="59bd2-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="59bd2-111">В замкнутой фундаментальной кривой продолжается с помощью последней точки в массиве и подключается с первой точки в массиве.</span><span class="sxs-lookup"><span data-stu-id="59bd2-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="59bd2-112">В следующем примере рисуется замкнутый фундаментальный сплайн, проходящий через шесть определенных точек.</span><span class="sxs-lookup"><span data-stu-id="59bd2-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="59bd2-113">Ниже показан замкнутый сплайн и шесть точек.</span><span class="sxs-lookup"><span data-stu-id="59bd2-113">The following illustration shows the closed spline along with the six points.</span></span>  
  
 <span data-ttu-id="59bd2-114">![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span><span class="sxs-lookup"><span data-stu-id="59bd2-114">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="59bd2-115">Изменение изгиба фундаментального сплайна</span><span class="sxs-lookup"><span data-stu-id="59bd2-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="59bd2-116">Изменить способ изгиб фундаментального сплайна, передав аргумент натяжение <xref:System.Drawing.Graphics.DrawCurve%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="59bd2-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="59bd2-117">В следующем примере рисуется три фундаментальные сплайны, которые проходят через тот же набор точек.</span><span class="sxs-lookup"><span data-stu-id="59bd2-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="59bd2-118">Ниже представлены три сплайна вместе со значениями натяжение.</span><span class="sxs-lookup"><span data-stu-id="59bd2-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="59bd2-119">Обратите внимание, что если натяжение равно 0, точки соединенных прямых линий.</span><span class="sxs-lookup"><span data-stu-id="59bd2-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 <span data-ttu-id="59bd2-120">![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span><span class="sxs-lookup"><span data-stu-id="59bd2-120">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="59bd2-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="59bd2-121">Compiling the Code</span></span>  
 <span data-ttu-id="59bd2-122">Предыдущий пример предназначен для работы с Windows Forms, и они требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="59bd2-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59bd2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="59bd2-123">See also</span></span>
- [<span data-ttu-id="59bd2-124">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="59bd2-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [<span data-ttu-id="59bd2-125">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="59bd2-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
