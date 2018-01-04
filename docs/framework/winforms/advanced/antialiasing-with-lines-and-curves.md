---
title: "Сглаживание прямых и кривых линий"
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
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8552f185a93b688555dbcfab3da9d28d9bfde6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="49519-102">Сглаживание прямых и кривых линий</span><span class="sxs-lookup"><span data-stu-id="49519-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="49519-103">При использовании [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для рисования линии, предоставляют начальную и конечную точки линии, но вам не требуется задать любые сведения об отдельных точках в строке.</span><span class="sxs-lookup"><span data-stu-id="49519-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="49519-104">работает в сочетании с программным обеспечением драйвера экрана, чтобы определить, какие точек будет включена для отображения в строке для каждого конкретного устройства отображения.</span><span class="sxs-lookup"><span data-stu-id="49519-104"> works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="49519-105">Совмещение имен</span><span class="sxs-lookup"><span data-stu-id="49519-105">Aliasing</span></span>  
 <span data-ttu-id="49519-106">Попробуйте прямо красная линия, идущий от точки (4, 2) в точку (16, 10).</span><span class="sxs-lookup"><span data-stu-id="49519-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="49519-107">Предположим системы координат расположен в верхнем левом углу, а единицей измерения является пикселя.</span><span class="sxs-lookup"><span data-stu-id="49519-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="49519-108">Также предположим, на который указывает ось x вправо, а ось y точки вниз.</span><span class="sxs-lookup"><span data-stu-id="49519-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="49519-109">Ниже показано увеличенное изображение красной линии, нарисованной на многоцветном фоне.</span><span class="sxs-lookup"><span data-stu-id="49519-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="49519-110">![Линия, без сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="49519-110">![Line, no antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="49519-111">Красные пиксели, составляющие линию, непрозрачны.</span><span class="sxs-lookup"><span data-stu-id="49519-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="49519-112">В строке нет отсутствуют частично прозрачные точки.</span><span class="sxs-lookup"><span data-stu-id="49519-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="49519-113">Этот тип отрисовки линии делает массивов оформление и строке похож на лестнице.</span><span class="sxs-lookup"><span data-stu-id="49519-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="49519-114">Этот метод представления линии называется Совмещение имен; лестнице является псевдонимом линия.</span><span class="sxs-lookup"><span data-stu-id="49519-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="49519-115">Сглаживание</span><span class="sxs-lookup"><span data-stu-id="49519-115">Antialiasing</span></span>  
 <span data-ttu-id="49519-116">Более сложные способы отрисовки прямых линий заключаются в использовании частично прозрачных точек наряду с непрозрачными.</span><span class="sxs-lookup"><span data-stu-id="49519-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="49519-117">Задается пикселей чисто красный цвет, либо смешение красного и цвет фона, в зависимости от того, насколько близко эти строки.</span><span class="sxs-lookup"><span data-stu-id="49519-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="49519-118">Этот тип визуализации называется сглаживания и результаты в строке, которая человеческого глаза они выглядели более гладкой.</span><span class="sxs-lookup"><span data-stu-id="49519-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="49519-119">Ниже показано, как несколько точек смешиваются с цветом фона для образования сглаженной линии.</span><span class="sxs-lookup"><span data-stu-id="49519-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="49519-120">![Сглаживание прямой линии](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="49519-120">![Antialiasing a Line](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="49519-121">Сглаживание, также называемый сглаживания, можно также применять для кривых.</span><span class="sxs-lookup"><span data-stu-id="49519-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="49519-122">На следующем рисунке увеличенное изображение сглаженного эллипса.</span><span class="sxs-lookup"><span data-stu-id="49519-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="49519-123">![Сглаживание кривых](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="49519-123">![Antialiasing Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="49519-124">Ниже показан тот же эллипс в натуральную величину, без сглаживания и один раз с помощью сглаживания.</span><span class="sxs-lookup"><span data-stu-id="49519-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="49519-125">![Пример сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="49519-125">![Antialiasing example](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="49519-126">Рисование линий и кривых с использованием сглаживания, создайте экземпляр <xref:System.Drawing.Graphics> и присвоить его <xref:System.Drawing.Graphics.SmoothingMode%2A> свойства <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> или <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="49519-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="49519-127">Затем вызовите один из методов рисования этого же <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="49519-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="49519-128">См. также</span><span class="sxs-lookup"><span data-stu-id="49519-128">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [<span data-ttu-id="49519-129">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="49519-129">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="49519-130">Практическое руководство. Сглаживание текста</span><span class="sxs-lookup"><span data-stu-id="49519-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
