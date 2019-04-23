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
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107332"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="cb495-102">B&#233;Безье сплайны в GDI +</span><span class="sxs-lookup"><span data-stu-id="cb495-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="cb495-103">Сплайн Безье — кривой, определяемый четырьмя точками: двумя конечными точками (p1 и p2) и двумя контрольными точками (c1 и c2).</span><span class="sxs-lookup"><span data-stu-id="cb495-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="cb495-104">Кривая начинается с p1 и заканчивается в точке p2.</span><span class="sxs-lookup"><span data-stu-id="cb495-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="cb495-105">Кривая проходит через контрольные точки, но контрольные точки действуют как магниты, который извлекает кривой определенные инструкции и влияние на способ изгиба кривой.</span><span class="sxs-lookup"><span data-stu-id="cb495-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="cb495-106">Ниже показан кривую Безье, а также его конечные точки и точки управления.</span><span class="sxs-lookup"><span data-stu-id="cb495-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="cb495-107">![Сплайны Безье](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="cb495-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="cb495-108">Кривая начинается в точке p1 и переходит к контрольной точки c1.</span><span class="sxs-lookup"><span data-stu-id="cb495-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="cb495-109">Касательной к кривой в p1 — это линия, проведенная через p1 до c1.</span><span class="sxs-lookup"><span data-stu-id="cb495-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="cb495-110">Касательной в конечной точке p2 — это линия, проведенная через c2 на p2.</span><span class="sxs-lookup"><span data-stu-id="cb495-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="cb495-111">Рисование сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="cb495-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="cb495-112">Чтобы нарисовать сплайн Безье, вам потребуется экземпляр <xref:System.Drawing.Graphics> класс и <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="cb495-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="cb495-113">Экземпляр <xref:System.Drawing.Graphics> класс предоставляет <xref:System.Drawing.Graphics.DrawBezier%2A> метод и <xref:System.Drawing.Pen> сохраняет атрибуты, например, ширина и цвет линии, используемый для отображения кривой.</span><span class="sxs-lookup"><span data-stu-id="cb495-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="cb495-114"><xref:System.Drawing.Pen> Передается в качестве одного из аргументов для <xref:System.Drawing.Graphics.DrawBezier%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="cb495-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="cb495-115">Остальные аргументы, передаваемые <xref:System.Drawing.Graphics.DrawBezier%2A> метод: конечные точки и точки управления.</span><span class="sxs-lookup"><span data-stu-id="cb495-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="cb495-116">В следующем примере рисуется сплайн Безье с начальной точки (0, 0), управлять точками (40, 20) и (80, 150) и конечную точку (100, 10):</span><span class="sxs-lookup"><span data-stu-id="cb495-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="cb495-117">Кривой, контрольные точки и две касательные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cb495-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="cb495-118">![Сплайны Безье](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="cb495-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="cb495-119">Сплайны Безье изначально были разработаны Пьер Безье для использования в автомобильной промышленности.</span><span class="sxs-lookup"><span data-stu-id="cb495-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="cb495-120">Они оказались будут полезны во многих типах автоматизированного проектирования и также используются для определения контуры шрифтов.</span><span class="sxs-lookup"><span data-stu-id="cb495-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="cb495-121">Сплайны Безье можно создавать множество различных фигур, некоторые из которых показаны на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="cb495-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="cb495-122">![Пути](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="cb495-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb495-123">См. также</span><span class="sxs-lookup"><span data-stu-id="cb495-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="cb495-124">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="cb495-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="cb495-125">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="cb495-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="cb495-126">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="cb495-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="cb495-127">Практическое руководство. Создание пера</span><span class="sxs-lookup"><span data-stu-id="cb495-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
