---
title: Замкнутые и незамкнутые кривые в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: bc78077be45f22826eaa23a746dcf272601d51b4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711464"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="a2acf-102">Замкнутые и незамкнутые кривые в GDI+</span><span class="sxs-lookup"><span data-stu-id="a2acf-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="a2acf-103">На следующем рисунке показано две кривые: открытая и закрытая.</span><span class="sxs-lookup"><span data-stu-id="a2acf-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="a2acf-104">![Замкнутые и незамкнутые кривые](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="a2acf-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="a2acf-105">Управляемый интерфейс для кривых</span><span class="sxs-lookup"><span data-stu-id="a2acf-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="a2acf-106">Замкнутых кривых есть внутренняя область, поэтому могут заполняться с помощью кисти.</span><span class="sxs-lookup"><span data-stu-id="a2acf-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="a2acf-107"><xref:System.Drawing.Graphics> В класс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет следующие методы для заполнения замкнутые фигуры и кривых: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, и <xref:System.Drawing.Graphics.FillRegion%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2acf-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="a2acf-108">При вызове одного из этих методов, необходимо передать тип кисти (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, или <xref:System.Drawing.Drawing2D.PathGradientBrush>) в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="a2acf-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="a2acf-109"><xref:System.Drawing.Graphics.FillPie%2A> Метод является дополнением к <xref:System.Drawing.Graphics.DrawArc%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a2acf-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="a2acf-110">Так же, как <xref:System.Drawing.Graphics.DrawArc%2A> метод рисует части контура эллипса, <xref:System.Drawing.Graphics.FillPie%2A> метод заполняет часть внутреннюю часть эллипса.</span><span class="sxs-lookup"><span data-stu-id="a2acf-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="a2acf-111">В следующем примере рисуется дуга и заполняет внутреннюю часть эллипса соответствующей части:</span><span class="sxs-lookup"><span data-stu-id="a2acf-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="a2acf-112">Ниже показан дуги и заполненный круг.</span><span class="sxs-lookup"><span data-stu-id="a2acf-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="a2acf-113">![Замкнутые и незамкнутые кривые](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="a2acf-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="a2acf-114"><xref:System.Drawing.Graphics.FillClosedCurve%2A> Метод является дополнением к <xref:System.Drawing.Graphics.DrawClosedCurve%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a2acf-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="a2acf-115">Оба метода автоматически закрывать кривой, подключившись к начальной точке конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a2acf-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="a2acf-116">В следующем примере рисуется кривую, проходящих через (0, 0), (60, 20) и (40, 50).</span><span class="sxs-lookup"><span data-stu-id="a2acf-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="a2acf-117">Затем кривой автоматически закрывается, подключив (40, 50) до начальной точки (0, 0), а внутренняя область заполняется сплошным цветом.</span><span class="sxs-lookup"><span data-stu-id="a2acf-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="a2acf-118"><xref:System.Drawing.Graphics.FillPath%2A> Метод заполняет внутреннюю часть различных частей пути.</span><span class="sxs-lookup"><span data-stu-id="a2acf-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="a2acf-119">Если часть пути, не образует замкнутую кривую, <xref:System.Drawing.Graphics.FillPath%2A> метод автоматически закрывает этот самый кусок путь до его заполнения.</span><span class="sxs-lookup"><span data-stu-id="a2acf-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="a2acf-120">В следующем примере рисует и заполняет путь, который состоит из дуги, фундаментальный сплайн, строка и сектора:</span><span class="sxs-lookup"><span data-stu-id="a2acf-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="a2acf-121">Ниже показан путь с и без сплошной заливки.</span><span class="sxs-lookup"><span data-stu-id="a2acf-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="a2acf-122">Обратите внимание, что текст в строке контуров символов, но не заполнено, <xref:System.Drawing.Graphics.DrawPath%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a2acf-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="a2acf-123">Это <xref:System.Drawing.Graphics.FillPath%2A> метод закрашиваются символов в строке.</span><span class="sxs-lookup"><span data-stu-id="a2acf-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="a2acf-124">![Строка в пути](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="a2acf-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2acf-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a2acf-125">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="a2acf-126">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="a2acf-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a2acf-127">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="a2acf-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="a2acf-128">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="a2acf-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
