---
title: B&#233;Безье сплайны в GDI +
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: 2e247ec2bcd57c2fb2f5c32f61d38a2e7a267ff1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517577"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="83b7e-102">B&#233;Безье сплайны в GDI +</span><span class="sxs-lookup"><span data-stu-id="83b7e-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="83b7e-103">Сплайн Безье — это кривая, задаваемая четырьмя точками: двумя конечными точками (p1 и p2) и двумя контрольными точками (c1 и c2).</span><span class="sxs-lookup"><span data-stu-id="83b7e-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="83b7e-104">Кривая начинается в точке p1 и заканчивается в точке p2.</span><span class="sxs-lookup"><span data-stu-id="83b7e-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="83b7e-105">Кривая не проходит через контрольные точки, но контрольные точки действуют как магниты удаление кривой в определенных направлениях и влияние на способ изгиба кривой.</span><span class="sxs-lookup"><span data-stu-id="83b7e-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="83b7e-106">На следующем рисунке кривая Безье и ее конечные и контрольные точки.</span><span class="sxs-lookup"><span data-stu-id="83b7e-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="83b7e-107">![Сплайны Безье](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="83b7e-107">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="83b7e-108">Кривая начинается в точке p1 и перемещается в направлении контрольной точки c1.</span><span class="sxs-lookup"><span data-stu-id="83b7e-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="83b7e-109">Касательной к кривой в p1 — это линия, соединяющей p1 для c1.</span><span class="sxs-lookup"><span data-stu-id="83b7e-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="83b7e-110">Касательной в конечной точке p2 — это линия, соединяющей c2 на p2.</span><span class="sxs-lookup"><span data-stu-id="83b7e-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="83b7e-111">Рисование сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="83b7e-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="83b7e-112">Чтобы нарисовать сплайн Безье, требуются объекты <xref:System.Drawing.Graphics> класса и <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="83b7e-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="83b7e-113">Экземпляр <xref:System.Drawing.Graphics> класс предоставляет <xref:System.Drawing.Graphics.DrawBezier%2A> метода и <xref:System.Drawing.Pen> хранит атрибуты, такие как ширина и цвет линии, используемой для подготовки к просмотру кривой.</span><span class="sxs-lookup"><span data-stu-id="83b7e-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="83b7e-114"><xref:System.Drawing.Pen> Передается в качестве одного из аргументов <xref:System.Drawing.Graphics.DrawBezier%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="83b7e-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="83b7e-115">Остальные аргументы, передаваемые <xref:System.Drawing.Graphics.DrawBezier%2A> метод — конечные точки и контрольные точки.</span><span class="sxs-lookup"><span data-stu-id="83b7e-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="83b7e-116">В следующем примере рисуется сплайн Безье с начальной точкой (0, 0), управления точками (40, 20) и (80, 150) и конечную точку с координатами (100, 10):</span><span class="sxs-lookup"><span data-stu-id="83b7e-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="83b7e-117">Кривая, контрольные точки и две касательные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="83b7e-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="83b7e-118">![Сплайны Безье](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="83b7e-118">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="83b7e-119">Сплайны Безье изначально были разработаны Пьер Безье для использования в автомобильной промышленности.</span><span class="sxs-lookup"><span data-stu-id="83b7e-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="83b7e-120">Они оказались во многих типов автоматизированного проектирования и также используются для определения структуры шрифтов.</span><span class="sxs-lookup"><span data-stu-id="83b7e-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="83b7e-121">Сплайны Безье можно создавать множество различных фигур, некоторые из которых показаны на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="83b7e-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="83b7e-122">![Пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="83b7e-122">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b7e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="83b7e-123">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="83b7e-124">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="83b7e-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="83b7e-125">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="83b7e-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [<span data-ttu-id="83b7e-126">Практическое руководство. Создание графических объектов для рисования</span><span class="sxs-lookup"><span data-stu-id="83b7e-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="83b7e-127">Практическое руководство. Создание пера</span><span class="sxs-lookup"><span data-stu-id="83b7e-127">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
