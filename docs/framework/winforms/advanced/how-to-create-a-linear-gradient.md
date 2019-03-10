---
title: Практическое руководство. Создание линейного градиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e47707d040cd7bf67008fab33ac482706963ce39
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725250"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="d09e2-102">Практическое руководство. Создание линейного градиента</span><span class="sxs-lookup"><span data-stu-id="d09e2-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="d09e2-103">поддерживает горизонтальные, вертикальные и диагональные линейные градиенты.</span><span class="sxs-lookup"><span data-stu-id="d09e2-103">provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="d09e2-104">По умолчанию цвет в линейном градиенте меняется равномерно.</span><span class="sxs-lookup"><span data-stu-id="d09e2-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="d09e2-105">Тем не менее можно настроить линейный градиент, таким образом, чтобы цвет меняется образом неоднородной.</span><span class="sxs-lookup"><span data-stu-id="d09e2-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="d09e2-106">В следующем примере заполняется линии, эллипсы и прямоугольник с горизонтальной кисти линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="d09e2-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="d09e2-107"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Конструктор принимает четыре аргумента: две точки и два цвета.</span><span class="sxs-lookup"><span data-stu-id="d09e2-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="d09e2-108">Первая точка (0, 10) связан с первый цвет (красный цвет), и второй точки (200, 10) связан со вторым цветом (синий).</span><span class="sxs-lookup"><span data-stu-id="d09e2-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="d09e2-109">Как и следовало ожидать, линии, соединяющей (0, 10) для (200, 10) плавно меняется от красного к синему.</span><span class="sxs-lookup"><span data-stu-id="d09e2-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="d09e2-110">Вторые точек (50, 10) и (200, 10), не важны.</span><span class="sxs-lookup"><span data-stu-id="d09e2-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="d09e2-111">Важно то, что две точки имеют одну координату второй — соединительных линий по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="d09e2-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="d09e2-112">Эллипс и прямоугольника также постепенно меняются от красного к синему как горизонтальные координаты от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="d09e2-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="d09e2-113">Ниже показаны строки, эллипс и прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="d09e2-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="d09e2-114">Обратите внимание на то, что цвет градиента, повторяет саму себя как горизонтальная координата выйдет за пределы 200.</span><span class="sxs-lookup"><span data-stu-id="d09e2-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="d09e2-115">![Линейный градиент](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="d09e2-115">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="d09e2-116">Использование горизонтальных линейных градиентов</span><span class="sxs-lookup"><span data-stu-id="d09e2-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="d09e2-117">Передайте непрозрачный синий, красный и непрозрачный как третий и четвертый аргумент, соответственно.</span><span class="sxs-lookup"><span data-stu-id="d09e2-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="d09e2-118">В предыдущем примере цветовые компоненты линейно меняются при переходе из горизонтальную координату 0 горизонтальную координату 200.</span><span class="sxs-lookup"><span data-stu-id="d09e2-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="d09e2-119">Например точки, в которых первая координата на равном расстоянии от 0 до 200 будет иметь синего компонента, который находится на равном расстоянии от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="d09e2-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="d09e2-120">позволяет настраивать цвет меняется в зависимости от одного края градиент другой способ изменения.</span><span class="sxs-lookup"><span data-stu-id="d09e2-120">allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="d09e2-121">Предположим, что вы хотите создать градиентную кисть, которая изменяется от черного к красному согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d09e2-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="d09e2-122">Горизонтальная координата</span><span class="sxs-lookup"><span data-stu-id="d09e2-122">Horizontal coordinate</span></span>|<span data-ttu-id="d09e2-123">RGB компонентов</span><span class="sxs-lookup"><span data-stu-id="d09e2-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="d09e2-124">0</span><span class="sxs-lookup"><span data-stu-id="d09e2-124">0</span></span>|<span data-ttu-id="d09e2-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="d09e2-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="d09e2-126">40</span><span class="sxs-lookup"><span data-stu-id="d09e2-126">40</span></span>|<span data-ttu-id="d09e2-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="d09e2-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="d09e2-128">200</span><span class="sxs-lookup"><span data-stu-id="d09e2-128">200</span></span>|<span data-ttu-id="d09e2-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="d09e2-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="d09e2-130">Обратите внимание, что красный компонент имеет половинную интенсивность, когда горизонтальная координата представляет только 20 процентов пути от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="d09e2-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="d09e2-131">В следующем примере задается <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> свойство <xref:System.Drawing.Drawing2D.LinearGradientBrush> объект должен быть сопоставлен три относительный интенсивности три относительные позиции.</span><span class="sxs-lookup"><span data-stu-id="d09e2-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="d09e2-132">Как и в предыдущей таблице относительная интенсивность 0,5, связанный с относительное положение 0,2.</span><span class="sxs-lookup"><span data-stu-id="d09e2-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="d09e2-133">Код заполняет эллипса и прямоугольник с градиентной кисти.</span><span class="sxs-lookup"><span data-stu-id="d09e2-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="d09e2-134">Ниже показан окончательный вид эллипса и прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="d09e2-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="d09e2-135">![Линейный градиент](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="d09e2-135">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="d09e2-136">Настройка линейных градиентов</span><span class="sxs-lookup"><span data-stu-id="d09e2-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="d09e2-137">Передайте непрозрачный черный и непрозрачный красный как третий и четвертый аргумент, соответственно.</span><span class="sxs-lookup"><span data-stu-id="d09e2-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="d09e2-138">Градиенты в предыдущих примерах были по горизонтали; то есть цвет постепенно изменяется при переходе по любой горизонтальной линии.</span><span class="sxs-lookup"><span data-stu-id="d09e2-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="d09e2-139">Можно также определить вертикальные и диагональные градиенты.</span><span class="sxs-lookup"><span data-stu-id="d09e2-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="d09e2-140">В следующем примере передается точки (0, 0) и (200, 100), чтобы <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="d09e2-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="d09e2-141">Связан синий цвет (0, 0) и зеленый цвет, связанные с (200, 100).</span><span class="sxs-lookup"><span data-stu-id="d09e2-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="d09e2-142">Строки (с помощью пера шириной 10) и эллипс заполняются кисти линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="d09e2-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="d09e2-143">Ниже показаны строки, а также эллипса.</span><span class="sxs-lookup"><span data-stu-id="d09e2-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="d09e2-144">Обратите внимание, что цвет эллипса постепенно при переходе по любой строке, — параллельное выполнение на строку, обрабатываемым (0, 0) и (200, 100).</span><span class="sxs-lookup"><span data-stu-id="d09e2-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="d09e2-145">![Линейный градиент](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="d09e2-145">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="d09e2-146">Чтобы создать диагональный линейным градиентом</span><span class="sxs-lookup"><span data-stu-id="d09e2-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="d09e2-147">Передайте непрозрачный синий и непрозрачный зеленый как третий и четвертый аргумент, соответственно.</span><span class="sxs-lookup"><span data-stu-id="d09e2-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="d09e2-148">См. также</span><span class="sxs-lookup"><span data-stu-id="d09e2-148">See also</span></span>
- [<span data-ttu-id="d09e2-149">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="d09e2-149">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="d09e2-150">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d09e2-150">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
