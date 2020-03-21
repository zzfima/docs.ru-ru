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
ms.openlocfilehash: 8636afcc5b63b71dc729812a7f3eb4945ba49494
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112041"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="bf0c3-102">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="bf0c3-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="bf0c3-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает поддержку мультимедиа, векторную графику, анимацию и композицию содержимого, делая создание интересных пользовательских интерфейсов и содержимого простым делом для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="bf0c3-104">С помощью Visual Studio можно создавать векторную графику или сложную анимацию и интегрировать мультимедиа в приложения.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-104">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="bf0c3-105">В этом разделе представлены возможности графики, анимации и мультимедиа в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые позволяют добавлять в приложения рисунки, эффекты перехода, звук и видео.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="bf0c3-106">Использование типов WPF в службе Windows настоятельно не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="bf0c3-107">При попытке использовать типы WPF в службе Windows, службы могут не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="bf0c3-108">Новые графические и мультимедийные возможности в WPF 4</span><span class="sxs-lookup"><span data-stu-id="bf0c3-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="bf0c3-109">В части графики и анимации были сделаны некоторые изменения.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="bf0c3-110">Округление макета</span><span class="sxs-lookup"><span data-stu-id="bf0c3-110">Layout Rounding</span></span>

  <span data-ttu-id="bf0c3-111">Когда граница объекта попадает в середину пикселя устройства, не зависящая от разрешения система графики может создавать артефакты отрисовки, например нечеткие или полупрозрачные границы.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="bf0c3-112">Предыдущие версии WPF для обработки таких случаев включали функцию привязки пикселей.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="bf0c3-113">В Silverlight 2 появилось округление макета, являющееся другим способом перемещения элементов так, чтобы границы попадали между пикселями.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="bf0c3-114">WPF теперь поддерживает округление <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> макета <xref:System.Windows.FrameworkElement>с прикрепленным свойством на.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="bf0c3-115">Кэшированная композиция</span><span class="sxs-lookup"><span data-stu-id="bf0c3-115">Cached Composition</span></span>

  <span data-ttu-id="bf0c3-116">Используя новые <xref:System.Windows.Media.BitmapCache> <xref:System.Windows.Media.BitmapCacheBrush> и классы, можно кэшировать сложную часть визуального дерева в виде бит-карты и значительно улучшить время рендеринга.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="bf0c3-117">Растровое изображение продолжает реагировать на действия пользователя, например на щелчки мыши, и им можно рисовать на других элементах, как любой кистью.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="bf0c3-118">Поддержка построителя текстур 3</span><span class="sxs-lookup"><span data-stu-id="bf0c3-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="bf0c3-119">WPF 4 построен на <xref:System.Windows.Media.Effects.ShaderEffect> верхней части поддержки, введенной в WPF 3.5 SP1, позволяя приложениям писать эффекты с помощью версии Pixel Shader (PS) 3.0.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="bf0c3-120">Шейдерная модель PS 3.0 сложнее, чем PS 2.0, что позволяет реализовать гораздо больше эффектов на поддерживаемом оборудовании.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="bf0c3-121">Функции плавности</span><span class="sxs-lookup"><span data-stu-id="bf0c3-121">Easing Functions</span></span>

  <span data-ttu-id="bf0c3-122">Можно усовершенствовать анимацию с помощью функций плавности, которые обеспечивают дополнительный контроль над поведением анимации.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="bf0c3-123">Например, можно применить <xref:System.Windows.Media.Animation.ElasticEase> анимацию, чтобы придать анимации упругое поведение.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="bf0c3-124">Для получения дополнительной информации см. <xref:System.Windows.Media.Animation></span><span class="sxs-lookup"><span data-stu-id="bf0c3-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="bf0c3-125">Графика и отрисовка</span><span class="sxs-lookup"><span data-stu-id="bf0c3-125">Graphics and Rendering</span></span>

