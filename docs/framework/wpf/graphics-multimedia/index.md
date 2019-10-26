---
title: Графика и мультимедиа
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: 150b742c2195c07abf2b2823871627b0ba827580
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919993"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="74678-102">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="74678-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="74678-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает поддержку мультимедиа, векторную графику, анимацию и композицию содержимого, облегчая разработчикам создание интересных пользовательских интерфейсов и содержимого.</span><span class="sxs-lookup"><span data-stu-id="74678-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="74678-104">С помощью Visual Studio можно создавать векторную графику или сложную анимацию и интегрировать мультимедиа в приложения.</span><span class="sxs-lookup"><span data-stu-id="74678-104">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="74678-105">В этом разделе представлены возможности графики, анимации и мультимедиа в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые позволяют добавлять в приложения рисунки, эффекты перехода, звук и видео.</span><span class="sxs-lookup"><span data-stu-id="74678-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="74678-106">Использование типов WPF в службе Windows настоятельно не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="74678-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="74678-107">При попытке использовать типы WPF в службе Windows, службы могут не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="74678-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="74678-108">Новые графические и мультимедийные возможности в WPF 4</span><span class="sxs-lookup"><span data-stu-id="74678-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="74678-109">В части графики и анимации были сделаны некоторые изменения.</span><span class="sxs-lookup"><span data-stu-id="74678-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="74678-110">Округление макета</span><span class="sxs-lookup"><span data-stu-id="74678-110">Layout Rounding</span></span>

  <span data-ttu-id="74678-111">Когда граница объекта попадает в середину пикселя устройства, не зависящая от разрешения система графики может создавать артефакты отрисовки, например нечеткие или полупрозрачные границы.</span><span class="sxs-lookup"><span data-stu-id="74678-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="74678-112">Предыдущие версии WPF для обработки таких случаев включали функцию привязки пикселей.</span><span class="sxs-lookup"><span data-stu-id="74678-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="74678-113">В Silverlight 2 появилось округление макета, являющееся другим способом перемещения элементов так, чтобы границы попадали между пикселями.</span><span class="sxs-lookup"><span data-stu-id="74678-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="74678-114">Теперь WPF поддерживает округление макета с присоединенным свойством <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> на <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="74678-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="74678-115">Кэшированная композиция</span><span class="sxs-lookup"><span data-stu-id="74678-115">Cached Composition</span></span>

  <span data-ttu-id="74678-116">С помощью новых классов <xref:System.Windows.Media.BitmapCache> и <xref:System.Windows.Media.BitmapCacheBrush> можно кэшировать сложную часть визуального дерева в виде точечного рисунка и значительно увеличить время отрисовки.</span><span class="sxs-lookup"><span data-stu-id="74678-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="74678-117">Растровое изображение продолжает реагировать на действия пользователя, например на щелчки мыши, и им можно рисовать на других элементах, как любой кистью.</span><span class="sxs-lookup"><span data-stu-id="74678-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="74678-118">Поддержка построителя текстур 3</span><span class="sxs-lookup"><span data-stu-id="74678-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="74678-119">Платформа WPF 4 строится на основе поддержки <xref:System.Windows.Media.Effects.ShaderEffect>, представленной в WPF 3,5 с пакетом обновления 1 (SP1), позволяя приложениям записывать эффекты с помощью пиксельного шейдера (PS) версии 3,0.</span><span class="sxs-lookup"><span data-stu-id="74678-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="74678-120">Шейдерная модель PS 3.0 сложнее, чем PS 2.0, что позволяет реализовать гораздо больше эффектов на поддерживаемом оборудовании.</span><span class="sxs-lookup"><span data-stu-id="74678-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="74678-121">Функции плавности</span><span class="sxs-lookup"><span data-stu-id="74678-121">Easing Functions</span></span>

  <span data-ttu-id="74678-122">Можно усовершенствовать анимацию с помощью функций плавности, которые обеспечивают дополнительный контроль над поведением анимации.</span><span class="sxs-lookup"><span data-stu-id="74678-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="74678-123">Например, можно применить к анимации <xref:System.Windows.Media.Animation.ElasticEase>, чтобы сделать анимацию высокоэффектной.</span><span class="sxs-lookup"><span data-stu-id="74678-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="74678-124">Дополнительные сведения см. в разделе Типы замедления в пространстве имен <xref:System.Windows.Media.Animation>.</span><span class="sxs-lookup"><span data-stu-id="74678-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="74678-125">Графика и отрисовка</span><span class="sxs-lookup"><span data-stu-id="74678-125">Graphics and Rendering</span></span>

