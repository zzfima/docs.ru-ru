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
ms.openlocfilehash: b836659821b54698b675d48acd4e46466001d654
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937920"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="ddeff-102">Практическое руководство. Создание линейного градиента</span><span class="sxs-lookup"><span data-stu-id="ddeff-102">How to: Create a Linear Gradient</span></span>
<span data-ttu-id="ddeff-103">GDI + поддерживает горизонтальные, вертикальные и диагональные линейные градиенты.</span><span class="sxs-lookup"><span data-stu-id="ddeff-103">GDI+ provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="ddeff-104">По умолчанию цвет в линейном градиенте меняется равномерно.</span><span class="sxs-lookup"><span data-stu-id="ddeff-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="ddeff-105">Тем не менее можно настроить линейный градиент, таким образом, чтобы цвет меняется образом неоднородной.</span><span class="sxs-lookup"><span data-stu-id="ddeff-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  

> [!NOTE]
> <span data-ttu-id="ddeff-106">В этой статье относятся методы, вызываемые из элемента управления <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="ddeff-106">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

<span data-ttu-id="ddeff-107">В следующем примере заполняется линии, эллипсы и прямоугольник с горизонтальной кисти линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="ddeff-107">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
<span data-ttu-id="ddeff-108"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> Конструктор принимает четыре аргумента: две точки и два цвета.</span><span class="sxs-lookup"><span data-stu-id="ddeff-108">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="ddeff-109">Первая точка (0, 10) связан с первый цвет (красный цвет), и второй точки (200, 10) связан со вторым цветом (синий).</span><span class="sxs-lookup"><span data-stu-id="ddeff-109">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="ddeff-110">Как и следовало ожидать, линии, соединяющей (0, 10) для (200, 10) плавно меняется от красного к синему.</span><span class="sxs-lookup"><span data-stu-id="ddeff-110">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="ddeff-111">Вторые точки (0, 10) и (200, 10), не важны.</span><span class="sxs-lookup"><span data-stu-id="ddeff-111">The 10s in the points (0, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="ddeff-112">Важно то, что две точки имеют одну координату второй — соединительных линий по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="ddeff-112">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="ddeff-113">Эллипс и прямоугольника также постепенно меняются от красного к синему как горизонтальные координаты от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="ddeff-113">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="ddeff-114">Ниже показаны строки, эллипс и прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="ddeff-114">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="ddeff-115">Обратите внимание на то, что цвет градиента, повторяет саму себя как горизонтальная координата выйдет за пределы 200.</span><span class="sxs-lookup"><span data-stu-id="ddeff-115">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="ddeff-116">![Линейный градиент](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="ddeff-116">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="ddeff-117">Использование горизонтальных линейных градиентов</span><span class="sxs-lookup"><span data-stu-id="ddeff-117">To use horizontal linear gradients</span></span>  
  
- <span data-ttu-id="ddeff-118">Передайте непрозрачный синий, красный и непрозрачный как третий и четвертый аргумент, соответственно.</span><span class="sxs-lookup"><span data-stu-id="ddeff-118">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="ddeff-119">В предыдущем примере цветовые компоненты линейно меняются при переходе из горизонтальную координату 0 горизонтальную координату 200.</span><span class="sxs-lookup"><span data-stu-id="ddeff-119">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="ddeff-120">Например точки, в которых первая координата на равном расстоянии от 0 до 200 будет иметь синего компонента, который находится на равном расстоянии от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="ddeff-120">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 <span data-ttu-id="ddeff-121">GDI + позволяет настраивать цвет меняется в зависимости от одного края градиент другой способ изменения.</span><span class="sxs-lookup"><span data-stu-id="ddeff-121">GDI+ allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="ddeff-122">Предположим, что вы хотите создать градиентную кисть, которая изменяется от черного к красному согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ddeff-122">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="ddeff-123">Горизонтальная координата</span><span class="sxs-lookup"><span data-stu-id="ddeff-123">Horizontal coordinate</span></span>|<span data-ttu-id="ddeff-124">RGB компонентов</span><span class="sxs-lookup"><span data-stu-id="ddeff-124">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="ddeff-125">0</span><span class="sxs-lookup"><span data-stu-id="ddeff-125">0</span></span>|<span data-ttu-id="ddeff-126">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="ddeff-126">(0, 0, 0)</span></span>|  
|<span data-ttu-id="ddeff-127">40</span><span class="sxs-lookup"><span data-stu-id="ddeff-127">40</span></span>|<span data-ttu-id="ddeff-128">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="ddeff-128">(128, 0, 0)</span></span>|  
|<span data-ttu-id="ddeff-129">200</span><span class="sxs-lookup"><span data-stu-id="ddeff-129">200</span></span>|<span data-ttu-id="ddeff-130">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="ddeff-130">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="ddeff-131">Обратите внимание, что красный компонент имеет половинную интенсивность, когда горизонтальная координата представляет только 20 процентов пути от 0 до 200.</span><span class="sxs-lookup"><span data-stu-id="ddeff-131">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="ddeff-132">В следующем примере задается <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> свойства должен быть сопоставлен три относительный интенсивности три относительные позиции.</span><span class="sxs-lookup"><span data-stu-id="ddeff-132">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> property to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="ddeff-133">Как и в предыдущей таблице относительная интенсивность 0,5, связанный с относительное положение 0,2.</span><span class="sxs-lookup"><span data-stu-id="ddeff-133">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="ddeff-134">Код заполняет эллипса и прямоугольник с градиентной кисти.</span><span class="sxs-lookup"><span data-stu-id="ddeff-134">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="ddeff-135">Ниже показан окончательный вид эллипса и прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="ddeff-135">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="ddeff-136">![Линейный градиент](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="ddeff-136">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  

### <a name="to-customize-linear-gradients"></a><span data-ttu-id="ddeff-137">Настройка линейных градиентов</span><span class="sxs-lookup"><span data-stu-id="ddeff-137">To customize linear gradients</span></span>  
  
- <span data-ttu-id="ddeff-138">Передайте непрозрачный черный и непрозрачный красный как третий и четвертый аргумент, соответственно.</span><span class="sxs-lookup"><span data-stu-id="ddeff-138">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="ddeff-139">Градиенты в предыдущих примерах были по горизонтали; то есть цвет постепенно изменяется при переходе по любой горизонтальной линии.</span><span class="sxs-lookup"><span data-stu-id="ddeff-139">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="ddeff-140">Можно также определить вертикальные и диагональные градиенты.</span><span class="sxs-lookup"><span data-stu-id="ddeff-140">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="ddeff-141">В следующем примере передается точки (0, 0) и (200, 100), чтобы <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="ddeff-141">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="ddeff-142">Связан синий цвет (0, 0) и зеленый цвет, связанные с (200, 100).</span><span class="sxs-lookup"><span data-stu-id="ddeff-142">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="ddeff-143">Строки (с помощью пера шириной 10) и эллипс заполняются кисти линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="ddeff-143">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="ddeff-144">Ниже показаны строки, а также эллипса.</span><span class="sxs-lookup"><span data-stu-id="ddeff-144">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="ddeff-145">Обратите внимание, что цвет эллипса постепенно при переходе по любой строке, — параллельное выполнение на строку, обрабатываемым (0, 0) и (200, 100).</span><span class="sxs-lookup"><span data-stu-id="ddeff-145">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="ddeff-146">![Линейный градиент](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="ddeff-146">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="ddeff-147">Чтобы создать диагональный линейным градиентом</span><span class="sxs-lookup"><span data-stu-id="ddeff-147">To create diagonal linear gradients</span></span>  
  
- <span data-ttu-id="ddeff-148">Передайте непрозрачный синий и непрозрачный зеленый как третий и четвертый аргумент, соответственно.</span><span class="sxs-lookup"><span data-stu-id="ddeff-148">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="ddeff-149">См. также</span><span class="sxs-lookup"><span data-stu-id="ddeff-149">See also</span></span>

- [<span data-ttu-id="ddeff-150">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="ddeff-150">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="ddeff-151">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddeff-151">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
