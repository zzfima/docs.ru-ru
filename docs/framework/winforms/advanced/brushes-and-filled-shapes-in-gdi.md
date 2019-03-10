---
title: Кисти и закрашенные фигуры в GDI+
ms.date: 03/30/2017
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
ms.openlocfilehash: fc6d6857e912ba14fca382eb49373655004534d5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720947"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="63170-102">Кисти и закрашенные фигуры в GDI+</span><span class="sxs-lookup"><span data-stu-id="63170-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="63170-103">Замкнутые фигуры, например прямоугольник или эллипс, состоит из структуры и внутренней частью.</span><span class="sxs-lookup"><span data-stu-id="63170-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="63170-104">Контур рисуется с помощью пера и внутренняя область заполняется с помощью кисти.</span><span class="sxs-lookup"><span data-stu-id="63170-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="63170-105">предоставляет несколько классов кисти для заливки фигур, закрытых: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, и <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="63170-105">provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="63170-106">Все эти классы наследуют <xref:System.Drawing.Brush> класса.</span><span class="sxs-lookup"><span data-stu-id="63170-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="63170-107">Ниже показан прямоугольник заполняется сплошной кистью и эллипс, заполненный кистей штриховки.</span><span class="sxs-lookup"><span data-stu-id="63170-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="63170-108">![Заполнить фигур](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="63170-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="63170-109">Сплошные кисти</span><span class="sxs-lookup"><span data-stu-id="63170-109">Solid Brushes</span></span>  
 <span data-ttu-id="63170-110">Для заполнения замкнутой фигуры, требуется экземпляр <xref:System.Drawing.Graphics> класс и <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="63170-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="63170-111">Экземпляр <xref:System.Drawing.Graphics> класс предоставляет методы, такие как <xref:System.Drawing.Graphics.FillRectangle%2A> и <xref:System.Drawing.Graphics.FillEllipse%2A>и <xref:System.Drawing.Brush> сохраняет атрибуты заливки, таких как цвет и шаблон.</span><span class="sxs-lookup"><span data-stu-id="63170-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="63170-112"><xref:System.Drawing.Brush> Передается в качестве одного из аргументов метода fill.</span><span class="sxs-lookup"><span data-stu-id="63170-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="63170-113">В следующем примере кода показано, как заливка эллипса сплошным красным цветом.</span><span class="sxs-lookup"><span data-stu-id="63170-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="63170-114">В приведенном выше примере кисть, которая имеет тип <xref:System.Drawing.SolidBrush>, который наследует от <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="63170-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="63170-115">Кистей штриховки</span><span class="sxs-lookup"><span data-stu-id="63170-115">Hatch Brushes</span></span>  
 <span data-ttu-id="63170-116">При заполнении формы штриховой кистью задаются цвет переднего плана, цветом фона и стиль штриховки.</span><span class="sxs-lookup"><span data-stu-id="63170-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="63170-117">Цвет переднего плана — это цвет штриховки.</span><span class="sxs-lookup"><span data-stu-id="63170-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="63170-118">предоставляет более чем 50 стилей штриховки. на следующем рисунке показано три стили представляют собой <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, и <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="63170-118">provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="63170-119">![Заполнить фигур](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="63170-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="63170-120">Текстурные кисти</span><span class="sxs-lookup"><span data-stu-id="63170-120">Texture Brushes</span></span>  
 <span data-ttu-id="63170-121">С помощью кисти текстуры вы можете заполнить фигуры с шаблоном, хранящиеся в точечном рисунке.</span><span class="sxs-lookup"><span data-stu-id="63170-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="63170-122">Предположим, например, приведенный ниже рисунок хранится на диске в файле с именем `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="63170-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="63170-123">![Заполнить форму](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="63170-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="63170-124">В следующем примере кода показано, как заливка эллипса, повторив рисунка, сохраненного в `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="63170-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="63170-125">На следующем рисунке заполненного эллипса.</span><span class="sxs-lookup"><span data-stu-id="63170-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="63170-126">![Заполнить форму](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="63170-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="63170-127">Градиентные кисти</span><span class="sxs-lookup"><span data-stu-id="63170-127">Gradient Brushes</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="63170-128">предоставляет два типа градиентных кистей: линейный и путь.</span><span class="sxs-lookup"><span data-stu-id="63170-128">provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="63170-129">Кисти линейного градиента можно использовать для заливки фигуры цвет, который постепенно через фигуры по горизонтали, вертикали или по диагонали.</span><span class="sxs-lookup"><span data-stu-id="63170-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="63170-130">В следующем примере кода показано, как заливка эллипса с горизонтальной градиентную кисть, которая поменяет цвет с синего на зеленый, при переходе от левого края эллипса по правому краю.</span><span class="sxs-lookup"><span data-stu-id="63170-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="63170-131">На следующем рисунке заполненного эллипса.</span><span class="sxs-lookup"><span data-stu-id="63170-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="63170-132">![Заполнить форму](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="63170-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="63170-133">Чтобы изменить цвет, при перемещении в центре фигуры к границе можно настроить кисти градиента контура.</span><span class="sxs-lookup"><span data-stu-id="63170-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="63170-134">![Заполнить форму](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="63170-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="63170-135">Градиентные кисти путь отличаются достаточной гибкостью.</span><span class="sxs-lookup"><span data-stu-id="63170-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="63170-136">Кисти градиента, используемый для заполнения в приведенном ниже рисунке последовательно от красного в центре для каждого из трех различных цветов в вершины треугольника.</span><span class="sxs-lookup"><span data-stu-id="63170-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="63170-137">![Заполнить форму](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="63170-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63170-138">См. также</span><span class="sxs-lookup"><span data-stu-id="63170-138">See also</span></span>
- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="63170-139">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="63170-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="63170-140">Практическое руководство. Нарисовать закрашенный прямоугольник в форме Windows</span><span class="sxs-lookup"><span data-stu-id="63170-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="63170-141">Практическое руководство. Рисование заполненного эллипса в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63170-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