<span data-ttu-id="74678-126">WPF включает поддержку двумерной графики высокого качества.</span><span class="sxs-lookup"><span data-stu-id="74678-126">WPF includes support for high quality 2-D graphics.</span></span> <span data-ttu-id="74678-127">Возможности включают кисти, геометрические объекты, изображения, фигуры и преобразования.</span><span class="sxs-lookup"><span data-stu-id="74678-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="74678-128">Дополнительные сведения см. в разделе [Графика](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="74678-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="74678-129">Отрисовка графических элементов основана на классе <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="74678-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="74678-130">Структура визуальных объектов на экране описывается визуальным деревом.</span><span class="sxs-lookup"><span data-stu-id="74678-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="74678-131">Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2-d-shapes"></a><span data-ttu-id="74678-132">Двумерные фигуры</span><span class="sxs-lookup"><span data-stu-id="74678-132">2-D Shapes</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="74678-133">предоставляет библиотеку часто используемых векторно рисуемых трехмерных фигур, таких как прямоугольники и эллипсы, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="74678-133">provides a library of commonly used, vector-drawn 2-D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Диаграмма, на которой показаны многоточие и прямоугольники.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="74678-135">Эти встроенные фигуры [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] являются не просто фигурами: это программируемые элементы, в которых реализованы многие возможности, ожидаемые от наиболее распространенных элементов управления, включая клавиатуру и мышь.</span><span class="sxs-lookup"><span data-stu-id="74678-135">These intrinsic [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="74678-136">В следующем примере показано, как обрабатывалось событие <xref:System.Windows.UIElement.MouseUp>, вызванное щелчком элемента <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="74678-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

<span data-ttu-id="74678-137">На следующем рисунке показан результат выполнения предыдущей разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода.</span><span class="sxs-lookup"><span data-stu-id="74678-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Окно сообщения "вы щелкнули многоточие!"](./media/index/messagebox-text-output.png)

