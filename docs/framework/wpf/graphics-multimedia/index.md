---
title: "Графика и мультимедиа | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- media, features
- video effects
- sound effects
- animation, features
- graphics features
- transition effects
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: ea78944133412f43075d8d094cd5fa93685299f9
ms.lasthandoff: 04/08/2017

---
# <a name="graphics-and-multimedia"></a>Графика и мультимедиа
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает поддержку мультимедиа, векторную графику, анимацию и композицию содержимого, делая создание интересных пользовательских интерфейсов и содержимого простым делом для разработчиков. С помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] можно создать векторную графику или сложную анимацию и интегрировать мультимедиа в приложения.  
  
 В этом разделе представлены возможности графики, анимации и мультимедиа в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые позволяют добавлять в приложения рисунки, эффекты перехода, звук и видео.  
  
> [!NOTE]
>  Использование типов WPF в службе Windows настоятельно не рекомендуется. При попытке использовать типы WPF в службе Windows, службы могут не работать должным образом.   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Новые графические и мультимедийные возможности в WPF 4  
 В части графики и анимации были сделаны некоторые изменения.  
  
-   Округление макета  
  
     Когда граница объекта попадает в середину пикселя устройства, не зависящая от разрешения система графики может создавать артефакты отрисовки, например нечеткие или полупрозрачные границы. Предыдущие версии WPF для обработки таких случаев включали функцию привязки пикселей. В Silverlight 2 появилось округление макета, являющееся другим способом перемещения элементов так, чтобы границы попадали между пикселями. Теперь WPF поддерживает округление макета с помощью присоединенного свойства <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> элемента <xref:System.Windows.FrameworkElement>.  
  
-   Кэшированная композиция  
  
     С помощью новых классов <xref:System.Windows.Media.BitmapCache> и <xref:System.Windows.Media.BitmapCacheBrush> можно кэшировать сложную часть визуального дерева в виде растрового изображения, что значительно уменьшает время отрисовки. Растровое изображение продолжает реагировать на действия пользователя, например на щелчки мыши, и им можно рисовать на других элементах, как любой кистью.  
  
-   Поддержка построителя текстур 3  
  
     WPF 4 расширяет поддержку <xref:System.Windows.Media.Effects.ShaderEffect>, представленную в WPF 3.5 SP1, позволяя приложениям записывать эффекты с помощью построителя текстур (PS) версии 3.0. Шейдерная модель PS 3.0 сложнее, чем PS 2.0, что позволяет реализовать гораздо больше эффектов на поддерживаемом оборудовании.  
  
-   Функции плавности  
  
     Можно усовершенствовать анимацию с помощью функций плавности, которые обеспечивают дополнительный контроль над поведением анимации. Например, можно применить к анимации <xref:System.Windows.Media.Animation.ElasticEase>, чтобы она отличалась "пружинным" поведением. Дополнительные сведения см. в описании типов плавности в пространстве имен <xref:System.Windows.Media.Animation>.  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a>Графика и отрисовка  
 WPF включает поддержку двумерной графики высокого качества. Возможности включают кисти, геометрические объекты, изображения, фигуры и преобразования. Дополнительные сведения см. в разделе [Графика](../../../../docs/framework/wpf/graphics-multimedia/graphics.md). Отрисовка графических элементов основана на классе <xref:System.Windows.Media.Visual>. Структура визуальных объектов на экране описывается визуальным деревом. Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
### <a name="2-d-shapes"></a>Двумерные фигуры  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет библиотеку стандартных векторных фигур [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], таких как прямоугольники и эллипсы, показанные на рисунке ниже.  
  
 ![Эллипсы и прямоугольники](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.PNG "WPFIntroFigure4")  
  
 Эти встроенные фигуры [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] являются не просто фигурами: это программируемые элементы, в которых реализованы многие возможности, ожидаемые от наиболее распространенных элементов управления, включая клавиатуру и мышь. В следующем примере демонстрируется обработка события <xref:System.Windows.UIElement.MouseUp>, возникающего при щелчке мышью элемента <xref:System.Windows.Shapes.Ellipse>.  
  
