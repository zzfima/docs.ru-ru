---
title: Перья, линии и прямоугольники в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: eb09d9a0df5ed3498e32e37bb5b23ff6c8744857
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523380"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="0c397-102">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="0c397-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="0c397-103">Чтобы нарисовать линии с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] необходимо создать <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="0c397-103">To draw lines with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="0c397-104"><xref:System.Drawing.Graphics> Объект предоставляет методы, которые фактически выполняют рисование, и <xref:System.Drawing.Pen> объект сохраняет атрибуты, такие как цвет, ширину и стиль.</span><span class="sxs-lookup"><span data-stu-id="0c397-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="0c397-105">Рисование линии</span><span class="sxs-lookup"><span data-stu-id="0c397-105">Drawing a Line</span></span>  
 <span data-ttu-id="0c397-106">Чтобы нарисовать линию, вызовите <xref:System.Drawing.Graphics.DrawLine%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="0c397-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="0c397-107"><xref:System.Drawing.Pen> Объект передается в качестве одного из аргументов <xref:System.Drawing.Graphics.DrawLine%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="0c397-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="0c397-108">В следующем примере рисуется линию из точки (4, 2) в точку ("12", "6"):</span><span class="sxs-lookup"><span data-stu-id="0c397-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="0c397-109"><xref:System.Drawing.Graphics.DrawLine%2A> — перегруженный метод <xref:System.Drawing.Graphics> класса, поэтому существует несколько способов передачи аргументов.</span><span class="sxs-lookup"><span data-stu-id="0c397-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="0c397-110">Например, можно создать два <xref:System.Drawing.Point> и передать <xref:System.Drawing.Point> объектов в качестве аргументов <xref:System.Drawing.Graphics.DrawLine%2A> метод:</span><span class="sxs-lookup"><span data-stu-id="0c397-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="0c397-111">Создание объекта Pen</span><span class="sxs-lookup"><span data-stu-id="0c397-111">Constructing a Pen</span></span>  
 <span data-ttu-id="0c397-112">Можно указать несколько атрибутов, при создании <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="0c397-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="0c397-113">Например, один `Pen` конструктор позволяет указать цвет и ширину.</span><span class="sxs-lookup"><span data-stu-id="0c397-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="0c397-114">В следующем примере рисуется синяя линия от ширины 2 от (0, 0) для (60, 30):</span><span class="sxs-lookup"><span data-stu-id="0c397-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="0c397-115">Пунктирные линии и завершения отрезков</span><span class="sxs-lookup"><span data-stu-id="0c397-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="0c397-116"><xref:System.Drawing.Pen> Объект также предоставляет свойства, такие как <xref:System.Drawing.Pen.DashStyle%2A>, можно использовать для указания свойства линии.</span><span class="sxs-lookup"><span data-stu-id="0c397-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="0c397-117">В следующем примере рисуется пунктирная линия с (100, 50) к (300, 80):</span><span class="sxs-lookup"><span data-stu-id="0c397-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="0c397-118">Можно использовать свойства <xref:System.Drawing.Pen> объекта можно задать многие атрибуты линии.</span><span class="sxs-lookup"><span data-stu-id="0c397-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="0c397-119"><xref:System.Drawing.Pen.StartCap%2A> И <xref:System.Drawing.Pen.EndCap%2A> свойства определяют внешний вид концах линии; может заканчиваться неструктурированный square, треугольником, или пользовательской фигуры.</span><span class="sxs-lookup"><span data-stu-id="0c397-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="0c397-120"><xref:System.Drawing.Pen.LineJoin%2A> Свойство позволяет указать ли соединенных линий углом (присоединение с острые углы), скошенные, округленное или обрезается.</span><span class="sxs-lookup"><span data-stu-id="0c397-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="0c397-121">Ниже показаны строки с использованием различных стилей завершения и соединения.</span><span class="sxs-lookup"><span data-stu-id="0c397-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="0c397-122">![Строки](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="0c397-122">![Lines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="0c397-123">Рисование прямоугольника</span><span class="sxs-lookup"><span data-stu-id="0c397-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="0c397-124">Рисование прямоугольников с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] похоже на рисование линий.</span><span class="sxs-lookup"><span data-stu-id="0c397-124">Drawing rectangles with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is similar to drawing lines.</span></span> <span data-ttu-id="0c397-125">Чтобы нарисовать прямоугольник, вам потребуется <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="0c397-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="0c397-126"><xref:System.Drawing.Graphics> Предоставляет <xref:System.Drawing.Graphics.DrawRectangle%2A> метод и <xref:System.Drawing.Pen> объект сохраняет атрибуты, такие как толщины и цвета.</span><span class="sxs-lookup"><span data-stu-id="0c397-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="0c397-127"><xref:System.Drawing.Pen> Объект передается в качестве одного из аргументов <xref:System.Drawing.Graphics.DrawRectangle%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="0c397-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="0c397-128">В следующем примере рисуется прямоугольник с его верхнего левого угла в (100, 50), ширины 80, а высота — 40:</span><span class="sxs-lookup"><span data-stu-id="0c397-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="0c397-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> — перегруженный метод <xref:System.Drawing.Graphics> класса, поэтому существует несколько способов передачи аргументов.</span><span class="sxs-lookup"><span data-stu-id="0c397-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="0c397-130">Например, можно создать <xref:System.Drawing.Rectangle> и передать <xref:System.Drawing.Rectangle> объект <xref:System.Drawing.Graphics.DrawRectangle%2A> метод в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="0c397-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="0c397-131">Объект <xref:System.Drawing.Rectangle> содержит методы и свойства для обработки и сбора сведений о прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="0c397-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="0c397-132">Например <xref:System.Drawing.Rectangle.Inflate%2A> и <xref:System.Drawing.Rectangle.Offset%2A> методы изменять размер и положение прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="0c397-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="0c397-133"><xref:System.Drawing.Rectangle.IntersectsWith%2A> Метод указывает, является ли прямоугольник пересекается с другим указанным прямоугольником и <xref:System.Drawing.Rectangle.Contains%2A> метод указывает, является ли заданная точка находится внутри прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="0c397-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c397-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0c397-134">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="0c397-135">Практическое руководство. Создание пера</span><span class="sxs-lookup"><span data-stu-id="0c397-135">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [<span data-ttu-id="0c397-136">Практическое руководство. Нарисовать линию в форме Windows</span><span class="sxs-lookup"><span data-stu-id="0c397-136">How to: Draw a Line on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="0c397-137">Практическое руководство. Рисование контурной фигуры</span><span class="sxs-lookup"><span data-stu-id="0c397-137">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
