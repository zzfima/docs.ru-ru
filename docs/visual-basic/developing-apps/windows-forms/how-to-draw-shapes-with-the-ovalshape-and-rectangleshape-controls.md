---
title: Как выполнить Рисование фигур при помощи OvalShape и RectangleShape элементов управления (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: fe937236332591f6065e618c49ca5cf2c54b987c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701226"
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a><span data-ttu-id="e7495-102">Как выполнить Рисование фигур при помощи OvalShape и RectangleShape элементов управления (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e7495-102">How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio)</span></span>
<span data-ttu-id="e7495-103">Можно использовать элемент управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> для рисования окружностей и овалов на формах и контейнерах и во время создания, и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e7495-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control to draw circles or ovals on a form or container, both at design time and at run time.</span></span> <span data-ttu-id="e7495-104">Можно использовать элемент управления <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> для рисования квадратов, прямоугольников и прямоугольников со скругленными углами на формах и контейнерах.</span><span class="sxs-lookup"><span data-stu-id="e7495-104">You can use the <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control to draw squares, rectangles, or rectangles with rounded corners on a form or container.</span></span> <span data-ttu-id="e7495-105">С помощью этого элемента управления также можно рисовать фигуры и во время создания, и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e7495-105">You can also use this control to draw shapes both at design time and at run time.</span></span>  
  
 <span data-ttu-id="e7495-106">Можно настраивать внешний вид фигур, изменяя их толщину, цвет и стиль рамки.</span><span class="sxs-lookup"><span data-stu-id="e7495-106">You can customize the appearance of a shape by changing the width, color, and style of the border.</span></span> <span data-ttu-id="e7495-107">По умолчанию у фигур прозрачный фон. Можно настроить фон, отображая сплошной цвет, узор, градиентную заливку (плавный переход от одного цвета к другому) или рисунок.</span><span class="sxs-lookup"><span data-stu-id="e7495-107">The background of a shape is transparent by default; you can customize the background to display a solid color, a pattern, a gradient fill (transitioning from one color to another), or an image.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a><span data-ttu-id="e7495-108">Рисование простых фигур во время создания</span><span class="sxs-lookup"><span data-stu-id="e7495-108">To draw a simple shape at design time</span></span>  
  
1.  <span data-ttu-id="e7495-109">Перетащите <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> или <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> управления из **Visual Basic PowerPacks** вкладке (Чтобы установить, см. в разделе [элементы управления Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) в **элементов** форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e7495-109">Drag the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> or <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control from the **Visual Basic PowerPacks** tab (to install, see [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e7495-110">Перетащите маркеры размера и перемещения, чтобы придать фигуре нужный размер и положение.</span><span class="sxs-lookup"><span data-stu-id="e7495-110">Drag the sizing and move handles to size and position the shape.</span></span>  
  
     <span data-ttu-id="e7495-111">Можно также изменить размер и расположение фигуры, изменив `Size` и `Position` свойств в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="e7495-111">You can also size and position the shape by changing the `Size` and `Position` properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="e7495-112">Чтобы создать прямоугольник со скругленными углами, выберите `CornerRadius` свойство в **свойства** окна и ему присвоено значение, большее 0.</span><span class="sxs-lookup"><span data-stu-id="e7495-112">To create a rectangle with rounded corners, select the `CornerRadius` property in the **Properties** window and set it to a value that is greater than 0.</span></span>  
  
3.  <span data-ttu-id="e7495-113">В **свойства** окно, можно задать дополнительные свойства для изменения внешнего вида фигуры.</span><span class="sxs-lookup"><span data-stu-id="e7495-113">In the **Properties** window, optionally set additional properties to change the appearance of the shape.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a><span data-ttu-id="e7495-114">Рисование простых фигур во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e7495-114">To draw a simple shape at run time</span></span>  
  
1.  <span data-ttu-id="e7495-115">В меню **Проект** щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="e7495-115">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="e7495-116">В **добавить ссылку** выберите **Microsoft.VisualBasic.PowerPacks.VS**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e7495-116">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e7495-117">В **редактор кода**, добавьте `Imports` или `using` инструкция в верхней части модуля:</span><span class="sxs-lookup"><span data-stu-id="e7495-117">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="e7495-118">Добавьте следующий код в процедуру `Event`:</span><span class="sxs-lookup"><span data-stu-id="e7495-118">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a><span data-ttu-id="e7495-119">Настройка фигур</span><span class="sxs-lookup"><span data-stu-id="e7495-119">Customizing Shapes</span></span>  
 <span data-ttu-id="e7495-120">При использовании параметров по умолчанию элементы управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> отображаются со сплошной черной рамкой шириной в один пиксель и с прозрачным фоном.</span><span class="sxs-lookup"><span data-stu-id="e7495-120">When you use the default settings, the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls are displayed with a solid black border that is one pixel wide and a transparent background.</span></span> <span data-ttu-id="e7495-121">С помощью свойств можно изменить ширину, стиль и цвет рамки.</span><span class="sxs-lookup"><span data-stu-id="e7495-121">You can change the width, style, and color of the border by setting properties.</span></span> <span data-ttu-id="e7495-122">Дополнительные свойства позволяют изменить фон фигуры на заливку сплошным цветом, узор, градиентную заливку или рисунок.</span><span class="sxs-lookup"><span data-stu-id="e7495-122">Additional properties enable you to change the background of a shape to a solid color, a pattern, a gradient fill, or an image.</span></span>  
  
 <span data-ttu-id="e7495-123">Перед изменением фона фигур обратите внимание, как взаимодействуют друг с другом некоторые свойства.</span><span class="sxs-lookup"><span data-stu-id="e7495-123">Before you change the background of a shape, you should know how several of the properties interact.</span></span>  
  
-   <span data-ttu-id="e7495-124">Значение свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> не будет учитываться, если не задать для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span><span class="sxs-lookup"><span data-stu-id="e7495-124">The <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> property setting has no effect unless the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="e7495-125">Если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> задано значение <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, то <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> переопределяет <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7495-125">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> overrides the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span></span>  
  
-   <span data-ttu-id="e7495-126">Если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> задано значение узора, такое как <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> или <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, узор будет показан в <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7495-126">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to a pattern value such as <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> or <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, the pattern will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span></span> <span data-ttu-id="e7495-127">Фон будет показан в <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> задано значение <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span><span class="sxs-lookup"><span data-stu-id="e7495-127">The background will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, provided that the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="e7495-128">Для отображения градиентной заливки нужно установить для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, а для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> — значение, отличное от <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="e7495-128">In order to display a gradient fill, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property must be set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> and the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> property must be set to a value other than <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span></span>  
  
-   <span data-ttu-id="e7495-129">Если задать для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> рисунок, все прочие параметры фона переопределяются.</span><span class="sxs-lookup"><span data-stu-id="e7495-129">Setting the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> property to an image overrides all other background settings.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a><span data-ttu-id="e7495-130">Рисование окружности с настраиваемой рамкой</span><span class="sxs-lookup"><span data-stu-id="e7495-130">To draw a circle that has a custom border</span></span>  
  
1.  <span data-ttu-id="e7495-131">Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e7495-131">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e7495-132">В **свойства** окно в `Size` задайте `Height` и `Width` одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="e7495-132">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="e7495-133">Задайте для свойства `BorderColor` нужный цвет.</span><span class="sxs-lookup"><span data-stu-id="e7495-133">Set the `BorderColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="e7495-134">Задайте для свойства `BorderStyle` любое значение, отличное от `Solid`.</span><span class="sxs-lookup"><span data-stu-id="e7495-134">Set the `BorderStyle` property to any value other than `Solid`.</span></span>  
  
5.  <span data-ttu-id="e7495-135">Задайте для свойства `BorderWidth` нужный размер в пикселях.</span><span class="sxs-lookup"><span data-stu-id="e7495-135">Set the `BorderWidth` to the size that you want, in pixels.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a><span data-ttu-id="e7495-136">Рисование окружности с заливкой сплошным цветом</span><span class="sxs-lookup"><span data-stu-id="e7495-136">To draw a circle that has a solid fill</span></span>  
  
1.  <span data-ttu-id="e7495-137">Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e7495-137">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e7495-138">В **свойства** окно в `Size` задайте `Height` и `Width` одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="e7495-138">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="e7495-139">Задайте для свойства `BackColor` нужный цвет.</span><span class="sxs-lookup"><span data-stu-id="e7495-139">Set the `BackColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="e7495-140">Задайте для свойства `BackStyle` значение `Opaque`.</span><span class="sxs-lookup"><span data-stu-id="e7495-140">Set the `BackStyle` property to `Opaque`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a><span data-ttu-id="e7495-141">Рисование окружности с заливкой узором</span><span class="sxs-lookup"><span data-stu-id="e7495-141">To draw a circle that has a patterned fill</span></span>  
  
1.  <span data-ttu-id="e7495-142">Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e7495-142">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e7495-143">В **свойства** окно в `Size` задайте `Height` и `Width` одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="e7495-143">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="e7495-144">Задайте для свойства `BackColor` нужный цвет фона.</span><span class="sxs-lookup"><span data-stu-id="e7495-144">Set the `BackColor` property to the color that you want for the background.</span></span>  
  
4.  <span data-ttu-id="e7495-145">Задайте для свойства `BackStyle` значение `Opaque`.</span><span class="sxs-lookup"><span data-stu-id="e7495-145">Set the `BackStyle` property to `Opaque`.</span></span>  
  
5.  <span data-ttu-id="e7495-146">Задайте для свойства `FillColor` нужный цвет фонового узора.</span><span class="sxs-lookup"><span data-stu-id="e7495-146">Set the `FillColor` property to the color that you want for the pattern.</span></span>  
  
6.  <span data-ttu-id="e7495-147">Задайте для свойства `FillStyle` любое значение, отличное от `Transparent` или `Solid`.</span><span class="sxs-lookup"><span data-stu-id="e7495-147">Set the `FillStyle` property to any value other than `Transparent` or `Solid`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a><span data-ttu-id="e7495-148">Рисование окружности с градиентной заливкой</span><span class="sxs-lookup"><span data-stu-id="e7495-148">To draw a circle that has a gradient fill</span></span>  
  
1.  <span data-ttu-id="e7495-149">Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e7495-149">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e7495-150">В **свойства** окно в `Size` задайте `Height` и `Width` одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="e7495-150">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="e7495-151">Задайте для свойства `FillColor` нужный начальный цвет.</span><span class="sxs-lookup"><span data-stu-id="e7495-151">Set the `FillColor` property to the color that you want for the starting color.</span></span>  
  
4.  <span data-ttu-id="e7495-152">Задайте для свойства `FillGradientColor` нужный конечный цвет.</span><span class="sxs-lookup"><span data-stu-id="e7495-152">Set the `FillGradientColor` property to the color that you want for the ending color.</span></span>  
  
5.  <span data-ttu-id="e7495-153">Задайте для свойства `FillGradientStyle` значение, отличное от `None`.</span><span class="sxs-lookup"><span data-stu-id="e7495-153">Set the `FillGradientStyle` property to a value other than `None`.</span></span>  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a><span data-ttu-id="e7495-154">Рисование окружности, заполненной рисунком</span><span class="sxs-lookup"><span data-stu-id="e7495-154">To draw a circle that is filled with an image</span></span>  
  
1.  <span data-ttu-id="e7495-155">Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e7495-155">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e7495-156">В **свойства** окно в `Size` задайте `Height` и `Width` одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="e7495-156">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="e7495-157">Выберите `BackgroundImage` свойство и нажмите кнопку **кнопку с многоточием** кнопку (...).</span><span class="sxs-lookup"><span data-stu-id="e7495-157">Select the `BackgroundImage` property and click the **ellipsis** button (...).</span></span>  
  
4.  <span data-ttu-id="e7495-158">В **Выбор ресурса** диалоговом окне выберите рисунок для отображения.</span><span class="sxs-lookup"><span data-stu-id="e7495-158">In the **Select Resource** dialog box, select an image to display.</span></span> <span data-ttu-id="e7495-159">Если в списке нет ресурсов, нажмите кнопку **импорта** для указания местоположения изображения.</span><span class="sxs-lookup"><span data-stu-id="e7495-159">If no image resources are listed, click **Import** to browse to the location of an image.</span></span>  
  
5.  <span data-ttu-id="e7495-160">Нажмите кнопку **ОК** для вставки изображения.</span><span class="sxs-lookup"><span data-stu-id="e7495-160">Click **OK** to insert the image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7495-161">См. также</span><span class="sxs-lookup"><span data-stu-id="e7495-161">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>
- <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>
- [<span data-ttu-id="e7495-162">Знакомство с элементами управления Line и Shape</span><span class="sxs-lookup"><span data-stu-id="e7495-162">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [<span data-ttu-id="e7495-163">Практическое руководство. Рисование линий с помощью элемента управления LineShape</span><span class="sxs-lookup"><span data-stu-id="e7495-163">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
