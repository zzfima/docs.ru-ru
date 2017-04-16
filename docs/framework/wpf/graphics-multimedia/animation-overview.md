---
title: "Общие сведения об эффектах анимации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Раскадровки [WPF] анимации"
  - "анимации [WPF], общие сведения"
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
caps.latest.revision: 73
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 73
---
# Общие сведения об эффектах анимации
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет мощный набор возможностей графикой и макетом, позволяющих создавать привлекательные пользовательские интерфейсы и документы. Применение анимации позволяет сделать пользовательский интерфейс еще более наглядным и может использоваться. Анимация цвета фона или объекта <xref:System.Windows.Media.Transform>, можно создать экранных эффектов перехода или отображения визуальных подсказок.  
  
 В этом обзоре введение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации и системы управления временем. Этот раздел посвящен анимации из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектов с использованием раскадровки.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>Введение в анимацию  
 Анимация — это имитация изменений, который создается счет быстрого показа серии слегка отличающихся друг от друга изображений. Мозг воспринимает группу изображений как один изменяющуюся картинку. В фильмах такой эффект достигается создается с помощью камер, записывающих множество фотографий или кадров в секунду. При воспроизведении кадров проектором зрители видят движущееся изображение.  
  
 Аналогично анимации на компьютере. Например программа, которая выполняет рисование прямоугольника исчезновение может работать следующим образом.  
  
-   Программа создает таймер.  
  
-   Программа проверяет таймера через заданные интервалы времени, чтобы увидеть, сколько времени прошло.  
  
-   Каждый раз при проверке значения таймера вычисляется текущее значение непрозрачности для прямоугольника, в зависимости от того, сколько времени прошло.  
  
-   Затем программа обновляет прямоугольник с новым значением и перерисовывает его.  
  
 До [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] разработчикам приходилось создавать и собственные поддерживать системы управления временем либо использовать специальные пользовательские библиотеки.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]включает эффективная система контроля времени, доступных через управляемый код и [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и тесно интегрирована в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]анимация позволяет легко анимировать элементы управления и другие графические объекты.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]обрабатывает все внутренние процессы управления системой времени и перерисовки экрана эффективно. Он предоставляет классы контроля времени, позволяющие сосредоточиться на эффекты, которые вы хотите создать, а не механике их реализации.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также упрощает создание собственной анимации, обеспечивая доступ к базовым классам анимации, из которых пользовательские классы могут наследовать, для создания пользовательской анимации. Эти анимации получить преимущества производительности классов стандартных анимации.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>Система анимации свойств WPF  
 Если понять основные понятия системы управления временем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимация может быть проще в использовании. Наиболее важно то, что в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], анимация объектов осуществляется путем применения анимации к свойствам этих объектов. Например, чтобы увеличить размер элемента среды, можно анимировать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства. Чтобы скрыть объект из представления, следует анимировать его <xref:System.Windows.UIElement.Opacity%2A> свойство.  
  
 Свойство, поддерживающее анимацию она должна удовлетворять следующим трем требованиям:  
  
-   Оно должно быть свойством зависимостей.  
  
-   Он должен принадлежать класс, наследуемый от <xref:System.Windows.DependencyObject> и реализует <xref:System.Windows.Media.Animation.IAnimatable> интерфейса.  
  
