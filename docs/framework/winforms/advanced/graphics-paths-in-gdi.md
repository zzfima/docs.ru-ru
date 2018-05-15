---
title: Контуры в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 66d30b949fbfe8190b9e2ae2ea7896ac36bf0bac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="06215-102">Контуры в GDI+</span><span class="sxs-lookup"><span data-stu-id="06215-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="06215-103">Пути сформированном путем объединения линии, прямоугольники и простейших кривых.</span><span class="sxs-lookup"><span data-stu-id="06215-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="06215-104">Вспомните из [Общие сведения о векторной графике](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) , основными строительными блоками доказали подходят для рисования изображений:</span><span class="sxs-lookup"><span data-stu-id="06215-104">Recall from the [Vector Graphics Overview](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="06215-105">Прямые линии</span><span class="sxs-lookup"><span data-stu-id="06215-105">Lines</span></span>  
  
-   <span data-ttu-id="06215-106">Прямоугольники</span><span class="sxs-lookup"><span data-stu-id="06215-106">Rectangles</span></span>  
  
-   <span data-ttu-id="06215-107">Многоточие</span><span class="sxs-lookup"><span data-stu-id="06215-107">Ellipses</span></span>  
  
-   <span data-ttu-id="06215-108">Дуги</span><span class="sxs-lookup"><span data-stu-id="06215-108">Arcs</span></span>  
  
-   <span data-ttu-id="06215-109">Многоугольники</span><span class="sxs-lookup"><span data-stu-id="06215-109">Polygons</span></span>  
  
-   <span data-ttu-id="06215-110">Фундаментальные сплайны</span><span class="sxs-lookup"><span data-stu-id="06215-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="06215-111">Сплайны Безье</span><span class="sxs-lookup"><span data-stu-id="06215-111">Bézier splines</span></span>  
  
 <span data-ttu-id="06215-112">В GDI + <xref:System.Drawing.Drawing2D.GraphicsPath> позволяет собирать последовательность таких блоков в одно целое.</span><span class="sxs-lookup"><span data-stu-id="06215-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="06215-113">Вся последовательность линии, прямоугольники, многоугольники и кривых может быть нарисована путем однократного вызова <xref:System.Drawing.Graphics.DrawPath%2A> метод <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="06215-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="06215-114">Ниже показан путь, созданный путем объединения линии, дуги, сплайна Безье и фундаментальный сплайн.</span><span class="sxs-lookup"><span data-stu-id="06215-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="06215-115">![Путь](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="06215-115">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="06215-116">С помощью пути</span><span class="sxs-lookup"><span data-stu-id="06215-116">Using a Path</span></span>  
 <span data-ttu-id="06215-117"><xref:System.Drawing.Drawing2D.GraphicsPath> Класс предоставляет следующие методы для создания последовательности элементов для отображения: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (для сплайны), и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="06215-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="06215-118">Каждый из этих методов перегружена; то есть каждый метод поддерживает несколько различными списками параметров.</span><span class="sxs-lookup"><span data-stu-id="06215-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="06215-119">Например, один из вариантов <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> метод получает четырех целых чисел, а другой вариант <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> метод получает два <xref:System.Drawing.Point> объектов.</span><span class="sxs-lookup"><span data-stu-id="06215-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="06215-120">Методы для добавления линии, прямоугольники и сплайнов Безье в пути имеют вспомогательные методы, выполняющие добавьте несколько элементов пути за один вызов: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="06215-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="06215-121">Кроме того <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> методы существуют вспомогательные методы <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, добавьте замкнутой кривой или круговой путь.</span><span class="sxs-lookup"><span data-stu-id="06215-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="06215-122">Чтобы нарисовать контур, нужно <xref:System.Drawing.Graphics> объекта, <xref:System.Drawing.Pen> объекта и <xref:System.Drawing.Drawing2D.GraphicsPath> объекта.</span><span class="sxs-lookup"><span data-stu-id="06215-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="06215-123"><xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.DrawPath%2A> метода и <xref:System.Drawing.Pen> объект хранит атрибуты, такие как ширина и цвет линии, используемой для подготовки к просмотру путь.</span><span class="sxs-lookup"><span data-stu-id="06215-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="06215-124"><xref:System.Drawing.Drawing2D.GraphicsPath> Объект хранит последовательности, линий и кривых линий, составляющих путь.</span><span class="sxs-lookup"><span data-stu-id="06215-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="06215-125"><xref:System.Drawing.Pen> Объекта и <xref:System.Drawing.Drawing2D.GraphicsPath> объекта передаются как аргументы для <xref:System.Drawing.Graphics.DrawPath%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="06215-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="06215-126">В следующем примере рисуется путь, состоящий из линии, эллипса и сплайна Безье:</span><span class="sxs-lookup"><span data-stu-id="06215-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="06215-127">Ниже показан путь.</span><span class="sxs-lookup"><span data-stu-id="06215-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="06215-128">![Путь](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="06215-128">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="06215-129">Помимо добавления линии, прямоугольники и кривых с путем, можно добавить пути в путь.</span><span class="sxs-lookup"><span data-stu-id="06215-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="06215-130">Это позволяет объединять существующие пути для формирования больших и сложных пути.</span><span class="sxs-lookup"><span data-stu-id="06215-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="06215-131">Существуют два элемента, можно добавить в путь: строку и сектор.</span><span class="sxs-lookup"><span data-stu-id="06215-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="06215-132">Сектор — часть внутреннюю часть эллипса.</span><span class="sxs-lookup"><span data-stu-id="06215-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="06215-133">В следующем примере создается путь от дуга, фундаментальный сплайн, строка и сектора:</span><span class="sxs-lookup"><span data-stu-id="06215-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="06215-134">Ниже показан путь.</span><span class="sxs-lookup"><span data-stu-id="06215-134">The following illustration shows the path.</span></span> <span data-ttu-id="06215-135">Обратите внимание, что путь не должен быть подключен; дуга, фундаментальный сплайн, строка и круговой разделены.</span><span class="sxs-lookup"><span data-stu-id="06215-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="06215-136">![Пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="06215-136">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06215-137">См. также</span><span class="sxs-lookup"><span data-stu-id="06215-137">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="06215-138">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="06215-138">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="06215-139">Практическое руководство. Создание графических объектов для рисования</span><span class="sxs-lookup"><span data-stu-id="06215-139">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="06215-140">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="06215-140">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
