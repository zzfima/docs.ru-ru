---
title: Общие сведения об эффектах анимации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: 5fb9550ddce4ead900206c2ece2f976ab8b42c4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="animation-overview"></a>Общие сведения об эффектах анимации
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет мощный набор средств графики и макет, позволяющие создавать привлекательные пользовательские интерфейсы и документы. Применение анимации позволяет сделать пользовательский интерфейс еще более наглядным и удобным в использовании. Анимацию цвета фона или объекта <xref:System.Windows.Media.Transform>, можно создать экранных эффектов перехода или отображения визуальных подсказок.  
  
 Данный обзор представляет собой введение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации и системы управления временем. Этот раздел посвящен анимацией [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектов с использованием раскадровки.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Введение в анимацию  
 Анимация — это имитация изменений, которая обеспечивается быстрым показом серии слегка отличающихся друг от друга изображений. Мозг человека воспринимает набор изображений как одну непрерывно изменяющуюся картинку. В фильме эта имитация создается за счет применения камер, записывающих множество фотографий (кадров) в секунду. При воспроизведении кадров проектором зрители видят движущееся изображение.  
  
 Анимация на компьютере выполняется по аналогичному принципу. Например, программа, в которой реализуется исчезновение прямоугольника, может работать следующим образом.  
  
-   В программе создается таймер.  
  
-   Через заданные временные интервалы проверяется значение таймера для определения истекшего времени.  
  
-   При каждой проверке значения таймера вычисляется текущее значение непрозрачности для прямоугольника в зависимости от прошедшего времени.  
  
-   Затем программа обновляет прямоугольник с использованием нового значения и перерисовывает его.  
  
 До появления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] разработчикам приходится создавать и управлять временем системами либо использовать специальные пользовательские библиотеки. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] включает систему эффективность промежутков времени, предоставляется с помощью управляемого кода и [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и тесно интегрирована в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework. Анимация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] упрощает анимацию элементов управления и других графических объектов.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эффективно осуществляются все внутренние процессы управления системой времени и перерисовки экрана. Предоставляются классы контроля времени, позволяющие сосредоточиться на создаваемых эффектах, а не на механике их реализации. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также упрощает создание собственной анимации, предоставляя доступ к базовым классам анимации, из которых пользовательские классы могут наследовать средства создания пользовательской анимации. По сравнению со стандартными пользовательские классы анимации обеспечивают большое преимущество в производительности.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>Система анимации свойств WPF  
 Если понять основные понятия системы управления временем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации может быть проще использовать. Наиболее важно то, что в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], анимация объектов осуществляется путем применения анимации к их свойствам. Например, чтобы увеличить размер элемента среды, анимировать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства. Чтобы скрыть объект из представления, следует анимировать его <xref:System.Windows.UIElement.Opacity%2A> свойство.  
  
 Свойство, поддерживающее анимацию, должно удовлетворять следующим трем требованиям.  
  
-   Свойство является свойством зависимостей.  
  
-   Он должен принадлежать к классу, который наследует от <xref:System.Windows.DependencyObject> и реализует <xref:System.Windows.Media.Animation.IAnimatable> интерфейса.  
  
