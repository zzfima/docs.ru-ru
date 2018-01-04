---
title: "Кисти и закрашенные фигуры в GDI+"
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
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89f0a7c86a83222030d9b50e20228f32e85ce730
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="0b320-102">Кисти и закрашенные фигуры в GDI+</span><span class="sxs-lookup"><span data-stu-id="0b320-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="0b320-103">Замкнутые фигуры, например прямоугольник или эллипса, состоит из структуры и внутренний.</span><span class="sxs-lookup"><span data-stu-id="0b320-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="0b320-104">Контур рисуется с помощью пера и внутренняя область заполняется с использованием кисти.</span><span class="sxs-lookup"><span data-stu-id="0b320-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="0b320-105">предоставляет несколько классов кисти для заливки замкнутых фигур: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, и <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="0b320-105"> provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="0b320-106">Эти классы наследуются от <xref:System.Drawing.Brush> класса.</span><span class="sxs-lookup"><span data-stu-id="0b320-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="0b320-107">На следующем рисунке прямоугольник с помощью сплошной кисти эллипса заливке а кистей штриховки.</span><span class="sxs-lookup"><span data-stu-id="0b320-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="0b320-108">![Заполнить фигуры](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="0b320-108">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="0b320-109">Сплошной кисти</span><span class="sxs-lookup"><span data-stu-id="0b320-109">Solid Brushes</span></span>  
 <span data-ttu-id="0b320-110">Чтобы залить замкнутую фигуру, требуется экземпляр <xref:System.Drawing.Graphics> класса и <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="0b320-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="0b320-111">Экземпляр <xref:System.Drawing.Graphics> класс предоставляет методы, такие как <xref:System.Drawing.Graphics.FillRectangle%2A> и <xref:System.Drawing.Graphics.FillEllipse%2A>и <xref:System.Drawing.Brush> для хранения атрибутов, таких как цвета или узора заливки.</span><span class="sxs-lookup"><span data-stu-id="0b320-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="0b320-112"><xref:System.Drawing.Brush> Передается в качестве одного из аргументов метода fill.</span><span class="sxs-lookup"><span data-stu-id="0b320-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="0b320-113">В следующем примере кода показано, как заливка эллипса сплошным красным цветом.</span><span class="sxs-lookup"><span data-stu-id="0b320-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="0b320-114">В приведенном выше примере кисть, которая принадлежит к типу <xref:System.Drawing.SolidBrush>, который наследует от <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="0b320-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="0b320-115">Кистей штриховки</span><span class="sxs-lookup"><span data-stu-id="0b320-115">Hatch Brushes</span></span>  
 <span data-ttu-id="0b320-116">При заливке формы штриховой кистью указываются основной цвет, цвет фона и стиль штриховки.</span><span class="sxs-lookup"><span data-stu-id="0b320-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="0b320-117">Цвет переднего плана — это цвет штриховки.</span><span class="sxs-lookup"><span data-stu-id="0b320-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="0b320-118">предоставляет более 50 стилей штриховки. на следующем рисунке изображены три стиля, <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, и <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="0b320-118"> provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="0b320-119">![Заполнить фигуры](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="0b320-119">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="0b320-120">Текстурные кисти</span><span class="sxs-lookup"><span data-stu-id="0b320-120">Texture Brushes</span></span>  
 <span data-ttu-id="0b320-121">С помощью кисти текстуры можно заливка фигуры с шаблоном, хранящихся в растровое изображение.</span><span class="sxs-lookup"><span data-stu-id="0b320-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="0b320-122">Предположим, например, приведенный ниже рисунок хранится на диске в файле с именем `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="0b320-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="0b320-123">![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="0b320-123">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="0b320-124">В следующем примере кода показано, как заливка эллипса, повторив рисунка, сохраненного в `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="0b320-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="0b320-125">На следующем рисунке закрашенный эллипс.</span><span class="sxs-lookup"><span data-stu-id="0b320-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="0b320-126">![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="0b320-126">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="0b320-127">Градиентные кисти</span><span class="sxs-lookup"><span data-stu-id="0b320-127">Gradient Brushes</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="0b320-128">имеется два типа градиентных кистей: линейный и путь.</span><span class="sxs-lookup"><span data-stu-id="0b320-128"> provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="0b320-129">Можно использовать линейной градиентной кисти для заливки фигуры цвет, который постепенно перемещении фигуры по горизонтали, по вертикали или по диагонали.</span><span class="sxs-lookup"><span data-stu-id="0b320-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="0b320-130">В следующем примере кода показано, как заливка эллипса с использованием горизонтальной градиентной кисти, изменение от синего до зеленого при переходе от левого края эллипса по правому краю.</span><span class="sxs-lookup"><span data-stu-id="0b320-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="0b320-131">На следующем рисунке закрашенный эллипс.</span><span class="sxs-lookup"><span data-stu-id="0b320-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="0b320-132">![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="0b320-132">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="0b320-133">Кисти градиента вдоль пути можно настроить для изменения цвета при переходе от центра фигуры к ее границам.</span><span class="sxs-lookup"><span data-stu-id="0b320-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="0b320-134">![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="0b320-134">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="0b320-135">Градиентные кисти пути обеспечивают высокую степень гибкости.</span><span class="sxs-lookup"><span data-stu-id="0b320-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="0b320-136">Демонстрируется использование градиентной кисти для заливки треугольника в приведенном ниже рисунке, изменяющимся от красного в центре для каждого из трех различных цветов в вершинах.</span><span class="sxs-lookup"><span data-stu-id="0b320-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="0b320-137">![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="0b320-137">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b320-138">См. также</span><span class="sxs-lookup"><span data-stu-id="0b320-138">See Also</span></span>  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [<span data-ttu-id="0b320-139">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="0b320-139">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="0b320-140">Практическое руководство. Рисование заполненного прямоугольника в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b320-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [<span data-ttu-id="0b320-141">Практическое руководство. Рисование заполненного эллипса в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b320-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