<span data-ttu-id="bf0c3-126">WPF включает в себя поддержку высококачественной 2D графики.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-126">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="bf0c3-127">Возможности включают кисти, геометрические объекты, изображения, фигуры и преобразования.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="bf0c3-128">Дополнительные сведения см. в разделе [Графика](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="bf0c3-129">Рендеринг графических элементов основан <xref:System.Windows.Media.Visual> на классе.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="bf0c3-130">Структура визуальных объектов на экране описывается визуальным деревом.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="bf0c3-131">Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="bf0c3-132">2D формы</span><span class="sxs-lookup"><span data-stu-id="bf0c3-132">2D Shapes</span></span>

<span data-ttu-id="bf0c3-133">WPF предоставляет библиотеку широко используемых, векторажных 2D форм, таких как прямоугольники и эллипсы, которые показывают следующие иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-133">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Диаграмма, показывающая эллипсы и прямоугольники.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="bf0c3-135">Эти неотъемлемые формы WPF не только формы: они программируемые элементы, которые реализуют многие из функций, которые вы ожидаете от наиболее распространенных элементов управления, которые включают клавиатуру и мышь ввода.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-135">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="bf0c3-136">Ниже приводится следующий <xref:System.Windows.UIElement.MouseUp> пример, как обрабатывать <xref:System.Windows.Shapes.Ellipse> событие, поднятое, нажав на элемент.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

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

<span data-ttu-id="bf0c3-137">На следующем рисунке показан результат выполнения предыдущей разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Коробка с сообщением: "Вы нажали на эллипс!"](./media/index/messagebox-text-output.png)