<span data-ttu-id="74678-139">Более подробную информацию см. в разделе [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="74678-140">Вводный пример см. в разделе [Пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="74678-140">For an introductory sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>

### <a name="2-d-geometries"></a><span data-ttu-id="74678-141">Двумерные геометрические объекты</span><span class="sxs-lookup"><span data-stu-id="74678-141">2-D Geometries</span></span>

<span data-ttu-id="74678-142">Если недостаточно двумерных фигур, которые [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляют, можно использовать [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддержку геометрических схем и путей для создания собственных.</span><span class="sxs-lookup"><span data-stu-id="74678-142">When the 2-D shapes that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides are not sufficient, you can use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] support for geometries and paths to create your own.</span></span> <span data-ttu-id="74678-143">Ниже показано, как можно использовать геометрические объекты для создания фигур (например, кисти рисования) и обрезки других элементов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74678-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elements.</span></span>

![Снимок экрана, показывающий, как можно использовать геометрические фигуры для создания фигур.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="74678-145">Более подробную информацию см. в разделе [Общие сведения о классе Geometry](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="74678-146">Вводный пример в разделе [Примеры геометрических объектов](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="74678-146">For an introductory sample, see [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>

### <a name="2-d-effects"></a><span data-ttu-id="74678-147">Двумерные эффекты</span><span class="sxs-lookup"><span data-stu-id="74678-147">2-D Effects</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="74678-148">предоставляет библиотеку двумерных классов, которые можно использовать для создания различных эффектов.</span><span class="sxs-lookup"><span data-stu-id="74678-148">provides a library of 2-D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="74678-149">Функция двухмерной отрисовки [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет возможность рисовать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов с градиентами, точечными рисунками, рисунками и видео. и для управления ими с помощью вращения, масштабирования и наклона.</span><span class="sxs-lookup"><span data-stu-id="74678-149">The 2-D rendering capability of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="74678-150">На следующем рисунке приведен пример многих эффектов, которых можно добиться с помощью кисти [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74678-150">The following illustration gives an example of the many effects you can achieve by using [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] brushes.</span></span>

![Иллюстрация, демонстрирующая различные кисти и элементы Paint WPF.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="74678-152">Более подробную информацию см. в разделе [Общие сведения о кистях WPF](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="74678-153">Вводный пример см. в разделе [Пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="74678-153">For an introductory sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>

<a name="rendering"></a>

## <a name="3-d-rendering"></a><span data-ttu-id="74678-154">Трехмерная отрисовка</span><span class="sxs-lookup"><span data-stu-id="74678-154">3-D Rendering</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="74678-155">предоставляет набор возможностей трехмерной отрисовки, которые интегрируются с поддержкой двухмерной графики в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], чтобы создавать более привлекательные макеты, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]и визуализации данных.</span><span class="sxs-lookup"><span data-stu-id="74678-155">provides a set of 3-D rendering capabilities that integrate with 2-D graphics support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="74678-156">На одном конце спектра [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет визуализировать двумерные изображения на поверхности трехмерных фигур, которые показаны на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="74678-156">At one end of the spectrum, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to render 2-D images onto the surfaces of 3-D shapes, which the following illustration demonstrates.</span></span>

![Снимок экрана примера, иллюстрирующий трехмерные фигуры с разными текстурами.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="74678-158">Более подробную информацию см. в разделе [Обзор трехмерной графики](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-158">For more information, see [3-D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="74678-159">Вводный пример см. в разделе [Пример трехмерных тел](https://go.microsoft.com/fwlink/?LinkID=159964).</span><span class="sxs-lookup"><span data-stu-id="74678-159">For an introductory sample, see [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="74678-160">Анимация</span><span class="sxs-lookup"><span data-stu-id="74678-160">Animation</span></span>

<span data-ttu-id="74678-161">Использование анимации позволяет применять к элементам управления и графическим элементам такие эффекты, как увеличение, дрожание, вращение и исчезание, создавать интересные эффекты смены страниц и другие эффекты.</span><span class="sxs-lookup"><span data-stu-id="74678-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="74678-162">Поскольку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет анимировать большинство свойств, можно анимировать не только большинство объектов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], но и использовать [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для анимации пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="74678-162">Because [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to animate most properties, not only can you animate most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] objects, you can also use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to animate custom objects that you create.</span></span>

![Снимок экрана: анимированный куб.](./media/index/animate-custom-objects.png)

<span data-ttu-id="74678-164">Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="74678-165">Вводный пример в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="74678-165">For an introductory sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="74678-166">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="74678-166">Media</span></span>

<span data-ttu-id="74678-167">Изображения, видео и аудио являются мультимедийными способами передачи информации и взаимодействия с пользователями.</span><span class="sxs-lookup"><span data-stu-id="74678-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="74678-168">образы,</span><span class="sxs-lookup"><span data-stu-id="74678-168">Images</span></span>

<span data-ttu-id="74678-169">Изображения, которые включают значки, фоновые рисунки и даже части анимаций, являются одним из основных элементов большинства приложений.</span><span class="sxs-lookup"><span data-stu-id="74678-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="74678-170">Так как с изображениями приходится работать часто, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет возможность работать с ними различными способами.</span><span class="sxs-lookup"><span data-stu-id="74678-170">Because you frequently need to use images, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="74678-171">На следующем рисунке показан один из таких способов.</span><span class="sxs-lookup"><span data-stu-id="74678-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="74678-172">![Снимок экрана с примерами стилей](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="74678-172">![Styling sample screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="74678-173">Более подробную информацию см. в разделе [Общие сведения об обработке изображений](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="74678-174">Видео и звук</span><span class="sxs-lookup"><span data-stu-id="74678-174">Video and Audio</span></span>

<span data-ttu-id="74678-175">Одна из основных особенностей графических возможностей [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] — встроенная поддержка работы с мультимедиа, что включает видео и аудио.</span><span class="sxs-lookup"><span data-stu-id="74678-175">A core feature of the graphics capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="74678-176">Следующий пример демонстрирует вставку в приложение медиапроигрывателя.</span><span class="sxs-lookup"><span data-stu-id="74678-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="74678-177"><xref:System.Windows.Controls.MediaElement> способен воспроизводить видео и аудио, и достаточно расширяема, чтобы обеспечить простое создание пользовательских интерфейсов пользователя.</span><span class="sxs-lookup"><span data-stu-id="74678-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="74678-178">Дополнительные сведения см. в разделе [Общие сведения о мультимедиа](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74678-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74678-179">См. также</span><span class="sxs-lookup"><span data-stu-id="74678-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="74678-180">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="74678-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="74678-181">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="74678-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="74678-182">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="74678-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="74678-183">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="74678-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="74678-184">Разделы руководства по анимации и времени</span><span class="sxs-lookup"><span data-stu-id="74678-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="74678-185">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="74678-185">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="74678-186">Общие сведения о мультимедиа</span><span class="sxs-lookup"><span data-stu-id="74678-186">Multimedia Overview</span></span>](multimedia-overview.md)
