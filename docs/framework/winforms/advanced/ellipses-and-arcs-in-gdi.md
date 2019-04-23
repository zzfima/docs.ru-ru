---
title: Эллипсы и дуги в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117460"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="2046b-102">Эллипсы и дуги в GDI+</span><span class="sxs-lookup"><span data-stu-id="2046b-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="2046b-103">Можно без труда нарисовать эллипсы и дуги с помощью <xref:System.Drawing.Graphics.DrawEllipse%2A> и <xref:System.Drawing.Graphics.DrawArc%2A> методы <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="2046b-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="2046b-104">Рисование эллипса</span><span class="sxs-lookup"><span data-stu-id="2046b-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="2046b-105">Чтобы нарисовать эллипс, вам потребуется <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="2046b-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="2046b-106"><xref:System.Drawing.Graphics> Предоставляет <xref:System.Drawing.Graphics.DrawEllipse%2A> метод и <xref:System.Drawing.Pen> объект сохраняет атрибуты, например, ширина и цвет линии, используемый для визуализации эллипса.</span><span class="sxs-lookup"><span data-stu-id="2046b-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="2046b-107"><xref:System.Drawing.Pen> Объект передается в качестве одного из аргументов <xref:System.Drawing.Graphics.DrawEllipse%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2046b-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="2046b-108">Остальные аргументы, передаваемые <xref:System.Drawing.Graphics.DrawEllipse%2A> указать метод прямоугольник, ограничивающий эллипс.</span><span class="sxs-lookup"><span data-stu-id="2046b-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="2046b-109">На следующем рисунке эллипс с ограничивающим его прямоугольником.</span><span class="sxs-lookup"><span data-stu-id="2046b-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="2046b-110">![Эллипсы и дуги](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="2046b-110">![Ellipses and arcs](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="2046b-111">В следующем примере рисуется эллипс; ограничивающий прямоугольник имеет ширину 80, в левом верхнем углу и высоты 40 (100, 50):</span><span class="sxs-lookup"><span data-stu-id="2046b-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="2046b-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> — перегруженный метод <xref:System.Drawing.Graphics> класса, поэтому существует несколько способов передачи аргументов.</span><span class="sxs-lookup"><span data-stu-id="2046b-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="2046b-113">Например, можно создать <xref:System.Drawing.Rectangle> и передать <xref:System.Drawing.Rectangle> для <xref:System.Drawing.Graphics.DrawEllipse%2A> метод в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="2046b-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="2046b-114">Рисование дуги</span><span class="sxs-lookup"><span data-stu-id="2046b-114">Drawing an Arc</span></span>  
 <span data-ttu-id="2046b-115">Дуга является частью эллипса.</span><span class="sxs-lookup"><span data-stu-id="2046b-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="2046b-116">Чтобы нарисовать дугу, вызовите <xref:System.Drawing.Graphics.DrawArc%2A> метод <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="2046b-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2046b-117">Параметры <xref:System.Drawing.Graphics.DrawArc%2A> метод такие же, как параметры <xref:System.Drawing.Graphics.DrawEllipse%2A> метода, за исключением случаев, <xref:System.Drawing.Graphics.DrawArc%2A> требует начального угла и угла поворота.</span><span class="sxs-lookup"><span data-stu-id="2046b-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="2046b-118">В следующем примере рисуется дуга с начальным углом 30 градусов и угол поворота, равный 180 градусов:</span><span class="sxs-lookup"><span data-stu-id="2046b-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="2046b-119">На следующем рисунке дуги, эллипс и ограничивающий прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="2046b-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="2046b-120">![Эллипсы и дуги](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="2046b-120">![Ellipses and arcs](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2046b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2046b-121">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="2046b-122">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="2046b-122">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="2046b-123">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="2046b-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="2046b-124">Практическое руководство. Создание пера</span><span class="sxs-lookup"><span data-stu-id="2046b-124">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="2046b-125">Практическое руководство. Рисование контурной фигуры</span><span class="sxs-lookup"><span data-stu-id="2046b-125">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