-   Должны быть совместимый тип анимации доступны. (Если [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предоставляет, можно создать свой собственный. В разделе [Общие сведения о пользовательской анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]содержит множество объектов с <xref:System.Windows.Media.Animation.IAnimatable> свойства. Элементы управления, такие как <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.TabControl>, а также <xref:System.Windows.Controls.Panel> и <xref:System.Windows.Shapes.Shape> объекты наследуют от <xref:System.Windows.DependencyObject>. Большинство их свойств являются свойствами зависимостей.  
  
 Можно использовать анимации практически в любом месте, включая в стили и шаблоны элемента управления. Анимации не требуется быть визуальной; можно анимировать и объекты, не являющиеся частью пользовательского интерфейса, если они удовлетворяют условиям, которые описаны в этом разделе.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Пример: Сделать элемент исчезания и  
 В этом примере показано, как использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации для анимации значения свойства зависимостей. Он использует <xref:System.Windows.Media.Animation.DoubleAnimation>, который является типом анимации, создающий <xref:System.Double> значения для анимации <xref:System.Windows.UIElement.Opacity%2A> свойство <xref:System.Windows.Shapes.Rectangle>. В результате <xref:System.Windows.Shapes.Rectangle> исчезает и появляется.  
  
 В первой части примера создается <xref:System.Windows.Shapes.Rectangle> элемента. Описанных ниже показано, как создать анимацию и применить его к прямоугольнику <xref:System.Windows.UIElement.Opacity%2A> свойство.  
  
 Ниже показано, как создать <xref:System.Windows.Shapes.Rectangle> элемент в <xref:System.Windows.Controls.StackPanel> в XAML.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 Ниже показано, как создать <xref:System.Windows.Shapes.Rectangle> элемент в <xref:System.Windows.Controls.StackPanel> в коде.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>Часть 1: Создание DoubleAnimation  
 Один из способов сделать исчезновения и появления элемента является анимация его <xref:System.Windows.UIElement.Opacity%2A> свойство. Поскольку <xref:System.Windows.UIElement.Opacity%2A> свойство имеет тип <xref:System.Double>, требуется анимацию, создающую значения типа double. Объект <xref:System.Windows.Media.Animation.DoubleAnimation> является одна анимация. Объект <xref:System.Windows.Media.Animation.DoubleAnimation> создает переход между двумя значениями типа double. Чтобы задать начальное значение, установите его <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство. Чтобы задать конечное значение, установите его <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойства.  
  
1.  Значение непрозрачности `1.0` делает объект полностью непрозрачным, а значение непрозрачности `0.0` полностью невидимым. To make the animation transition from                                  `1.0` to                                  `0.0` you set its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to                                  `1.0` and its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property to                                  `0.0`. Ниже показано, как создать <xref:System.Windows.Media.Animation.DoubleAnimation> в XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     Ниже показано, как создать <xref:System.Windows.Media.Animation.DoubleAnimation> в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  Далее необходимо указать <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимации определяет длительность перехода от начального значения к конечному значению. Ниже показано, как присвоить <xref:System.Windows.Media.Animation.Timeline.Duration%2A> до пяти секунд в XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     Ниже показано, как присвоить <xref:System.Windows.Media.Animation.Timeline.Duration%2A> до пяти секунд в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  В предыдущем примере была анимации, которая переходит из `1.0` в `0.0`, чего исчезают из полностью непрозрачный реализуется целевого элемента. Чтобы отобразить элемент обратно в представление после его исчезновения, установите <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойства анимации к `true`. Чтобы повторить анимацию неограниченного времени, задайте его <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойства <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Ниже показано, как присвоить <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойства в XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     Ниже показано, как присвоить <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойства в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>Часть 2: Создание раскадровки  
 Чтобы применить анимацию к объекту, создайте <xref:System.Windows.Media.Animation.Storyboard> и использовать <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> прикрепленные свойства, чтобы указать объект и свойство для анимации.  
  
1.  Создание <xref:System.Windows.Media.Animation.Storyboard> и добавить анимацию в качестве дочернего. Ниже показано, как создать <xref:System.Windows.Media.Animation.Storyboard> в XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]  
  
     Для создания <xref:System.Windows.Media.Animation.Storyboard> в коде объявите <xref:System.Windows.Media.Animation.Storyboard> переменных на уровне класса.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     Затем инициализируйте <xref:System.Windows.Media.Animation.Storyboard> и добавить анимацию в качестве дочернего.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  <xref:System.Windows.Media.Animation.Storyboard> должен знать, где применяется анимация. Используйте <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> вложенное свойство для указания объекта для анимации. Ниже показано, как присвоить имя целевого <xref:System.Windows.Media.Animation.DoubleAnimation> для `MyRectangle` в XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     Ниже показано, как присвоить имя целевого <xref:System.Windows.Media.Animation.DoubleAnimation> к `MyRectangle` в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  Используйте <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> вложенного свойства, чтобы указать свойство для анимации. Далее показано, как настроить анимацию к целевому объекту <xref:System.Windows.UIElement.Opacity%2A> свойство <xref:System.Windows.Shapes.Rectangle> в XAML.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     Далее показано, как настроить анимацию к целевому объекту <xref:System.Windows.UIElement.Opacity%2A> свойство <xref:System.Windows.Shapes.Rectangle> в коде.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> синтаксиса и Дополнительные примеры см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Часть 3 (XAML): Связать раскадровки с триггера  
 Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] является использование триггера события.                          В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с триггером в разметке XAML.  
  
