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
# <a name="graphics-and-multimedia"></a>Графика и мультимедиа

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает поддержку мультимедиа, векторную графику, анимацию и композицию содержимого, делая создание интересных пользовательских интерфейсов и содержимого простым делом для разработчиков. С помощью Visual Studio можно создавать векторную графику или сложную анимацию и интегрировать мультимедиа в приложения.

В этом разделе представлены возможности графики, анимации и мультимедиа в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые позволяют добавлять в приложения рисунки, эффекты перехода, звук и видео.

> [!NOTE]
> Использование типов WPF в службе Windows настоятельно не рекомендуется. При попытке использовать типы WPF в службе Windows, службы могут не работать должным образом.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Новые графические и мультимедийные возможности в WPF 4

В части графики и анимации были сделаны некоторые изменения.

- Округление макета

  Когда граница объекта попадает в середину пикселя устройства, не зависящая от разрешения система графики может создавать артефакты отрисовки, например нечеткие или полупрозрачные границы. Предыдущие версии WPF для обработки таких случаев включали функцию привязки пикселей. В Silverlight 2 появилось округление макета, являющееся другим способом перемещения элементов так, чтобы границы попадали между пикселями. WPF теперь поддерживает округление <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> макета <xref:System.Windows.FrameworkElement>с прикрепленным свойством на.

- Кэшированная композиция

  Используя новые <xref:System.Windows.Media.BitmapCache> <xref:System.Windows.Media.BitmapCacheBrush> и классы, можно кэшировать сложную часть визуального дерева в виде бит-карты и значительно улучшить время рендеринга. Растровое изображение продолжает реагировать на действия пользователя, например на щелчки мыши, и им можно рисовать на других элементах, как любой кистью.

- Поддержка построителя текстур 3

  WPF 4 построен на <xref:System.Windows.Media.Effects.ShaderEffect> верхней части поддержки, введенной в WPF 3.5 SP1, позволяя приложениям писать эффекты с помощью версии Pixel Shader (PS) 3.0. Шейдерная модель PS 3.0 сложнее, чем PS 2.0, что позволяет реализовать гораздо больше эффектов на поддерживаемом оборудовании.

- Функции плавности

  Можно усовершенствовать анимацию с помощью функций плавности, которые обеспечивают дополнительный контроль над поведением анимации. Например, можно применить <xref:System.Windows.Media.Animation.ElasticEase> анимацию, чтобы придать анимации упругое поведение. Для получения дополнительной информации см. <xref:System.Windows.Media.Animation>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Графика и отрисовка

WPF включает в себя поддержку высококачественной 2D графики. Возможности включают кисти, геометрические объекты, изображения, фигуры и преобразования. Дополнительные сведения см. в разделе [Графика](graphics.md). Рендеринг графических элементов основан <xref:System.Windows.Media.Visual> на классе. Структура визуальных объектов на экране описывается визуальным деревом. Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md).

### <a name="2d-shapes"></a>2D формы

WPF предоставляет библиотеку широко используемых, векторажных 2D форм, таких как прямоугольники и эллипсы, которые показывают следующие иллюстрации.

