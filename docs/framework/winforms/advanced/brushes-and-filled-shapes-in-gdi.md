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
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912234"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="a8f92-102">Кисти и закрашенные фигуры в GDI+</span><span class="sxs-lookup"><span data-stu-id="a8f92-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="a8f92-103">Замкнутая фигура, например прямоугольник или эллипс, состоит из контура и внутренней части.</span><span class="sxs-lookup"><span data-stu-id="a8f92-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="a8f92-104">Контур рисуется с помощью пера, а внутренняя часть заполняется кистью.</span><span class="sxs-lookup"><span data-stu-id="a8f92-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> <span data-ttu-id="a8f92-105">Интерфейс GDI+ предоставляет несколько классов кистей для заполнения внутренних областей замкнутых <xref:System.Drawing.SolidBrush>фигур <xref:System.Drawing.Drawing2D.HatchBrush>: <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>,, <xref:System.Drawing.Drawing2D.PathGradientBrush>и.</span><span class="sxs-lookup"><span data-stu-id="a8f92-105">GDI+ provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="a8f92-106">Все эти классы наследуются от <xref:System.Drawing.Brush> класса.</span><span class="sxs-lookup"><span data-stu-id="a8f92-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="a8f92-107">На следующем рисунке показан прямоугольник, заполненный сплошной кистью, и эллипс, заполненный штриховым кистью.</span><span class="sxs-lookup"><span data-stu-id="a8f92-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="a8f92-108">![Заполненные фигуры](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="a8f92-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="a8f92-109">Сплошные кисти</span><span class="sxs-lookup"><span data-stu-id="a8f92-109">Solid Brushes</span></span>  
 <span data-ttu-id="a8f92-110">Для заполнения замкнутой фигуры необходим экземпляр <xref:System.Drawing.Graphics> класса <xref:System.Drawing.Brush>и.</span><span class="sxs-lookup"><span data-stu-id="a8f92-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="a8f92-111">Экземпляр <xref:System.Drawing.Graphics> класса предоставляет методы, такие как <xref:System.Drawing.Graphics.FillRectangle%2A> и <xref:System.Drawing.Graphics.FillEllipse%2A>, и <xref:System.Drawing.Brush> сохраняет атрибуты заливки, такие как цвет и шаблон.</span><span class="sxs-lookup"><span data-stu-id="a8f92-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="a8f92-112"><xref:System.Drawing.Brush> Передается в качестве одного из аргументов метода Fill.</span><span class="sxs-lookup"><span data-stu-id="a8f92-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="a8f92-113">В следующем примере кода показано, как заполнить эллипс с помощью сплошного красного цвета.</span><span class="sxs-lookup"><span data-stu-id="a8f92-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> <span data-ttu-id="a8f92-114">В предыдущем примере кисть имеет тип <xref:System.Drawing.SolidBrush>, который наследует от. <xref:System.Drawing.Brush></span><span class="sxs-lookup"><span data-stu-id="a8f92-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="a8f92-115">Штриховые кисти</span><span class="sxs-lookup"><span data-stu-id="a8f92-115">Hatch Brushes</span></span>  
 <span data-ttu-id="a8f92-116">При заполнении фигуры штриховой кистью необходимо указать цвет переднего плана, цвет фона и стиль штриховки.</span><span class="sxs-lookup"><span data-stu-id="a8f92-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="a8f92-117">Цвет переднего плана — это цвет штриховки.</span><span class="sxs-lookup"><span data-stu-id="a8f92-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 <span data-ttu-id="a8f92-118">Интерфейс GDI+ предоставляет более 50 стилей штриховки; на следующем рисунке показаны три стиля: <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>и <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span><span class="sxs-lookup"><span data-stu-id="a8f92-118">GDI+ provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="a8f92-119">![Заполненные фигуры](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="a8f92-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="a8f92-120">Текстурные кисти</span><span class="sxs-lookup"><span data-stu-id="a8f92-120">Texture Brushes</span></span>  
 <span data-ttu-id="a8f92-121">Текстурная кисть позволяет заполнить фигуру шаблоном, хранящимся в растровом изображении.</span><span class="sxs-lookup"><span data-stu-id="a8f92-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="a8f92-122">Например, предположим, что следующий рисунок хранится в файле на диске с именем `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="a8f92-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="a8f92-123">![Заполненная фигура](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="a8f92-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="a8f92-124">В следующем примере кода показано, как заполнить эллипс путем повторения изображения, хранящегося в `MyTexture.bmp`.</span><span class="sxs-lookup"><span data-stu-id="a8f92-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="a8f92-125">На следующем рисунке показан закрашенный эллипс.</span><span class="sxs-lookup"><span data-stu-id="a8f92-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="a8f92-126">![Заполненная фигура](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="a8f92-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="a8f92-127">Градиентные кисти</span><span class="sxs-lookup"><span data-stu-id="a8f92-127">Gradient Brushes</span></span>  
 <span data-ttu-id="a8f92-128">GDI+ предоставляет два вида градиентных кистей: линейную и траекторию.</span><span class="sxs-lookup"><span data-stu-id="a8f92-128">GDI+ provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="a8f92-129">Кисть линейного градиента можно использовать для заливки фигуры цветом, который постепенно меняется при перемещении по горизонтали, по вертикали или по диагонали.</span><span class="sxs-lookup"><span data-stu-id="a8f92-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="a8f92-130">В следующем примере кода показано, как заполнить эллипс с помощью горизонтальной градиентной кисти, которая меняется с синего на зеленую при переходе от левого края эллипса к правому краю.</span><span class="sxs-lookup"><span data-stu-id="a8f92-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="a8f92-131">На следующем рисунке показан закрашенный эллипс.</span><span class="sxs-lookup"><span data-stu-id="a8f92-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="a8f92-132">![Заполненная фигура](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="a8f92-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="a8f92-133">Кисть градиента контура может быть настроена на изменение цвета при перемещении от центра фигуры к границе.</span><span class="sxs-lookup"><span data-stu-id="a8f92-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="a8f92-134">![Заполненная фигура](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="a8f92-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="a8f92-135">Кисти градиента вдоль пути являются достаточно гибкими.</span><span class="sxs-lookup"><span data-stu-id="a8f92-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="a8f92-136">Градиентная кисть, используемая для заливки треугольника на следующем рисунке, постепенно меняется от красного в центре к каждому из трех различных цветов в вершинах.</span><span class="sxs-lookup"><span data-stu-id="a8f92-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="a8f92-137">![Заполненная фигура](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="a8f92-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f92-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a8f92-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="a8f92-139">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="a8f92-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a8f92-140">Практическое руководство. Нарисовать закрашенный прямоугольник в форме Windows</span><span class="sxs-lookup"><span data-stu-id="a8f92-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="a8f92-141">Практическое руководство. Нарисовать закрашенный эллипс в форме Windows</span><span class="sxs-lookup"><span data-stu-id="a8f92-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
