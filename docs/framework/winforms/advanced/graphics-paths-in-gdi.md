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
ms.openlocfilehash: c9a43065210f5ef0fffcae01cc7eb88349696b6b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140508"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="0e776-102">Контуры в GDI+</span><span class="sxs-lookup"><span data-stu-id="0e776-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="0e776-103">Пути сформированном путем объединения линии, прямоугольники и простой кривых.</span><span class="sxs-lookup"><span data-stu-id="0e776-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="0e776-104">Как следует из [Общие сведения о векторной графики](vector-graphics-overview.md) что следующих основных блоков оказались наиболее подходят для рисования изображений:</span><span class="sxs-lookup"><span data-stu-id="0e776-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="0e776-105">Прямых линий</span><span class="sxs-lookup"><span data-stu-id="0e776-105">Lines</span></span>  
  
-   <span data-ttu-id="0e776-106">Прямоугольники</span><span class="sxs-lookup"><span data-stu-id="0e776-106">Rectangles</span></span>  
  
-   <span data-ttu-id="0e776-107">Многоточие</span><span class="sxs-lookup"><span data-stu-id="0e776-107">Ellipses</span></span>  
  
-   <span data-ttu-id="0e776-108">Дуги</span><span class="sxs-lookup"><span data-stu-id="0e776-108">Arcs</span></span>  
  
-   <span data-ttu-id="0e776-109">Многоугольники</span><span class="sxs-lookup"><span data-stu-id="0e776-109">Polygons</span></span>  
  
-   <span data-ttu-id="0e776-110">Фундаментальные сплайны</span><span class="sxs-lookup"><span data-stu-id="0e776-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="0e776-111">Сплайны Безье</span><span class="sxs-lookup"><span data-stu-id="0e776-111">Bézier splines</span></span>  
  
 <span data-ttu-id="0e776-112">В GDI + <xref:System.Drawing.Drawing2D.GraphicsPath> объект позволяет собирать последовательность из этих блоков в единое целое.</span><span class="sxs-lookup"><span data-stu-id="0e776-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="0e776-113">Вся последовательность линии, прямоугольники, многоугольники и кривых могут быть нарисована за одно обращение <xref:System.Drawing.Graphics.DrawPath%2A> метод <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="0e776-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="0e776-114">Ниже показан путь, полученное путем объединения строки, дуги, сплайна Безье и фундаментальный сплайн.</span><span class="sxs-lookup"><span data-stu-id="0e776-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="0e776-115">![Путь](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="0e776-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="0e776-116">С помощью пути</span><span class="sxs-lookup"><span data-stu-id="0e776-116">Using a Path</span></span>  
 <span data-ttu-id="0e776-117"><xref:System.Drawing.Drawing2D.GraphicsPath> Класс предоставляет следующие методы для создания последовательность элементов для отрисовки: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (для фундаментальные сплайны), и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="0e776-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="0e776-118">Каждый из этих методов перегружена; то есть каждый метод поддерживает несколько различными списками параметров.</span><span class="sxs-lookup"><span data-stu-id="0e776-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="0e776-119">Например, один из вариантов <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> метод получает четырех целых чисел, а в другом варианте <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> метод получает два <xref:System.Drawing.Point> объектов.</span><span class="sxs-lookup"><span data-stu-id="0e776-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="0e776-120">Методы для добавления линии, прямоугольники и сплайны Безье в пути имеют вспомогательные методы, выполняющие добавьте несколько элементов пути за один вызов: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, и <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="0e776-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="0e776-121">Кроме того <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> методы существуют вспомогательные методы <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, которые расширяют секции замкнутой кривой или круговой путь.</span><span class="sxs-lookup"><span data-stu-id="0e776-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="0e776-122">Чтобы нарисовать контур, вам потребуется <xref:System.Drawing.Graphics> объекта, <xref:System.Drawing.Pen> объекта и <xref:System.Drawing.Drawing2D.GraphicsPath> объекта.</span><span class="sxs-lookup"><span data-stu-id="0e776-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="0e776-123"><xref:System.Drawing.Graphics> Предоставляет <xref:System.Drawing.Graphics.DrawPath%2A> метод и <xref:System.Drawing.Pen> объект сохраняет атрибуты, например, ширина и цвет линии, используемый для визуализации путь.</span><span class="sxs-lookup"><span data-stu-id="0e776-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="0e776-124"><xref:System.Drawing.Drawing2D.GraphicsPath> Объект сохраняет последовательность линий и кривых линий, составляющих путь.</span><span class="sxs-lookup"><span data-stu-id="0e776-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="0e776-125"><xref:System.Drawing.Pen> Объекта и <xref:System.Drawing.Drawing2D.GraphicsPath> объекта передаются как аргументы для <xref:System.Drawing.Graphics.DrawPath%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="0e776-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="0e776-126">В следующем примере рисуется путь, который состоит из строки, эллипс и сплайн Безье:</span><span class="sxs-lookup"><span data-stu-id="0e776-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="0e776-127">На следующем рисунке путь.</span><span class="sxs-lookup"><span data-stu-id="0e776-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="0e776-128">![Путь](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="0e776-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="0e776-129">Помимо добавления линии, прямоугольники и кривые к пути, можно добавить пути к пути.</span><span class="sxs-lookup"><span data-stu-id="0e776-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="0e776-130">Это позволяет объединять существующие пути для формирования больших и сложных путей.</span><span class="sxs-lookup"><span data-stu-id="0e776-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="0e776-131">Два других элемента, можно добавить в путь: строку и сектор.</span><span class="sxs-lookup"><span data-stu-id="0e776-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="0e776-132">Сектор — часть внутреннюю часть эллипса.</span><span class="sxs-lookup"><span data-stu-id="0e776-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="0e776-133">В следующем примере создается путь из дуги, фундаментальный сплайн, строка и сектора:</span><span class="sxs-lookup"><span data-stu-id="0e776-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="0e776-134">На следующем рисунке путь.</span><span class="sxs-lookup"><span data-stu-id="0e776-134">The following illustration shows the path.</span></span> <span data-ttu-id="0e776-135">Обратите внимание, что путь не обязательно должен быть подключен; arc, фундаментальный сплайн, строка и круговой разделены.</span><span class="sxs-lookup"><span data-stu-id="0e776-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="0e776-136">![Пути](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="0e776-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e776-137">См. также</span><span class="sxs-lookup"><span data-stu-id="0e776-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="0e776-138">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="0e776-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="0e776-139">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="0e776-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="0e776-140">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="0e776-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