![Диаграмма, показывающая эллипсы и прямоугольники.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Эти неотъемлемые формы WPF не только формы: они программируемые элементы, которые реализуют многие из функций, которые вы ожидаете от наиболее распространенных элементов управления, которые включают клавиатуру и мышь ввода. Ниже приводится следующий <xref:System.Windows.UIElement.MouseUp> пример, как обрабатывать <xref:System.Windows.Shapes.Ellipse> событие, поднятое, нажав на элемент.

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

На следующем рисунке показан результат выполнения предыдущей разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода.

![Коробка с сообщением: "Вы нажали на эллипс!"](./media/index/messagebox-text-output.png)

Более подробную информацию см. в разделе [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md). Вводный пример см. в разделе [Пример элементов-фигур](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).

### <a name="2d-geometries"></a>2D геометрии

Когда 2D-формы, которые предоставляет WPF, недостаточны, вы можете использовать поддержку WPF для геометрии и путей для создания собственных. На следующей иллюстрации показано, как можно использовать геометрии для создания фигур в качестве кисти для рисования и для обреза других элементов WPF.

![Скриншот, показывающий, как можно использовать геометрии для создания фигур.](./media/index/use-geometries-create-shapes.png)

Для получения дополнительной информации смотрите [обзор геометрии](geometry-overview.md). Вводный пример в разделе [Примеры геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).

### <a name="2d-effects"></a>2D эффекты

WPF предоставляет библиотеку 2D классов, которые можно использовать для создания различных эффектов. Возможность 2D рендеринга WPF обеспечивает возможность [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] рисовать элементы, которые имеют градиенты, бит-карты, рисунки и видео; и манипулировать ими с помощью вращения, масштабирования и перекоса. Ниже приводится пример многих эффектов, которые можно достичь с помощью кистей WPF.

![Иллюстрация, показывающая различные кисти WPF и элементы краски.](./media/index/brushes-paint-elements.png)

Для получения дополнительной информации, [см.](wpf-brushes-overview.md) Вводный пример см. в разделе [Пример использования кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).

<a name="rendering"></a>

## <a name="3d-rendering"></a>3D Рендеринг

WPF предоставляет набор возможностей 3D-рендеринга, которые интегрируются с поддержкой 2D [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]графики в WPF для того, чтобы создать более захватывающую компоновку и визуализацию данных. На одном конце спектра WPF позволяет рендерить 2D-изображения на поверхности 3D-форм, что демонстрирует следующая иллюстрация.

![Скриншот образца, показывающего 3D-формы с различными текстурами.](./media/index/visual-three-dimensional-shape.png)

Для получения дополнительной информации смотрите [обзор 3D графики](3-d-graphics-overview.md). Для вводного образца [см.](https://go.microsoft.com/fwlink/?LinkID=159964)

<a name="animation"></a>

## <a name="animation"></a>Анимация

Использование анимации позволяет применять к элементам управления и графическим элементам такие эффекты, как увеличение, дрожание, вращение и исчезание, создавать интересные эффекты смены страниц и другие эффекты. Поскольку WPF позволяет оживить большинство свойств, вы не только можете оживить большинство объектов WPF, вы также можете использовать WPF для анимировать пользовательские объекты, которые вы создаете.

![Скриншот анимированного куба.](./media/index/animate-custom-objects.png)

Для получения дополнительной информации [см.](animation-overview.md) Вводный пример в разделе [Коллекция примеров анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).

<a name="media"></a>

## <a name="media"></a>Служба мультимедиа

Изображения, видео и аудио являются мультимедийными способами передачи информации и взаимодействия с пользователями.

### <a name="images"></a>Изображения

Изображения, которые включают значки, фоновые рисунки и даже части анимаций, являются одним из основных элементов большинства приложений. Поскольку часто требуется использовать изображения, WPF предоставляет возможность работать с ними различными способами. На следующем рисунке показан один из таких способов.

![Укладка образца скриншот](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Для получения дополнительной информации смотрите [обзор изображений](imaging-overview.md).

### <a name="video-and-audio"></a>Видео и звук

Основной особенностью графических возможностей WPF является предоставление родной поддержки для работы с мультимедиа, которая включает в себя видео и аудио. Следующий пример демонстрирует вставку в приложение медиапроигрывателя.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>способен воспроизваться как видео, так и аудио, и достаточно расширяем, чтобы позволить легкосоздавать пользовательские пользовательские пользовательские пользовательские файлы.

Дополнительные сведения см. в разделе [Общие сведения о мультимедиа](multimedia-overview.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Общие сведения о фигурах и базовых средствах рисования в WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
- [Разделы руководства по анимации и таймерам](animation-and-timing-how-to-topics.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
- [Общие сведения о мультимедиа](multimedia-overview.md)
