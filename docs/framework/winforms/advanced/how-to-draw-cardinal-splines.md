---
title: Практическое руководство. Рисование фундаментальных сплайнов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 2f03177bf97936a2ca9558972d4d82fa3e07463c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204956"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="a6d5f-102">Практическое руководство. Рисование фундаментальных сплайнов</span><span class="sxs-lookup"><span data-stu-id="a6d5f-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="a6d5f-103">Фундаментальный сплайн представляет кривую, проходящую через заданные точки.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="a6d5f-104">Чтобы нарисовать фундаментальный сплайн, создайте <xref:System.Drawing.Graphics> и передать адрес массив точек для <xref:System.Drawing.Graphics.DrawCurve%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="a6d5f-105">Рисование колоколообразной фундаментального сплайна</span><span class="sxs-lookup"><span data-stu-id="a6d5f-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="a6d5f-106">Следующий пример выводит колоколообразной фундаментальный сплайн, проходящий через пять определенных точек.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="a6d5f-107">На следующем рисунке кривой и пять точек.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-107">The following illustration shows the curve and five points.</span></span>  
  
     ![Схема, показывающая колоколообразной фундаментальный сплайн.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="a6d5f-109">Рисование замкнутую кривую Кардинала</span><span class="sxs-lookup"><span data-stu-id="a6d5f-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="a6d5f-110">Используйте <xref:System.Drawing.Graphics.DrawClosedCurve%2A> метод <xref:System.Drawing.Graphics> классе для рисования замкнутый фундаментальный сплайн.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="a6d5f-111">В замкнутой фундаментальной кривой продолжается с помощью последней точки в массиве и подключается с первой точки в массиве.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="a6d5f-112">В следующем примере рисуется замкнутый фундаментальный сплайн, проходящий через шесть определенных точек.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="a6d5f-113">На следующем рисунке показан замкнутый сплайн и шесть точек:</span><span class="sxs-lookup"><span data-stu-id="a6d5f-113">The following illustration shows the closed spline along with the six points:</span></span>  
  
 ![Схема, показывающая замкнутый фундаментальный сплайн.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="a6d5f-115">Изменение изгиба фундаментального сплайна</span><span class="sxs-lookup"><span data-stu-id="a6d5f-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="a6d5f-116">Изменить способ изгиб фундаментального сплайна, передав аргумент натяжение <xref:System.Drawing.Graphics.DrawCurve%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="a6d5f-117">В следующем примере рисуется три фундаментальные сплайны, которые проходят через тот же набор точек.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="a6d5f-118">Ниже представлены три сплайна вместе со значениями натяжение.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="a6d5f-119">Обратите внимание, что если натяжение равно 0, точки соединенных прямых линий.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 ![Схема, показывающая три фундаментальные сплайны.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a6d5f-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a6d5f-121">Compiling the Code</span></span>  
 <span data-ttu-id="a6d5f-122">Предыдущий пример предназначен для работы с Windows Forms, и они требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="a6d5f-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d5f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a6d5f-123">See also</span></span>

- [<span data-ttu-id="a6d5f-124">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="a6d5f-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a6d5f-125">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="a6d5f-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