-   Доступен совместимый тип анимации. (Если [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предоставляет сертификат, можно создать свой собственный. В разделе [Обзор пользовательской анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержит множество объектов с <xref:System.Windows.Media.Animation.IAnimatable> свойства. Элементы управления, например <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.TabControl>, а также <xref:System.Windows.Controls.Panel> и <xref:System.Windows.Shapes.Shape> объекты наследуют от <xref:System.Windows.DependencyObject>. Большинство их свойств являются свойствами зависимостей.  
  
 Анимацию можно использовать практически везде, где используются стили и шаблоны элементов управления. Анимация не обязательно должна быть визуальной; можно анимировать и объекты, не являющиеся частью пользовательского интерфейса, если они соответствуют описанным в этом разделе условиям.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Пример. Реализация исчезновения и появления элемента  
 В этом примере показано, как использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации для анимации значения свойства зависимостей. Она использует <xref:System.Windows.Media.Animation.DoubleAnimation>, который является типом анимации, которая приводит к возникновению ошибки <xref:System.Double> значения, для которого должна начаться анимация <xref:System.Windows.UIElement.Opacity%2A> свойство <xref:System.Windows.Shapes.Rectangle>. В результате <xref:System.Windows.Shapes.Rectangle> исчезает и появляется.  
  
 В первой части примера создается <xref:System.Windows.Shapes.Rectangle> элемента. Описанных ниже показано, как создание анимации и применить его в прямоугольник <xref:System.Windows.UIElement.Opacity%2A> свойство.
  
 В следующем примере показано создание <xref:System.Windows.Shapes.Rectangle> элемент <xref:System.Windows.Controls.StackPanel> в XAML.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 В следующем примере показано создание <xref:System.Windows.Shapes.Rectangle> элемент <xref:System.Windows.Controls.StackPanel> в коде.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Часть 1. Создание объекта DoubleAnimation  
 Один из способов сделать исчезновения и появления элемента является анимация его <xref:System.Windows.UIElement.Opacity%2A> свойство. Поскольку <xref:System.Windows.UIElement.Opacity%2A> свойство относится к типу <xref:System.Double>, требуется анимацию, создающую значения типа double. Объект <xref:System.Windows.Media.Animation.DoubleAnimation> является одна анимация. Объект <xref:System.Windows.Media.Animation.DoubleAnimation> создает переход между двумя значениями типа double. Чтобы задать начальное значение, установите его <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство. Чтобы задать конечное значение, задайте его <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство.  
  
1.  Значение непрозрачности `1.0` делает объект полностью непрозрачным, а значение непрозрачности `0.0` полностью невидимым. Для анимации перехода из `1.0` для `0.0` задать его <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойства `1.0` и его <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойства `0.0`. В следующем примере показано создание <xref:System.Windows.Media.Animation.DoubleAnimation> в XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     В следующем примере показано создание <xref:System.Windows.Media.Animation.DoubleAnimation> в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  Далее необходимо указать <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Анимации определяет время, необходимое для перехода от его начального значения до его конечного значения. В следующем примере показано значение <xref:System.Windows.Media.Animation.Timeline.Duration%2A> до пяти секунд в XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     В следующем примере показано значение <xref:System.Windows.Media.Animation.Timeline.Duration%2A> пять секунд, в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  В предыдущем примере была анимации, которая переходит из `1.0` для `0.0`, что вызывает исчезают из полностью непрозрачный реализуется целевого элемента. Чтобы отобразить элемент обратно в представление после его исчезновения, установите <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойства анимации для `true`. Чтобы повторить анимацию неограниченного времени, задайте его <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойства <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. В следующем примере показано значение <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойства в XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     В следующем примере показано значение <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойствам в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Часть 2. Создание раскадровки  
 Для применения объекта анимации, необходимо создать <xref:System.Windows.Media.Animation.Storyboard> и использовать <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> присоединенного свойства для указания объекта и анимируемое свойство.  
  
1.  Создание <xref:System.Windows.Media.Animation.Storyboard> и добавьте анимации в качестве дочернего. В следующем примере показано создание <xref:System.Windows.Media.Animation.Storyboard> в XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]    
  
     Для создания <xref:System.Windows.Media.Animation.Storyboard> в коде объявите <xref:System.Windows.Media.Animation.Storyboard> переменных на уровне класса.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     Затем инициализируйте <xref:System.Windows.Media.Animation.Storyboard> и добавьте анимации в качестве дочернего.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  <xref:System.Windows.Media.Animation.Storyboard> Должен знать, где применяется анимация. Используйте <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> вложенное свойство для указания объекта для анимации. Далее показано, как присвоить имя целевого <xref:System.Windows.Media.Animation.DoubleAnimation> для `MyRectangle` в XAML.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     Далее показано, как присвоить имя целевого <xref:System.Windows.Media.Animation.DoubleAnimation> для `MyRectangle` в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  Используйте <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> присоединенного свойства для указания анимируемое свойство. Далее показано, как настроить анимацию целевой <xref:System.Windows.UIElement.Opacity%2A> свойство <xref:System.Windows.Shapes.Rectangle> в XAML.
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     Далее показано, как настроить анимацию целевой <xref:System.Windows.UIElement.Opacity%2A> свойство <xref:System.Windows.Shapes.Rectangle> в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> синтаксиса и Дополнительные примеры см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Часть 3 (XAML). Связывание раскадровки с триггером  
 Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] заключается в использовании триггер события. В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с триггером в разметке XAML.  
  
1.  Создание <xref:System.Windows.Media.Animation.BeginStoryboard> и свяжите с ним раскадровки. Объект <xref:System.Windows.Media.Animation.BeginStoryboard> — это тип <xref:System.Windows.TriggerAction> , применяется и запускает <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  Создание <xref:System.Windows.EventTrigger> и добавьте <xref:System.Windows.Media.Animation.BeginStoryboard> для его <xref:System.Windows.EventTrigger.Actions%2A> коллекции. Задать <xref:System.Windows.EventTrigger.RoutedEvent%2A> свойство <xref:System.Windows.EventTrigger> для перенаправленного события, которое вы хотите начать <xref:System.Windows.Media.Animation.Storyboard>. (Дополнительные сведения о перенаправленных событиях см. в разделе [направлено Общие сведения о событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  Добавить <xref:System.Windows.EventTrigger> для <xref:System.Windows.FrameworkElement.Triggers%2A> коллекции прямоугольника.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Часть 3 (код). Связывание раскадровки с обработчиком событий  
 Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> в коде является использование обработчика событий. В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с обработчиком событий в коде.  
  
1.  Регистрация для <xref:System.Windows.FrameworkElement.Loaded> событий прямоугольника.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  Объявите обработчик событий. В обработчике событий используйте <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод для применения раскадровки.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Полный пример  
 Ниже показано, как создать прямоугольник, который исчезает и в XAML появляется.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 Далее показано, как создать прямоугольник, который исчезает и появляется, в коде.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Типы анимации  
 Поскольку анимация создает значения свойств, для различных типов свойств существуют различные типы анимации. Для анимации свойства, которое принимает <xref:System.Double>, такие как <xref:System.Windows.FrameworkElement.Width%2A> свойства элемента, используйте анимацию, создающую <xref:System.Double> значения. Для анимации свойства, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д. Из-за количества различных типов свойств, существует несколько классов анимации в <xref:System.Windows.Media.Animation> пространства имен. Имена классов следуют строгому соглашению, благодаря чему их легко различать.  
  
-   \<*Тип*> анимации  
  
     Такая анимация называется "базовой" (или From/To/By) и производится либо от начального до конечного значения, либо посредством добавления значения смещения к начальному значению.  
  
    -   Чтобы установить начальное значение, присвойте значение свойству From анимации.  
  
    -   Чтобы установить конечное значение, присвойте значение свойству To анимации.  
  
    -   Чтобы установить значение смещения, присвойте значение свойству By анимации.  
  
     В примерах этого раздела используются анимации этого класса, поскольку они являются наиболее простыми в использовании. Анимации From/To/By подробно описываются в обзоре From/To/By анимации.  
  
-   \<*Тип*> AnimationUsingKeyFrames  
  
     Анимация с использованием ключевых кадров является более эффективным средством, чем анимация класса From/To/By, поскольку при ее использовании можно задать любое число конечных значений, а также управлять методами их интерполяции. Некоторые типы могут быть анимированы только с помощью анимации с ключевыми кадрами. Подробно описываемый кадрам [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   \<*Тип*> AnimationUsingPath  
  
     Анимация с использованием пути позволяет использовать геометрический путь для создания анимации значений.  
  
-   \<*Тип*> AnimationBase  
  
     Абстрактный класс, при реализации анимирует \< *тип*> значение. Этот класс служит базовым классом для \< *тип*> анимации и \< *тип*> AnimationUsingKeyFrames классы. Эти классы используются непосредственно только для создания пользовательской анимации. В противном случае используйте \< *тип*> анимации или ключевой кадр\<*тип*> анимации.  
  
 В большинстве случаев вы будете использовать \< *тип*> анимации классов, таких как <xref:System.Windows.Media.Animation.DoubleAnimation> и <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 В следующей таблице приведены несколько общих типов анимации, а также некоторые свойства, с которыми они используются.  
  
|Тип свойства|Соответствующая базовая (From/To/By) анимация|Соответствующая анимация с ключевыми кадрами|Соответствующая анимация с использованием пути|Пример использования|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Нет|Анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> или <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Анимация <xref:System.Windows.FrameworkElement.Width%2A> из <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.FrameworkElement.Height%2A> из <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Анимация <xref:System.Windows.Media.EllipseGeometry.Center%2A> положение <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Нет|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Нет|Анимация <xref:System.Windows.Controls.TextBlock.Text%2A> из <xref:System.Windows.Controls.TextBlock> или <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Анимации представляет собой шкалу времени  
 Все типы анимации наследуются из <xref:System.Windows.Media.Animation.Timeline> класса; таким образом, все анимации — это специальные типы из временных шкал. Объект <xref:System.Windows.Media.Animation.Timeline> определяет сегмент времени. Можно указать *временные характеристики* временной шкалы: его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, сколько раз он является, а также скорость течения времени для него.  
  
 Поскольку анимации <xref:System.Windows.Media.Animation.Timeline>, она также представляет сегмент времени. Анимации вычисляет выходных значений, по мере ее выполнения хотя его указанный сегмент времени (или <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). По мере выполнения (воспроизведения) анимации обновляется свойство, с которым она связана.  
  
 Три часто используются свойства времени <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>Свойство Duration  
 Как упоминалось ранее, временная шкала представляет собой сегмент времени. Длина этого сегмента определяется <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы, обычно задается с помощью <xref:System.Windows.Duration.TimeSpan%2A> значение. По достижении конца временной шкалы времени ее выполнение завершается.  
  
 Анимация использует его <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойства, чтобы определить его текущее значение. Если вы не укажете <xref:System.Windows.Media.Animation.Timeline.Duration%2A> значение для анимации, используется 1 секунда, используемом по умолчанию.  
  
 Ниже показана синтаксическая упрощенную версию [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] синтаксиса для атрибута <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство.  
  
*часы* `:` *минуты* `:` *секунды*
  
 В следующей таблице показаны несколько <xref:System.Windows.Duration> параметры и возвращаемые ими значения.  
  
|Параметр|Возвращаемое значение|  
|-------------|---------------------|  
|0:0:5.5|5,5 секунды.|  
|0:30:5.5|30 минут и 5,5 секунды.|  
|1:30:5.5|1 час, 30 минут и 5,5 секунды.|  
  
 Один из способов указания <xref:System.Windows.Duration> в коде является использование <xref:System.TimeSpan.FromSeconds%2A> метод для создания <xref:System.TimeSpan>, затем объявить новый <xref:System.Windows.Duration> структуру, используя <xref:System.TimeSpan>.  
  
 Дополнительные сведения о <xref:System.Windows.Duration> значения и полный [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] синтаксиса, в разделе <xref:System.Windows.Duration> структуры.  
  
#### <a name="autoreverse"></a>Свойство AutoReverse  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Свойство определяет, воспроизводится ли временная шкала обратно после достижения конца его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Если значение этого свойства анимации `true`, анимацию обращает после достижения конца его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>воспроизведение от конечного значения обратно в начальное значение. По умолчанию это свойство является `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Свойство указывает, сколько воспроизведений шкалы времени. По умолчанию временные шкалы имеют число итераций `1.0`, означающее, что воспроизведение происходит один раз и не повторяется.  
  
 Дополнительные сведения об этих и других свойствах см. в разделе [свойствах](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Применение анимации к свойству  
 В предыдущих разделах описаны различные типы анимации и их свойства времени. В этом подразделе показано, как применить анимацию к свойству. <xref:System.Windows.Media.Animation.Storyboard> объекты предоставляют один из способов применения анимации к свойствам. Объект <xref:System.Windows.Media.Animation.Storyboard> — *временная шкала контейнера* , предоставляющий сведения о содержащихся в нем анимациях.  
  
### <a name="targeting-objects-and-properties"></a>Целевые объекты и свойства  
 <xref:System.Windows.Media.Animation.Storyboard> Класс предоставляет <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> вложенные свойства. Эти свойства определяют анимируемые объекты. Чтобы использовать объект в качестве целевого объекта анимации, обычно следует присвоить ему имя.  
  
 Назначение имени для <xref:System.Windows.FrameworkElement> отличается от назначения имени <xref:System.Windows.Freezable> объекта. Большинство элементов управления и панелей являются элементами среды. Однако большинство чисто графических объектов, в том числе кисти, преобразования и геометрические объекты, являются фиксируемыми объектами. Если вы не уверены, является ли тип <xref:System.Windows.FrameworkElement> или <xref:System.Windows.Freezable>, посвящены **иерархии наследования** раздел справочной документации.  
  
-   Чтобы сделать <xref:System.Windows.FrameworkElement> целевого объекта анимации, можно присвоить ему имя, установив его <xref:System.Windows.FrameworkElement.Name%2A> свойство. В коде необходимо использовать <xref:System.Windows.FrameworkElement.RegisterName%2A> метода для регистрации имени элемента на странице, к которой он принадлежит.  
  
-   Чтобы сделать <xref:System.Windows.Freezable> объекта целевого объекта анимации в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используется [директива x: Name](../../../../docs/framework/xaml-services/x-name-directive.md) присвоить имя. В коде, просто используйте <xref:System.Windows.FrameworkElement.RegisterName%2A> метод для регистрации на странице, к которой он принадлежит объект.  
  
 В последующих разделах приводится пример присваивания имени элементу в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и код. Более подробные сведения о именования и целевых объектов см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Применение и запуск раскадровки  
 Запуск раскадровки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], необходимо связать его с <xref:System.Windows.EventTrigger>. <xref:System.Windows.EventTrigger> — Это объект, описывающий действий, предпринимаемых при возникновении указанного события. Одно из этих действий может быть <xref:System.Windows.Media.Animation.BeginStoryboard> действие, которое используется для запуска раскадровки. Триггеры событий по концепции аналогичны обработчикам событий, так как они позволяют задать реакцию приложения на конкретное событие. В отличие от обработчиков событий, триггеры событий могут быть полностью описаны в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; никакой другой код не требуется.  
  
 Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> в коде, можно использовать <xref:System.Windows.EventTrigger> или использовать <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод <xref:System.Windows.Media.Animation.Storyboard> класса.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Интерактивное управление раскадровкой  
 В предыдущем примере показан запуск <xref:System.Windows.Media.Animation.Storyboard> при возникновении события. Вы можете также управлять в интерактивном режиме <xref:System.Windows.Media.Animation.Storyboard> после ее запуска: можно приостановить, возобновить, остановить, перейти к периоду заполнения, поиска и удалить <xref:System.Windows.Media.Animation.Storyboard>. Дополнительные сведения и пример, в котором показано, как управлять в интерактивном режиме <xref:System.Windows.Media.Animation.Storyboard>, в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>Что происходит по завершении анимации?  
 <xref:System.Windows.Media.Animation.FillBehavior> Свойство определяет поведение шкалы времени по ее завершении. По умолчанию временная шкала начинает <xref:System.Windows.Media.Animation.ClockState.Filling> при ее завершении. Анимации, которая является <xref:System.Windows.Media.Animation.ClockState.Filling> содержит окончательного выходного значения.  
  
 <xref:System.Windows.Media.Animation.DoubleAnimation> В предыдущем примере не заканчивается, поскольку его <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойству <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. В следующем примере прямоугольник анимируется с помощью аналогичной анимации. В отличие от предыдущего примера <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> и <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> осталось свойств объекта анимации, значения по умолчанию. Таким образом, анимация выполняется от 1 до 0 в течение пяти секунд, а затем останавливается.  
  
 [!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Так как его <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> не был изменен со значения по умолчанию, который является <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, анимация хранит его конечное значение 0, по ее завершении. Таким образом <xref:System.Windows.UIElement.Opacity%2A> прямоугольника в 0 после анимация завершается. Если задать <xref:System.Windows.UIElement.Opacity%2A> прямоугольника с другим значением, видимых не действуют, поскольку анимации по-прежнему управляется <xref:System.Windows.UIElement.Opacity%2A> свойство.  
  
 Чтобы возвратить управления анимированного свойства в коде является использование <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод и задать значение null для <xref:System.Windows.Media.Animation.AnimationTimeline> параметра. Дополнительные сведения и пример см. в разделе [задать свойства после анимации с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Обратите внимание, что, несмотря на то, что задание значения свойства с <xref:System.Windows.Media.Animation.ClockState.Active> или <xref:System.Windows.Media.Animation.ClockState.Filling> анимации, по-видимому, не действуют, измените значение свойства. Дополнительные сведения см. в разделе [анимации и общие сведения о синхронизации системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Привязка данных и анимирование анимации  
 Большинство свойств анимации могут быть связаны с данными либо анимированы. Например, можно анимировать <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство <xref:System.Windows.Media.Animation.DoubleAnimation>. Однако в связи с особенностями работы системы времени поведение привязки данных или анимированных анимаций отличается от других случаев привязки данных и анимирования объектов. Чтобы понять их поведение, следует понять значение применения анимации к свойству.  
  
 В примере в предыдущем разделе, демонстрируется порядок анимации <xref:System.Windows.UIElement.Opacity%2A> прямоугольника. При загрузке прямоугольника в предыдущем примере, его обработчик событий применяет <xref:System.Windows.Media.Animation.Storyboard>. Система времени создает копию объекта <xref:System.Windows.Media.Animation.Storyboard> и его анимации. Эти копии фиксируются (доступным только для чтения) и <xref:System.Windows.Media.Animation.Clock> на их основе создаются объекты. Эти объекты используются для выполнения фактических действий по анимации целевых свойств.  
  
 В системе времени создаются часы для <xref:System.Windows.Media.Animation.DoubleAnimation> и применяет его к объекту и свойства, который задается параметром <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> из <xref:System.Windows.Media.Animation.DoubleAnimation>. В этом случае система времени применяет часы к <xref:System.Windows.UIElement.Opacity%2A> свойство объекта, который называется «MyRectangle».  
  
 Несмотря на то, что часы также создаются для <xref:System.Windows.Media.Animation.Storyboard>, часы не применяется к его свойствам. Он предназначен для управления его дочерних часами, которая создается для <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Для отражения анимацией привязки данных или изменений анимации следует обновить ее часы. Автоматическое повторное создание часов не выполняется. Чтобы отразить изменения в анимации, повторно примените соответствующую раскадровку с помощью <xref:System.Windows.Media.Animation.BeginStoryboard> или <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод. При использовании любого из этих методов анимация запускается повторно. В коде, можно использовать <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метода для раскадровки обратно в предыдущее положение.  
  
 Пример данных привязаны анимации, см. в разделе [Пример анимации сплайн ключ](http://go.microsoft.com/fwlink/?LinkID=160011). Дополнительные сведения о работе анимации и системы времени см. в разделе [анимации и общие сведения о синхронизации системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Другие способы анимации  
 В примерах этого раздела демонстрируется анимация с помощью раскадровок. При использовании кода можно выполнять анимацию различными способами. Дополнительные сведения см. в разделе [Общие сведения о методах анимации свойства](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Примеры анимации  
 В следующих примерах описывается порядок добавления анимации в приложения.  
  
-   [Пример целевых значений анимации From, To, By](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Описание различных параметров анимации From/To/By.  
  
-   [Пример поведения анимации с учетом времени](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Описание способов управления поведением анимации во времени. В этом примере также описывается порядок привязки данных для конечного значения анимации.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|Описывает, как система времени использует <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> классов, которые позволяют создавать анимации.|  
|[Советы и рекомендации по анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|Список полезных советов по устранению проблем с анимацией, например проблем производительности.|  
|[Общие сведения о пользовательской анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|Описание способов расширения системы анимации полными кадрами, классами анимации и покадровым обратным вызовом.|  
|Общие сведения об анимациях From/To/By|Описание способов создания анимации, которая переходит между двумя значениями.|  
|[Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|Описание способов создания анимации с несколькими целевыми значениями, включая возможность управления методом интерполяции.|  
|[Функции плавности](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|Описание способов применения математических формул к анимациям для получения реалистичного поведения, такого как подскок.|  
|[Общие сведения об анимации с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|Описание способов перемещения или поворота объекта по сложному пути.|  
|[Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|Описание анимации свойств с помощью раскадровок, локальных анимаций, часов и покадровой анимации.|  
|[Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|Описание способов использования раскадровок с несколькими временными шкалами для создания сложных анимаций.|  
|[Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|Описывает <xref:System.Windows.Media.Animation.Timeline> типы и свойства, используемые в анимации.|  
|[Общие сведения о временных событиях](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|Описывает события, доступные на <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> объекты для выполнения кода в точках на временной шкале, такие как начать, приостановить, возобновить, пропустить или остановить.|  
|[Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|Примеры кода для использования анимаций и временных шкал в приложении.|  
|[Разделы руководства, посвященные часам](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|Примеры кода для использования <xref:System.Windows.Media.Animation.Clock> объекта в приложении.|  
|[Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|Примеры кода для использования покадровой анимации в приложении.|  
|[Практические руководства, посвященные анимации по контуру](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|Примеры кода для применения анимации с использованием пути в приложении.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>
