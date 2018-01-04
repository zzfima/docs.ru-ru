---
title: "Практическое руководство. Создание линейного градиента"
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
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33979decf37e9adb29d94a6602a43f992d93aaa1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="dab18-102">Практическое руководство. Создание линейного градиента</span><span class="sxs-lookup"><span data-stu-id="dab18-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="dab18-103">поддерживает горизонтальные, вертикальные и диагональные линейные градиенты.</span><span class="sxs-lookup"><span data-stu-id="dab18-103"> provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="dab18-104">По умолчанию цвет в линейном градиенте меняется равномерно.</span><span class="sxs-lookup"><span data-stu-id="dab18-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="dab18-105">Тем не менее можно настроить линейный градиент, чтобы цвет изменяется таким образом неоднородной.</span><span class="sxs-lookup"><span data-stu-id="dab18-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="dab18-106">В следующем примере заполняется линии, эллипса и прямоугольника с горизонтальной кисти линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="dab18-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="dab18-107"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Конструктор принимает четыре параметра: две точки и два цвета.</span><span class="sxs-lookup"><span data-stu-id="dab18-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="dab18-108">Первая точка (0, 10) связан с первый цвет (красный), а вторая точка (200, 10) связан со вторым цветом (синий).</span><span class="sxs-lookup"><span data-stu-id="dab18-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="dab18-109">Как и следовало ожидать, линии, соединяющей (0, 10) для (200, 10) плавно меняется от красного, синего.</span><span class="sxs-lookup"><span data-stu-id="dab18-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="dab18-110">Вторые точек (50, 10) и (200, 10) не имеют значения.</span><span class="sxs-lookup"><span data-stu-id="dab18-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="dab18-111">Важно то, что две точки имеют одну координату второй — линию, соединяющую их горизонтальной.</span><span class="sxs-lookup"><span data-stu-id="dab18-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="dab18-112">Эллипса и прямоугольника тоже плавно меняются от красного, синего как горизонтальной оси находятся значения от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="dab18-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="dab18-113">На следующем рисунке линии, эллипса и прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="dab18-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="dab18-114">Обратите внимание, что цветового градиента повторяется заново при увеличении горизонтальной координаты за пределы 200.</span><span class="sxs-lookup"><span data-stu-id="dab18-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="dab18-115">![Линейный градиент](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="dab18-115">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="dab18-116">Использование горизонтальных линейных градиентов</span><span class="sxs-lookup"><span data-stu-id="dab18-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="dab18-117">Передайте непрозрачный красный и непрозрачный синим цветом в качестве третьего и четвертого аргумента соответственно.</span><span class="sxs-lookup"><span data-stu-id="dab18-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="dab18-118">В предыдущем примере цветовые компоненты линейно меняются при перемещении из горизонтальная координата 0 горизонтальная координата 200.</span><span class="sxs-lookup"><span data-stu-id="dab18-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="dab18-119">Например точки, первая координата на равном расстоянии от 0 до 200 будет синего компонента, который находится на равном расстоянии от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="dab18-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="dab18-120">позволяет настроить способ цвета при движении от одного края градиент в другой.</span><span class="sxs-lookup"><span data-stu-id="dab18-120"> allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="dab18-121">Предположим, что вы хотите создать градиентной кисти, меняется с черный цвет на красный согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="dab18-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="dab18-122">Горизонтальная координата</span><span class="sxs-lookup"><span data-stu-id="dab18-122">Horizontal coordinate</span></span>|<span data-ttu-id="dab18-123">RGB-компоненты</span><span class="sxs-lookup"><span data-stu-id="dab18-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="dab18-124">0</span><span class="sxs-lookup"><span data-stu-id="dab18-124">0</span></span>|<span data-ttu-id="dab18-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="dab18-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="dab18-126">40</span><span class="sxs-lookup"><span data-stu-id="dab18-126">40</span></span>|<span data-ttu-id="dab18-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="dab18-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="dab18-128">200</span><span class="sxs-lookup"><span data-stu-id="dab18-128">200</span></span>|<span data-ttu-id="dab18-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="dab18-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="dab18-130">Обратите внимание, что красный компонент половину интенсивность когда горизонтальная координата составляет только 20 процентов пути от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="dab18-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="dab18-131">В следующем примере задается <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> свойство <xref:System.Drawing.Drawing2D.LinearGradientBrush> объект, связанный с тремя относительные позиции три относительный интенсивности.</span><span class="sxs-lookup"><span data-stu-id="dab18-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="dab18-132">Как показано в предыдущей таблице относительная интенсивность 0,5 связан с относительной позиции 0,2.</span><span class="sxs-lookup"><span data-stu-id="dab18-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="dab18-133">В коде осуществляется заливка эллипса и прямоугольника с градиентной кисти.</span><span class="sxs-lookup"><span data-stu-id="dab18-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="dab18-134">На следующем рисунке окончательный вид эллипса и прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="dab18-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="dab18-135">![Линейный градиент](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="dab18-135">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="dab18-136">Настройка линейных градиентов</span><span class="sxs-lookup"><span data-stu-id="dab18-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="dab18-137">Передайте непрозрачный черный и непрозрачный красным цветом в качестве третьего и четвертого аргумента соответственно.</span><span class="sxs-lookup"><span data-stu-id="dab18-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="dab18-138">В предыдущих примерах градиенты являлись горизонтальными; то есть цвет плавно меняется при движении вдоль любой горизонтальной линии.</span><span class="sxs-lookup"><span data-stu-id="dab18-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="dab18-139">Можно также определить вертикальные и диагональные градиенты.</span><span class="sxs-lookup"><span data-stu-id="dab18-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="dab18-140">В следующем примере передается точки (0, 0) и (200, 100), чтобы <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="dab18-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="dab18-141">Связан синий цвет (0, 0) и зеленый цвет, связанные с (200, 100).</span><span class="sxs-lookup"><span data-stu-id="dab18-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="dab18-142">Линия (толщина пера 10) и эллипс заполняются кисти линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="dab18-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="dab18-143">В строке и эллипс на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="dab18-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="dab18-144">Обратите внимание, что цвет эллипса постепенно при движении вдоль любой строке, параллельной прямой, проходящей через (0, 0) и (200, 100).</span><span class="sxs-lookup"><span data-stu-id="dab18-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="dab18-145">![Линейный градиент](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="dab18-145">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="dab18-146">Создание диагональных линейных градиентов</span><span class="sxs-lookup"><span data-stu-id="dab18-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="dab18-147">Передайте непрозрачный синий и непрозрачный зеленым цветом в качестве третьего и четвертого аргумента соответственно.</span><span class="sxs-lookup"><span data-stu-id="dab18-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="dab18-148">См. также</span><span class="sxs-lookup"><span data-stu-id="dab18-148">See Also</span></span>  
 [<span data-ttu-id="dab18-149">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="dab18-149">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [<span data-ttu-id="dab18-150">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dab18-150">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