```xaml  
\<Window  
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
  
 ![Окно с текстом "Вы щелкнули эллипс!"](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Более подробную информацию см. в разделе [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md). Вводный пример см. в разделе [Пример элементов-фигур](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
### <a name="2-d-geometries"></a>Двумерные геометрические объекты  
 Когда фигур [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], предоставляемых [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], недостаточно, можно использовать поддержку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] геометрических фигур и путей для создания собственных. Ниже показано, как можно использовать геометрические объекты для создания фигур (например, кисти рисования) и обрезки других элементов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Различные способы использования Path](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.PNG "WPFIntroFigure5")  
  
 Более подробную информацию см. в разделе [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md). Вводный пример в разделе [Примеры геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
### <a name="2-d-effects"></a>Двумерные эффекты  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет библиотеку классов [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], которые можно использовать для создания различных эффектов. Возможности отрисовки в [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] для [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяют рисовать элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], имеющие градиентные заливки, растровые изображения, рисунки и видео, а также управлять ими с помощью вращения, масштабирования и наклона. На следующем рисунке приведен пример многих эффектов, которых можно добиться с помощью кисти [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Иллюстрации различных кистей](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.PNG "WPFIntroFigure6")  
  
 Более подробную информацию см. в разделе [Общие сведения о кистях WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md). Вводный пример см. в разделе [Пример использования кистей](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a>Трехмерная отрисовка  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет набор возможностей отрисовки [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], которые интегрируются с поддержкой графики [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для создания более интересного макета, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и визуализации данных. С одной стороны, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет отрисовывать изображения [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] на поверхностях фигур [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], что показано на рисунке ниже.  
  
 ![Снимок экрана примера Visual3D](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Более подробную информацию см. в разделе [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md). Вводный пример см. в разделе [Пример трехмерных тел](http://go.microsoft.com/fwlink/?LinkID=159964).  
  
<a name="animation"></a>   
## <a name="animation"></a>Анимация  
 Использование анимации позволяет применять к элементам управления и графическим элементам такие эффекты, как увеличение, дрожание, вращение и исчезание, создавать интересные эффекты смены страниц и другие эффекты. Поскольку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет анимировать большинство свойств, можно анимировать не только большинство объектов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], но и использовать [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для анимации пользовательских объектов.  
  
 ![Изображения анимированного куба](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Вводный пример в разделе [Коллекция примеров анимации](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
<a name="media"></a>   
## <a name="media"></a>Мультимедиа  
 Изображения, видео и аудио являются мультимедийными способами передачи информации и взаимодействия с пользователями.  
  
### <a name="images"></a>Изображения  
 Изображения, которые включают значки, фоновые рисунки и даже части анимаций, являются одним из основных элементов большинства приложений. Так как с изображениями приходится работать часто, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет возможность работать с ними различными способами. На следующем рисунке показан один из таких способов.  
  
 ![Пример стилизации (снимок экрана)](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
 Более подробную информацию см. в разделе [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### <a name="video-and-audio"></a>Видео и звук  
 Одна из основных особенностей графических возможностей [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] — встроенная поддержка работы с мультимедиа, что включает видео и аудио. Следующий пример демонстрирует вставку в приложение медиапроигрывателя.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement> может воспроизводить как видео, так и аудио и является достаточно расширяемым для простого создания пользовательских [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].  
  
 Дополнительные сведения см. в разделе [Общие сведения о мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Media3D>   
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Общие сведения о фигурах и базовых средствах рисования в WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Анимация и время](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Трехмерная графика](http://msdn.microsoft.com/en-us/565c1f3c-235b-47de-b05b-3b53ed63f1b8)   
 [Мультимедиа](http://msdn.microsoft.com/en-us/44a8dcd0-80cb-4db0-a222-87cde68c2fac)
