---
title: "Практическое руководство. Рисование фундаментальных сплайнов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c47ff269cb1c367abee0be197fdc80485fb37b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="1f587-102">Практическое руководство. Рисование фундаментальных сплайнов</span><span class="sxs-lookup"><span data-stu-id="1f587-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="1f587-103">Фундаментальный сплайн представляет кривую, проходящую через заданные точки.</span><span class="sxs-lookup"><span data-stu-id="1f587-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="1f587-104">Чтобы нарисовать фундаментальный сплайн, создайте <xref:System.Drawing.Graphics> и передать массив указывает на адрес <xref:System.Drawing.Graphics.DrawCurve%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1f587-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="1f587-105">Рисование колоколообразной фундаментальный сплайн</span><span class="sxs-lookup"><span data-stu-id="1f587-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="1f587-106">Следующий пример выводит колоколообразной фундаментальный сплайн, проходящий через пять заданных точек.</span><span class="sxs-lookup"><span data-stu-id="1f587-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="1f587-107">Кривая и пять точек на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="1f587-107">The following illustration shows the curve and five points.</span></span>  
  
     <span data-ttu-id="1f587-108">![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span><span class="sxs-lookup"><span data-stu-id="1f587-108">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="1f587-109">Рисование замкнутый фундаментальный сплайн</span><span class="sxs-lookup"><span data-stu-id="1f587-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="1f587-110">Используйте <xref:System.Drawing.Graphics.DrawClosedCurve%2A> метод <xref:System.Drawing.Graphics> для отрисовки замкнутый фундаментальный сплайн.</span><span class="sxs-lookup"><span data-stu-id="1f587-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="1f587-111">В замкнутой фундаментальной сплайновой кривой продолжается за последнюю точку в массиве и подключается с первой точки в массиве.</span><span class="sxs-lookup"><span data-stu-id="1f587-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="1f587-112">В следующем примере рисуется замкнутый фундаментальный сплайн, проходящий через шесть заданных точек.</span><span class="sxs-lookup"><span data-stu-id="1f587-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="1f587-113">На следующем рисунке замкнутый сплайн и шесть точек.</span><span class="sxs-lookup"><span data-stu-id="1f587-113">The following illustration shows the closed spline along with the six points.</span></span>  
  
 <span data-ttu-id="1f587-114">![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span><span class="sxs-lookup"><span data-stu-id="1f587-114">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="1f587-115">Изменение изгиба фундаментальный сплайн</span><span class="sxs-lookup"><span data-stu-id="1f587-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="1f587-116">Изменение способа изгиб фундаментальный сплайн, передавая значение параметра натяжения <xref:System.Drawing.Graphics.DrawCurve%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1f587-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="1f587-117">В следующем примере рисуется три фундаментальные сплайны, которые проходят через один и тот же набор точек.</span><span class="sxs-lookup"><span data-stu-id="1f587-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="1f587-118">Ниже представлены три сплайна вместе с соответствующими значениями параметра натяжения.</span><span class="sxs-lookup"><span data-stu-id="1f587-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="1f587-119">Обратите внимание, что в случае, когда параметр натяжения равен 0, точки соединяются прямых линий.</span><span class="sxs-lookup"><span data-stu-id="1f587-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 <span data-ttu-id="1f587-120">![Фундаментальный сплайн](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span><span class="sxs-lookup"><span data-stu-id="1f587-120">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1f587-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1f587-121">Compiling the Code</span></span>  
 <span data-ttu-id="1f587-122">Предыдущий пример предназначен для работы с Windows Forms, и требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="1f587-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f587-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1f587-123">See Also</span></span>  
 [<span data-ttu-id="1f587-124">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="1f587-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="1f587-125">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="1f587-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
