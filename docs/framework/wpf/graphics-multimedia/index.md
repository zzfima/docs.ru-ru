---
title: "Графика и мультимедиа | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, функции"
  - "графические функции"
  - "носители, функции"
  - "звуковые эффекты"
  - "включение эффектов перехода"
  - "видео - эффекты"
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Графика и мультимедиа
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает поддержку мультимедиа, векторной графики, анимации и композиции содержимого, делая простым для разработчиков создание интересных пользовательских интерфейсов и содержимого.  Используя [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], можно создавать векторную графику или сложную анимацию и интегрировать мультимедиа в приложения.  
  
 В этом разделе рассматриваются графические, анимационные и мультимедийные возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые позволяют добавлять рисунки, эффекты перехода, звуки и видео в приложения.  
  
> [!NOTE]
>  Крайне нежелательно использовать типы WPF в службе Windows.  Использование типов WPF в службе Windows может привести к непредвиденному поведению этой службы.  
  
   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## Новые графические и мультимедийные возможности в WPF 4  
 Некоторые изменения также коснулись графики и анимации.  
  
-   Округление макета  
  
     Когда положение границы попадает в середину пикселя устройства, система графики, не зависящая от разрешения, может создавать эффекты отрисовки, такие как смазанные или полупрозрачные границы.  В предыдущих версиях WPF для обработки таких случаев была предусмотрена привязка пикселей.  В Silverlight 2 появилось округление макета, являющееся другим способом перемещения элементов, чтобы границы попадали между пикселями.  Теперь WPF поддерживает округление макета с помощью свойства <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>, подключенного к элементу <xref:System.Windows.FrameworkElement>.  
  
-   Кэшированная композиция  
  
     С помощью новых классов <xref:System.Windows.Media.BitmapCache> и <xref:System.Windows.Media.BitmapCacheBrush> можно кэшировать составную часть визуального дерева как растровое изображение и значительно уменьшить время отрисовки.  Растровое изображение продолжает реагировать на пользовательский ввод, такой как щелчок кнопкой мыши, и его можно изобразить на других элементах, как любую кисть.  
  
-   Поддержка построителя текстуры 3  
  
     WPF 4 строится на основе поддержки <xref:System.Windows.Media.Effects.ShaderEffect>, введенной в WPF 3.5 с пакетом обновления 1 \(SP1\) путем разрешения приложениям записывать эффекты с помощью построителя текстуры \(PS\) версии 3.0.  Модель построителя текстуры версии 3.0 более сложная, чем построитель текстуры версии 2.0, что позволяет использовать гораздо больше эффектов на поддерживаемом оборудовании.  
  
-   Функции плавности  
  
     Можно усовершенствовать анимацию с помощью функции плавности, что дает дополнительный контроль поведения анимации.  Например, можно применить <xref:System.Windows.Media.Animation.ElasticEase> к анимации, чтобы придать анимации быстроту.  Дополнительные сведения см. в документации, посвященной типам плавности в пространстве имен <xref:System.Windows.Media.Animation>.  
  
<a name="graphics_and_rendering"></a>   
## Графика и отрисовка  
 WPF включает поддержку двухмерной графики высокого качества.  Данная функциональность охватывает кисти, геометрии, изображения, фигуры и преобразования.  Дополнительные сведения см. в разделе [Графика](../../../../docs/framework/wpf/graphics-multimedia/graphics.md).  Отрисовка графических элементов основана на классе <xref:System.Windows.Media.Visual>.  Структура визуальных объектов на экране описывается визуальным деревом.  Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