1.  Создание <xref:System.Windows.Media.Animation.BeginStoryboard> и свяжите с ним раскадровки. Объект <xref:System.Windows.Media.Animation.BeginStoryboard> — это тип <xref:System.Windows.TriggerAction> , применяется и запускает <xref:System.Windows.Media.Animation.Storyboard>.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  Создание <xref:System.Windows.EventTrigger> и добавьте <xref:System.Windows.Media.Animation.BeginStoryboard> для его <xref:System.Windows.EventTrigger.Actions%2A> коллекции. Задайте <xref:System.Windows.EventTrigger.RoutedEvent%2A> свойство <xref:System.Windows.EventTrigger> перенаправленное событие, которое вы хотите начать <xref:System.Windows.Media.Animation.Storyboard>. (Дополнительные сведения о маршрутизируемых событиях см. в разделе [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  Добавить <xref:System.Windows.EventTrigger> для <xref:System.Windows.FrameworkElement.Triggers%2A> коллекции прямоугольника.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Часть 3 (код): Связать раскадровку с обработчиком событий  
 Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> — это использование обработчика событий. В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с обработчиком событий в коде.  
  
1.  Регистрация для <xref:System.Windows.FrameworkElement.Loaded> событий прямоугольника.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  Объявите обработчик событий. В обработчике событий используйте <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод для применения раскадровки.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>Полный пример  
 Ниже показано, как создать прямоугольник, который исчезает и в XAML появляется.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 Ниже показано, как создать прямоугольник, который исчезает и в коде появляется.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>Типы анимации  
 Поскольку анимация создает значения свойств, для различных типов свойств существуют различные типы анимации. Для анимации свойства, которое принимает <xref:System.Double>, такие как <xref:System.Windows.FrameworkElement.Width%2A> свойства элемента, используйте анимацию, создающую <xref:System.Double> значения. Для анимации свойства, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д. Из-за количества различных типов свойств, существуют несколько классов анимации в <xref:System.Windows.Media.Animation> пространства имен. К счастью они следуют строгому правилу именования, позволяет легко различать:  
  
-   <                         *Тип*настроек анимации  
  
     Известная как «From/To/By» или «базовый» анимацию, эти анимации от начального до конечного значения, или путем добавления значения смещения к начальному значению.  
  
    -   Чтобы задать начальное значение, присвойте свойству From анимации.  
  
    -   Чтобы указать конечное значение, установите свойство To анимации.  
  
    -   Чтобы задать значение смещения, присвойте свойству By анимации.  
  
     Примеры в этом обзоре использовать эти анимации, поскольку они являются простыми в использовании. Анимация From/To/By подробно описываются в обзоре анимации From/To/By.  
  
-   <                         *Тип*настроек AnimationUsingKeyFrames  
  
     По ключевым кадрам являются большими возможностями, чем анимации From/To/By, поскольку можно указать любое количество целевых значений и даже контролировать их интерполяции. Некоторые типы могут быть анимированы только с помощью опорных кадров анимации. Подробно описаны по ключевым кадрам [сведения об анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   <                         *Тип*настроек AnimationUsingPath  
  
     Анимация с использованием пути дают возможность использовать геометрический путь для создания анимации значений.  
  
-   <                         *Тип*настроек AnimationBase  
  
     Абстрактный класс, при реализации которого анимируется <> \</> *тип*настроек значение. Этот класс служит базовым классом для <> \</> *тип*настроек анимации и <> \</> *тип*настроек AnimationUsingKeyFrames классы. Вам придется иметь дело напрямую с этими классами, только в том случае, если вы хотите создать пользовательской анимации. В противном случае, используйте <> \</> *тип*настроек анимации или ключевой кадр<>*тип*настроек анимации.  
  
 В большинстве случаев требуется использовать <> \</> *тип*настроек классов анимации, таких как <xref:System.Windows.Media.Animation.DoubleAnimation> и <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 В следующей таблице показаны несколько общих типов анимации, а также некоторые свойства, с которыми они используются.  
  
|Тип свойства|Соответствующий анимации basic (From, To и By)|Анимации соответствующих опорных кадров|Соответствующий анимации пути|Пример использования|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Нет|Animate the                                  <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a                                  <xref:System.Windows.Media.SolidColorBrush> or a                                  <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animate the                                  <xref:System.Windows.FrameworkElement.Width%2A> of a                                  <xref:System.Windows.Controls.DockPanel> or the                                  <xref:System.Windows.FrameworkElement.Height%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Анимация <xref:System.Windows.Media.EllipseGeometry.Center%2A> положение <xref:System.Windows.Media.EllipseGeometry>.|  
|<xref:System.String>|Нет|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Нет|Animate the                                  <xref:System.Windows.Controls.TextBlock.Text%2A> of a                                  <xref:System.Windows.Controls.TextBlock> or the                                  <xref:System.Windows.Controls.ContentControl.Content%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>Анимации, временные шкалы  
 Все типы анимации наследуются от класса <xref:System.Windows.Media.Animation.Timeline> класса; таким образом, все анимации, специальных типов шкал времени. Объект <xref:System.Windows.Media.Animation.Timeline> определяет сегмент времени. Можно указать *временные характеристики* временной шкалы: его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, сколько раз это, а также скорость течения времени для него.  
  
 Поскольку анимация принадлежит <xref:System.Windows.Media.Animation.Timeline>, она также представляет сегмент времени. Анимации вычисляет выходных значений, по мере его выполнения хотя сегмента указанного времени (или <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). Анимация продвигается или «воспроизведение» он обновляет свойства, связанного с ним.  
  
 Три часто используются свойства времени <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.  
  
#### <a name="the-duration-property"></a>Свойство Duration  
 Как упоминалось ранее временная шкала представляет сегмент времени. Длина этого сегмента определяется <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы, обычно задается с помощью <xref:System.Windows.Duration.TimeSpan%2A> значение. Когда временная шкала достигает конца своей длительности, его выполнение завершается.  
  
 Анимация использует его <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойства, чтобы определить его текущее значение. Если вы не укажете <xref:System.Windows.Media.Animation.Timeline.Duration%2A> значение для анимации, он использует 1 секунды, по умолчанию.  
  
 Ниже показана синтаксическая упрощенную версию [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] синтаксиса для атрибута <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство.  
  
||  
|-|  
|*hours* `:` *minutes* `:` *seconds*|  
  
 В следующей таблице показаны несколько <xref:System.Windows.Duration> параметры и возвращаемые ими значения.  
  
|Параметр|Результирующее значение|  
|-------------|---------------------|  
|0:0:5.5|5,5 секунд.|  
|0:30:5.5|30 минут и 5,5 секунд.|  
|1:30:5.5|1 час, 30 минут и 5,5 секунд.|  
  
 Один из способов задания <xref:System.Windows.Duration> в коде состоит в использовании <xref:System.TimeSpan.FromSeconds%2A> метод для создания <xref:System.TimeSpan>, затем объявить новый <xref:System.Windows.Duration> структуру, используя <xref:System.TimeSpan>.  
  
 Дополнительные сведения о <xref:System.Windows.Duration> значения и полный [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] синтаксиса, в разделе <xref:System.Windows.Duration> структуры.  
  
#### <a name="autoreverse"></a>AutoReverse  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство задает воспроизведение обратной шкалы времени после достижения конца его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Если значение этого свойства анимации `true`, обращает анимации после достижения конца его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>воспроизведение от конечного значения обратно к начальному значению. По умолчанию это свойство имеет `false`.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойство определяет количество воспроизведений шкалы времени. По умолчанию временные шкалы имеют число итераций, равное `1.0`, то есть воспроизведение происходит один раз и не повторяется.  
  
 Дополнительные сведения об этих и других свойствах см. в разделе [свойствах](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>Применение анимации к свойству  
 В предыдущих разделах описаны различные типы анимации и их свойства времени. В этом разделе показано, как применить анимацию к свойству, которое требуется анимировать.                  <xref:System.Windows.Media.Animation.Storyboard> объекты предоставляют один из способов применения анимации к свойствам. Объект <xref:System.Windows.Media.Animation.Storyboard> — *контейнера временной шкалы* , предоставляющий сведения о содержащихся в нем анимациях.  
  
### <a name="targeting-objects-and-properties"></a>Целевые объекты и свойства  
 <xref:System.Windows.Media.Animation.Storyboard> класс предоставляет <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> вложенные свойства. Задавая эти свойства анимации, определяют то, что для анимации. Однако перед анимации можно целевой объект, объект должен обычно следует присвоить имя.  
  
 Присваивание имени <xref:System.Windows.FrameworkElement> отличается от назначения имени <xref:System.Windows.Freezable> объекта. Большинство элементов управления и панелей являются элементами среды. Однако большинство чисто графических объектов, например кистей, преобразования и геометрические объекты, являются фиксируемыми объектами. Если вы не уверены, является ли тип <xref:System.Windows.FrameworkElement> или <xref:System.Windows.Freezable>, обратитесь к **иерархии наследования** разделе справочной документации.  
  
-   Чтобы сделать <xref:System.Windows.FrameworkElement> цель анимации, можно назвать ее, установив его <xref:System.Windows.FrameworkElement.Name%2A> свойства. В коде, необходимо использовать <xref:System.Windows.FrameworkElement.RegisterName%2A> метода для регистрации имени элемента на странице, к которой он принадлежит.  
  
-   Чтобы сделать <xref:System.Windows.Freezable> объекта цель анимации в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно использовать [директива x: Name](../../../../docs/framework/xaml-services/x-name-directive.md) присвоить имя. В коде, можно просто использовать <xref:System.Windows.FrameworkElement.RegisterName%2A> метод для регистрации объекта на странице, к которой он принадлежит.  
  
 В последующих разделах приводится пример присваивания имени элементу в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и код. Более подробные сведения об именовании и предназначенные для просмотра [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="applying-and-starting-storyboards"></a>Применение и запуск раскадровки  
 Чтобы запустить раскадровку [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], необходимо связать его с <xref:System.Windows.EventTrigger>. <xref:System.Windows.EventTrigger> — это объект, с описанием действий, предпринимаемых при возникновении указанного события. Одно из этих действий может быть <xref:System.Windows.Media.Animation.BeginStoryboard> действия, которое используется для запуска раскадровки. Триггеры событий, сходны по замыслу обработчикам событий, так как они позволяют указать, как приложение реагирует на определенное событие. В отличие от обработчиков событий, триггеры событий могут быть полностью описаны в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; никакого другого кода не требуется.  
  
 Для запуска <xref:System.Windows.Media.Animation.Storyboard> в коде, можно использовать <xref:System.Windows.EventTrigger> или <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод <xref:System.Windows.Media.Animation.Storyboard> класса.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>Интерактивное управление раскадровкой  
 В предыдущем примере показан запуск <xref:System.Windows.Media.Animation.Storyboard> происходит определенное событие. Можно также интерактивно управлять <xref:System.Windows.Media.Animation.Storyboard> после ее запуска: можно приостановить, возобновить, остановить, перейти к периоду заполнения, поиска и удаления <xref:System.Windows.Media.Animation.Storyboard>. Дополнительные сведения и пример, в котором показано, как для интерактивного управления <xref:System.Windows.Media.Animation.Storyboard>, в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>Что происходит после окончания анимации?  
 <xref:System.Windows.Media.Animation.FillBehavior> свойство определяет поведение шкалы времени по ее завершении. По умолчанию запускается временная шкала <xref:System.Windows.Media.Animation.ClockState> при ее окончании. Анимацию, которая является <xref:System.Windows.Media.Animation.ClockState> содержит его значение конечного результата.  
  
 <xref:System.Windows.Media.Animation.DoubleAnimation> в предыдущем примере не заканчивается, поскольку его <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойству <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. В следующем примере прямоугольник анимируется с помощью аналогичной анимации. В отличие от предыдущего примера <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> и <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойства этой анимации остаются значения по умолчанию. Таким образом анимация выполняется от 1 до 0 в течение пяти секунд, а затем останавливается.  
  
 [!code-xml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 Так как его <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> не был изменен со значением по умолчанию, который является <xref:System.Windows.Media.Animation.FillBehavior>, анимация хранит его конечное значение 0, при ее завершении. Таким образом <xref:System.Windows.UIElement.Opacity%2A> прямоугольника в 0 после анимация завершается. Если задать <xref:System.Windows.UIElement.Opacity%2A> прямоугольника с другим значением, код отображается не действовать так, как анимация по-прежнему управляется <xref:System.Windows.UIElement.Opacity%2A> свойство.  
  
 Чтобы возвратить управление анимированного свойства в коде является использование <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод и указать значение null для <xref:System.Windows.Media.Animation.AnimationTimeline> параметр. Дополнительные сведения и пример см. в разделе [задать свойства после анимации с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md).  
  
 Обратите внимание, что, несмотря на то, что задание значения свойства с <xref:System.Windows.Media.Animation.ClockState> или <xref:System.Windows.Media.Animation.ClockState> анимация будет не действовать, измените значение свойства. Дополнительные сведения см. в разделе [анимации и обзор системы времени](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>Привязка данных и анимирование анимации  
 Большинство свойств анимации могут быть связаны с данными либо анимированы. Например, можно анимировать <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство <xref:System.Windows.Media.Animation.DoubleAnimation>. Тем не менее из-за способа работы системы времени, данные привязанного или анимированных анимаций не ведут себя так, как и другие данные привязаны или анимированных объектов. Чтобы понять их поведение, полезно понять, что означает применить анимацию к свойству.  
  
 В примере в предыдущем разделе, демонстрируется порядок анимации <xref:System.Windows.UIElement.Opacity%2A> прямоугольника. При загрузке прямоугольника в предыдущем примере его обработчик событий применяет <xref:System.Windows.Media.Animation.Storyboard>. Система времени создает копию <xref:System.Windows.Media.Animation.Storyboard> и его анимации. Эти копии фиксируются (доступным только для чтения) и <xref:System.Windows.Media.Animation.Clock> на их основе создаются объекты. Эти часы производят фактическую работу по анимации целевых свойств.  
  
 В системе времени создаются часы для <xref:System.Windows.Media.Animation.DoubleAnimation> и применяет его к объекту и свойству, определяемый <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> из <xref:System.Windows.Media.Animation.DoubleAnimation>. В этом случае система времени применяет часы к <xref:System.Windows.UIElement.Opacity%2A> свойство объекта, который называется «MyRectangle».  
  
 Несмотря на то, что часы также создаются для <xref:System.Windows.Media.Animation.Storyboard>, часы не применяется к его свойствам. Он предназначен для управления его дочерних часами, которые создаются для <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Для отражения анимацией привязки данных или анимации изменений необходимо повторно ее часы. Часы не воссоздаются для вас автоматически. Чтобы отразить изменения в анимации, повторно примените соответствующую раскадровку с помощью <xref:System.Windows.Media.Animation.BeginStoryboard> или <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод. При использовании любого из этих методов анимация запускается повторно. В коде, можно использовать <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метода для раскадровки обратно в предыдущее положение.  
  
 Пример данных привязаны анимации, см. в разделе [Пример анимации сплайн ключ](http://go.microsoft.com/fwlink/?LinkID=160011).                  Дополнительные сведения о работе анимации и системы времени см. в разделе [анимации и обзор системы времени](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>Другие способы анимации  
 В примерах этого раздела показано, как для анимации с помощью раскадровки. При использовании кода можно анимировать несколькими способами. Дополнительные сведения см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>Примеры анимации  
 Следующие примеры, которые могут помочь начать добавление анимации в приложениях.  
  
-   [FROM, To и пример целевых значений анимации](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     Показывает параметры различных From, To и By.  
  
-   [Пример времени поведения анимации](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     Описание способов можно управлять поведением времени анимации. В этом примере также показан порядок привязки данных для конечного значения анимации.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Анимации и обзор системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|Описывает, как система управления временем использует <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> классов, которые позволяют создавать анимации.|  
|[Анимация советы и рекомендации](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|Список полезных советов по устранению проблем с анимацией, например производительность.|  
|[Общие сведения о пользовательской анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|Описание способов расширения системы с помощью ключевых кадров, классы анимации или обратных вызовов кадров анимации.|  
|Общие сведения об анимациях From/To/By|Описание способов создания анимации, которая переходит между двумя значениями.|  
|[Общие сведения об анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|Описание способов создания анимации с несколькими целевыми значениями, включая возможность управления методом интерполяции.|  
|[Функции плавности](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|Описание способов применения математических формул для анимаций для получения реалистичного поведения, такие как прыгать.|  
|[Общие сведения об анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|Описание способов перемещения или поворота объекта по сложному пути.|  
|[Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|Описывает свойства анимации с помощью раскадровки, локальные анимации, часы и покадровая анимация.|  
|[Общие сведения о раскадровках](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|Описание способов использования раскадровок с несколькими временными шкалами для создания сложных анимаций.|  
|[Свойствах](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|Описывает <xref:System.Windows.Media.Animation.Timeline> типов и свойств, используемых в анимации.|  
|[Общие сведения о событиях времени](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|Описание событий, доступных в <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> объектов для выполнения кода в точках временной шкалы, такие как начать, приостановить, возобновить, пропустить или остановить.|  
|[Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|Содержит примеры кода для использования в приложении анимации и временной шкалы.|  
|[Разделы руководства, посвященные часы](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|Примеры кода для использования <xref:System.Windows.Media.Animation.Clock> объект в приложении.|  
|[Разделы руководства по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|Содержит примеры кода для использования покадровой анимации в приложении.|  
|[Разделы руководства, посвященные анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|Содержит примеры кода для использования анимация с использованием пути в приложении.|  
  
<a name="reference"></a>   
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>