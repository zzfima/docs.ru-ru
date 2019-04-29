---
title: Сглаживание прямых и кривых линий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: cbc9033f18f1ab255862c8f8e2891aa9b68cf8d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961105"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="04886-102">Сглаживание прямых и кривых линий</span><span class="sxs-lookup"><span data-stu-id="04886-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="04886-103">При использовании [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Чтобы нарисовать линию, предоставляют начальную и конечную точку линии, но нет необходимости предоставлять данные об отдельных пикселях в строке.</span><span class="sxs-lookup"><span data-stu-id="04886-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="04886-104">работает в сочетании с программным обеспечением драйвера экрана, чтобы определить, какие точек будет включена для отображения в строке на устройстве отображения.</span><span class="sxs-lookup"><span data-stu-id="04886-104">works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="04886-105">Присвоение псевдонима</span><span class="sxs-lookup"><span data-stu-id="04886-105">Aliasing</span></span>  
 <span data-ttu-id="04886-106">Рассмотрите возможность непосредственно красная линия, идущий от точки (4, 2) в точку (16, 10).</span><span class="sxs-lookup"><span data-stu-id="04886-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="04886-107">Предположим, система координат расположен в левом верхнем углу и означает что единицы измерения пиксель.</span><span class="sxs-lookup"><span data-stu-id="04886-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="04886-108">Также предполагается, что ось x обращена вправо, а ось y точек вниз.</span><span class="sxs-lookup"><span data-stu-id="04886-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="04886-109">На следующем рисунке увеличенное изображение красной линии, рисуемой на многоцветном фоне.</span><span class="sxs-lookup"><span data-stu-id="04886-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="04886-110">![Строка, без сглаживания](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="04886-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="04886-111">Красные пиксели, используемый для отображения линии, непрозрачный.</span><span class="sxs-lookup"><span data-stu-id="04886-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="04886-112">В строке есть не частично прозрачных точек.</span><span class="sxs-lookup"><span data-stu-id="04886-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="04886-113">Этот тип отрисовки линии делает зубчатой и строке похож на лестница.</span><span class="sxs-lookup"><span data-stu-id="04886-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="04886-114">Этот метод представления линии называется Совмещение имен; лестница является псевдонимом для теоретической линии.</span><span class="sxs-lookup"><span data-stu-id="04886-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="04886-115">Сглаживание</span><span class="sxs-lookup"><span data-stu-id="04886-115">Antialiasing</span></span>  
 <span data-ttu-id="04886-116">Более сложный прием для подготовки к просмотру строки заключаются в использовании частично прозрачных точек вместе с непрозрачными.</span><span class="sxs-lookup"><span data-stu-id="04886-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="04886-117">Пиксели задаются чистый красный цвет, либо смешение красного и цвет фона, зависимости от того, насколько близко эти строки.</span><span class="sxs-lookup"><span data-stu-id="04886-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="04886-118">Этот тип визуализации называется сглаживания и результаты в строке, которая человеческим глазом они выглядели более smooth.</span><span class="sxs-lookup"><span data-stu-id="04886-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="04886-119">Ниже показано, как несколько точек смешиваются с цветом фона для образования сглаженной линии.</span><span class="sxs-lookup"><span data-stu-id="04886-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="04886-120">![Сглаживание прямой линии](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="04886-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="04886-121">Сглаживание, также называемый сглаживание, могут также применяться к кривым.</span><span class="sxs-lookup"><span data-stu-id="04886-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="04886-122">На следующем рисунке увеличенное изображение сглаженного эллипса.</span><span class="sxs-lookup"><span data-stu-id="04886-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="04886-123">![Сглаживание кривых](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="04886-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="04886-124">Ниже показан тот же эллипс в натуральную величину, без применения и один раз с помощью сглаживания.</span><span class="sxs-lookup"><span data-stu-id="04886-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="04886-125">![Пример сглаживания](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="04886-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="04886-126">Для рисования линий и кривых, использующих сглаживания, создайте экземпляр <xref:System.Drawing.Graphics> и присвоить его <xref:System.Drawing.Graphics.SmoothingMode%2A> свойства <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> или <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="04886-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="04886-127">Затем вызовите один из методов рисования этого же <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="04886-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="04886-128">См. также</span><span class="sxs-lookup"><span data-stu-id="04886-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="04886-129">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="04886-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="04886-130">Практическое руководство. Сглаживание текста</span><span class="sxs-lookup"><span data-stu-id="04886-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
