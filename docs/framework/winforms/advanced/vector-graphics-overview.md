---
title: "Общие сведения о векторной графике"
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
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7bb3247f531a0dac83657e118fb53ebaf708ec9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="5cabe-102">Общие сведения о векторной графике</span><span class="sxs-lookup"><span data-stu-id="5cabe-102">Vector Graphics Overview</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5cabe-103">Рисование линии, прямоугольники и других фигур в системе координат.</span><span class="sxs-lookup"><span data-stu-id="5cabe-103"> draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="5cabe-104">Можно выбрать из различных систем координат, но система координат по умолчанию имеет начала координат в левом верхнем углу ось x вправо, а ось y направлена вниз.</span><span class="sxs-lookup"><span data-stu-id="5cabe-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="5cabe-105">Единица измерения, в системе координат по умолчанию является пиксель.</span><span class="sxs-lookup"><span data-stu-id="5cabe-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="5cabe-106">Стандартные блоки GDI +</span><span class="sxs-lookup"><span data-stu-id="5cabe-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="5cabe-107">![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="5cabe-107">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="5cabe-108">Изображение на прямоугольный массив точек, называемых элементами изображения формируется мониторе компьютера.</span><span class="sxs-lookup"><span data-stu-id="5cabe-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="5cabe-109">Количество пикселей, которые отображаются на экране, зависит от одного монитора к следующему и количество пикселей, которые отображаются на отдельных монитор обычно следует задавать в некоторой степени пользователем.</span><span class="sxs-lookup"><span data-stu-id="5cabe-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="5cabe-110">![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="5cabe-110">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="5cabe-111">При использовании [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для рисования линии, прямоугольника или кривой, предоставляют определенные ключевые данные об элементе для отрисовки.</span><span class="sxs-lookup"><span data-stu-id="5cabe-111">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="5cabe-112">Например можно указать строку, предоставляя две точки и прямоугольника можно указать, предоставляя точку, высотой и шириной.</span><span class="sxs-lookup"><span data-stu-id="5cabe-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5cabe-113">работает в сочетании с программным обеспечением драйвера экрана, чтобы определить, какие точек должен быть включен для отображения линии, прямоугольника или кривой.</span><span class="sxs-lookup"><span data-stu-id="5cabe-113"> works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="5cabe-114">На следующем рисунке пиксели, которые включены для отображения линии с точки (4, 2) в точку ("12", "8").</span><span class="sxs-lookup"><span data-stu-id="5cabe-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="5cabe-115">![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="5cabe-115">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="5cabe-116">Со временем некоторые основные стандартные блоки оказались наиболее полезен при создании двухмерных изображений.</span><span class="sxs-lookup"><span data-stu-id="5cabe-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="5cabe-117">Эти блоки, которые поддерживаются системой [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], приведены в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="5cabe-117">These building blocks, which are all supported by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], are given in the following list:</span></span>  
  
-   <span data-ttu-id="5cabe-118">Прямые линии</span><span class="sxs-lookup"><span data-stu-id="5cabe-118">Lines</span></span>  
  
-   <span data-ttu-id="5cabe-119">Прямоугольники</span><span class="sxs-lookup"><span data-stu-id="5cabe-119">Rectangles</span></span>  
  
-   <span data-ttu-id="5cabe-120">Многоточие</span><span class="sxs-lookup"><span data-stu-id="5cabe-120">Ellipses</span></span>  
  
-   <span data-ttu-id="5cabe-121">Дуги</span><span class="sxs-lookup"><span data-stu-id="5cabe-121">Arcs</span></span>  
  
-   <span data-ttu-id="5cabe-122">Многоугольники</span><span class="sxs-lookup"><span data-stu-id="5cabe-122">Polygons</span></span>  
  
-   <span data-ttu-id="5cabe-123">Фундаментальные сплайны</span><span class="sxs-lookup"><span data-stu-id="5cabe-123">Cardinal splines</span></span>  
  
-   <span data-ttu-id="5cabe-124">сплайны Безье</span><span class="sxs-lookup"><span data-stu-id="5cabe-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="5cabe-125">Методы для рисования с помощью графических объектов</span><span class="sxs-lookup"><span data-stu-id="5cabe-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="5cabe-126"><xref:System.Drawing.Graphics> Класса в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет следующие методы для рисования элементов в списке выше: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (для фундаментальные сплайны) и <xref:System.Drawing.Graphics.DrawBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="5cabe-126">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="5cabe-127">Каждый из этих методов перегружена; то есть каждый метод поддерживает несколько различными списками параметров.</span><span class="sxs-lookup"><span data-stu-id="5cabe-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="5cabe-128">Например, один из вариантов <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> объекта и четырех целых чисел, а другой вариант <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> и два <xref:System.Drawing.Point> объектов.</span><span class="sxs-lookup"><span data-stu-id="5cabe-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="5cabe-129">Методы для рисования линии, прямоугольники и сплайнов Безье существуют вспомогательные методы, выполняющие рисование нескольких элементов за один вызов: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, и <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="5cabe-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="5cabe-130">Кроме того <xref:System.Drawing.Graphics.DrawCurve%2A> метод имеет вспомогательный метод, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, что указывают закрывает кривую путем соединения с первой конечной точки кривой.</span><span class="sxs-lookup"><span data-stu-id="5cabe-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="5cabe-131">Все методы для рисования <xref:System.Drawing.Graphics> класса работы в сочетании с <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="5cabe-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5cabe-132">Чтобы нарисовать любой элемент, необходимо создать по крайней мере два объекта: <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="5cabe-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5cabe-133"><xref:System.Drawing.Pen> Объект хранит атрибуты, такие как толщины и цвета для отображения элемента.</span><span class="sxs-lookup"><span data-stu-id="5cabe-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="5cabe-134"><xref:System.Drawing.Pen> Объекта передается в качестве одного из аргументов метод рисования.</span><span class="sxs-lookup"><span data-stu-id="5cabe-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="5cabe-135">Например, один из вариантов <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> объекта и четырех целых чисел, как показано в следующем примере рисование прямоугольника с шириной 100, высотой 50 и координатами верхнего левого угла (20, 10):</span><span class="sxs-lookup"><span data-stu-id="5cabe-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="5cabe-136">См. также</span><span class="sxs-lookup"><span data-stu-id="5cabe-136">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="5cabe-137">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="5cabe-137">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="5cabe-138">Практическое руководство. Создание графических объектов для рисования</span><span class="sxs-lookup"><span data-stu-id="5cabe-138">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