<span data-ttu-id="bf0c3-139">Более подробную информацию см. в разделе [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="bf0c3-140">Вводный пример см. в разделе [Пример элементов-фигур](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-140">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="bf0c3-141">2D геометрии</span><span class="sxs-lookup"><span data-stu-id="bf0c3-141">2D Geometries</span></span>

<span data-ttu-id="bf0c3-142">Когда 2D-формы, которые предоставляет WPF, недостаточны, вы можете использовать поддержку WPF для геометрии и путей для создания собственных.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-142">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="bf0c3-143">На следующей иллюстрации показано, как можно использовать геометрии для создания фигур в качестве кисти для рисования и для обреза других элементов WPF.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![Скриншот, показывающий, как можно использовать геометрии для создания фигур.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="bf0c3-145">Для получения дополнительной информации смотрите [обзор геометрии](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="bf0c3-146">Вводный пример в разделе [Примеры геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-146">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="bf0c3-147">2D эффекты</span><span class="sxs-lookup"><span data-stu-id="bf0c3-147">2D Effects</span></span>

<span data-ttu-id="bf0c3-148">WPF предоставляет библиотеку 2D классов, которые можно использовать для создания различных эффектов.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-148">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="bf0c3-149">Возможность 2D рендеринга WPF обеспечивает возможность [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] рисовать элементы, которые имеют градиенты, бит-карты, рисунки и видео; и манипулировать ими с помощью вращения, масштабирования и перекоса.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-149">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="bf0c3-150">Ниже приводится пример многих эффектов, которые можно достичь с помощью кистей WPF.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-150">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![Иллюстрация, показывающая различные кисти WPF и элементы краски.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="bf0c3-152">Для получения дополнительной информации, [см.](wpf-brushes-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bf0c3-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="bf0c3-153">Вводный пример см. в разделе [Пример использования кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-153">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="bf0c3-154">3D Рендеринг</span><span class="sxs-lookup"><span data-stu-id="bf0c3-154">3D Rendering</span></span>

<span data-ttu-id="bf0c3-155">WPF предоставляет набор возможностей 3D-рендеринга, которые интегрируются с поддержкой 2D [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]графики в WPF для того, чтобы создать более захватывающую компоновку и визуализацию данных.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-155">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="bf0c3-156">На одном конце спектра WPF позволяет рендерить 2D-изображения на поверхности 3D-форм, что демонстрирует следующая иллюстрация.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-156">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![Скриншот образца, показывающего 3D-формы с различными текстурами.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="bf0c3-158">Для получения дополнительной информации смотрите [обзор 3D графики](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-158">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="bf0c3-159">Для вводного образца [см.](https://go.microsoft.com/fwlink/?LinkID=159964)</span><span class="sxs-lookup"><span data-stu-id="bf0c3-159">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="bf0c3-160">Анимация</span><span class="sxs-lookup"><span data-stu-id="bf0c3-160">Animation</span></span>

<span data-ttu-id="bf0c3-161">Использование анимации позволяет применять к элементам управления и графическим элементам такие эффекты, как увеличение, дрожание, вращение и исчезание, создавать интересные эффекты смены страниц и другие эффекты.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="bf0c3-162">Поскольку WPF позволяет оживить большинство свойств, вы не только можете оживить большинство объектов WPF, вы также можете использовать WPF для анимировать пользовательские объекты, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-162">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![Скриншот анимированного куба.](./media/index/animate-custom-objects.png)

<span data-ttu-id="bf0c3-164">Для получения дополнительной информации [см.](animation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bf0c3-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="bf0c3-165">Вводный пример в разделе [Коллекция примеров анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-165">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="bf0c3-166">Служба мультимедиа</span><span class="sxs-lookup"><span data-stu-id="bf0c3-166">Media</span></span>

<span data-ttu-id="bf0c3-167">Изображения, видео и аудио являются мультимедийными способами передачи информации и взаимодействия с пользователями.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="bf0c3-168">Изображения</span><span class="sxs-lookup"><span data-stu-id="bf0c3-168">Images</span></span>

<span data-ttu-id="bf0c3-169">Изображения, которые включают значки, фоновые рисунки и даже части анимаций, являются одним из основных элементов большинства приложений.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="bf0c3-170">Поскольку часто требуется использовать изображения, WPF предоставляет возможность работать с ними различными способами.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-170">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="bf0c3-171">На следующем рисунке показан один из таких способов.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="bf0c3-172">![Укладка образца скриншот](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="bf0c3-172">![Styling sample screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="bf0c3-173">Для получения дополнительной информации смотрите [обзор изображений](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="bf0c3-174">Видео и звук</span><span class="sxs-lookup"><span data-stu-id="bf0c3-174">Video and Audio</span></span>

<span data-ttu-id="bf0c3-175">Основной особенностью графических возможностей WPF является предоставление родной поддержки для работы с мультимедиа, которая включает в себя видео и аудио.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-175">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="bf0c3-176">Следующий пример демонстрирует вставку в приложение медиапроигрывателя.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="bf0c3-177"><xref:System.Windows.Controls.MediaElement>способен воспроизваться как видео, так и аудио, и достаточно расширяем, чтобы позволить легкосоздавать пользовательские пользовательские пользовательские пользовательские файлы.</span><span class="sxs-lookup"><span data-stu-id="bf0c3-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="bf0c3-178">Дополнительные сведения см. в разделе [Общие сведения о мультимедиа](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf0c3-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf0c3-179">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf0c3-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="bf0c3-180">Двумерная графика и изображения</span><span class="sxs-lookup"><span data-stu-id="bf0c3-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="bf0c3-181">Общие сведения о фигурах и базовых средствах рисования в WPF</span><span class="sxs-lookup"><span data-stu-id="bf0c3-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="bf0c3-182">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="bf0c3-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="bf0c3-183">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="bf0c3-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="bf0c3-184">Разделы руководства по анимации и таймерам</span><span class="sxs-lookup"><span data-stu-id="bf0c3-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="bf0c3-185">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="bf0c3-185">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="bf0c3-186">Общие сведения о мультимедиа</span><span class="sxs-lookup"><span data-stu-id="bf0c3-186">Multimedia Overview</span></span>](multimedia-overview.md)