### Двухмерные формы  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет библиотеку, часто используемую для векторного рисования форм [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], таких как прямоугольники и эллипсы, которые показаны на следующем рисунке.  
  
 ![Эллипсы и прямоугольники](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.png "WPFIntroFigure4")  
  
 Эти встроенные фигуры [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] являются не просто формами. Они являются элементами программирования, которые реализуют многие возможности других наиболее распространенных элементов управления, включая клавиатуру и мышь.  В следующем примере показана обработка события <xref:System.Windows.UIElement.MouseUp>, возникающего при щелчке мышью элемента <xref:System.Windows.Shapes.Ellipse>.  
  
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
  
 На следующем рисунке показан результат для предыдущей разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и кода программной части.  
  
 ![Окно с текстом “you clicked the ellipse&#33;”](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")  
  
 Дополнительные сведения см. в разделе [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  Ознакомительный пример см. в файле [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
### Двухмерная геометрия  
 Когда [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] фигур [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] недостаточно, можно использовать поддержку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для геометрических фигур и путей для создания своих собственных фигур.  На следующем рисунке показано, как можно использовать геометрические объекты для создания фигур, например кисти рисования, и отсечения других элементов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Различные способы использования Path](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.png "WPFIntroFigure5")  
  
 Дополнительные сведения см. в разделе [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  Ознакомительный пример см. в файле [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
### Двухмерные эффекты  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет библиотеку классов [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)], которую можно использовать для создания различных эффектов.  Возможности отрисовки [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] обеспечивают средства для рисования элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с градиентами, точечными рисунками, рисунками и видеозаписями, а также управления ими с помощью вращения, масштабирования и [наклона](GTMT).  На следующем рисунке приведен пример многих эффектов, которые можно получить с помощью кисти [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 ![Иллюстрация различных кистей](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.png "WPFIntroFigure6")  
  
 Дополнительные сведения см. в разделе [Общие сведения о кистях WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  Ознакомительный пример см. в файле [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
<a name="rendering"></a>   
## Трехмерная отрисовка  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет набор средств для отрисовки [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], который включает поддержку графики [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для создания более интересного макета [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и визуализации данных.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет отображать изображения [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] на поверхностях фигур [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], как показано на следующем рисунке.  
  
 ![Снимок экрана примера Visual3D](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")  
  
 Дополнительные сведения см. в разделе [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  Ознакомительный пример см. в файле [3\-D Solids Sample](http://go.microsoft.com/fwlink/?LinkID=159964).  
  
<a name="animation"></a>   
## Анимация  
 Используйте эффекты анимации, чтобы заставить элементы управления увеличиваться, вибрировать, вращаться или растворяться, а также чтобы создать оригинальные переходы между страницами и т.д.  Поскольку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет анимировать большинство свойств, можно не только анимировать большинство объектов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], но также использовать [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для анимации создаваемых пользователем объектов.  
  
 ![Изображения анимированного куба](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")  
  
 Дополнительные сведения см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Ознакомительный пример см. в файле [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
<a name="media"></a>   
## Мультимедиа  
 Рисунки, видео и аудио являются разнообразными способами передачи информации и взаимодействия с пользователем.  
  
### Изображения  
 Изображения, которые включают значки, фоновые рисунки и даже часть анимации, являются основной частью большинства приложений.  Так как часто возникает необходимость использовать изображения, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет различные способы работы с ними.  Ниже приведен только один из этих способов.  
  
 ![Снимок экрана примера стилизации](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro\_EventTriggers")  
  
 Дополнительные сведения см. в разделе общих сведений [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### Видео и аудио  
 Основные графические возможности [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляют встроенную поддержку для работы с мультимедиа, которая включает видео и звук.  В следующем примере показано, как вставить в приложение медиа\-проигрыватель.  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <xref:System.Windows.Controls.MediaElement> способен воспроизводить видео и аудио, а также имеет достаточно широкие возможности для легкого создания пользовательских [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].  
  
 Дополнительные сведения см. в разделе [Общие сведения о мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md).  
  
## См. также  
 <xref:System.Windows.Media>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Media3D>   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Animation and Timing](http://msdn.microsoft.com/ru-ru/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [3\-D Graphics](http://msdn.microsoft.com/ru-ru/565c1f3c-235b-47de-b05b-3b53ed63f1b8)   
 [Multimedia](http://msdn.microsoft.com/ru-ru/44a8dcd0-80cb-4db0-a222-87cde68c2fac)