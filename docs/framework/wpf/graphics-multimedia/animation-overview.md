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
ms.openlocfilehash: f0f55c948d10c61ebab57f47e3461531ccf5f610
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559720"
---
# <a name="animation-overview"></a>Общие сведения об эффектах анимации

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет мощный набор функций для работы с графикой и макетом, позволяющий создавать привлекательные пользовательские интерфейсы и привлекательные документы. Применение анимации позволяет сделать пользовательский интерфейс еще более наглядным и удобным в использовании. Просто анимировать цвет фона или применить анимированный <xref:System.Windows.Media.Transform>, вы можете создавать значительные переходы экрана или предоставлять полезные визуальные подсказки.

В этом обзоре содержатся общие сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации и системе управления временем. Он посвящен анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектов с помощью раскадровок.

<a name="introducinganimations"></a>

## <a name="introducing-animations"></a>Введение в анимацию

Анимация — это имитация изменений, которая обеспечивается быстрым показом серии слегка отличающихся друг от друга изображений. Мозг человека воспринимает набор изображений как одну непрерывно изменяющуюся картинку. В фильме эта имитация создается за счет применения камер, записывающих множество фотографий (кадров) в секунду. При воспроизведении кадров проектором зрители видят движущееся изображение.

Анимация на компьютере выполняется по аналогичному принципу. Например, программа, в которой реализуется исчезновение прямоугольника, может работать следующим образом.

- В программе создается таймер.

- Через заданные временные интервалы проверяется значение таймера для определения истекшего времени.

- При каждой проверке значения таймера вычисляется текущее значение непрозрачности для прямоугольника в зависимости от прошедшего времени.

- Затем программа обновляет прямоугольник с использованием нового значения и перерисовывает его.

Прежде чем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], разработчикам Microsoft Windows пришлось создавать собственные системы управления временем и управлять ими, а также использовать специальные пользовательские библиотеки. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержит эффективную систему управления временем, доступную через управляемый код и [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и тесно интегрированную в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ную платформу. Анимация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] упрощает анимацию элементов управления и других графических объектов.

В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эффективно осуществляются все внутренние процессы управления системой времени и перерисовки экрана. Предоставляются классы контроля времени, позволяющие сосредоточиться на создаваемых эффектах, а не на механике их реализации. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также упрощает создание собственной анимации, предоставляя доступ к базовым классам анимации, из которых пользовательские классы могут наследовать средства создания пользовательской анимации. По сравнению со стандартными пользовательские классы анимации обеспечивают большое преимущество в производительности.

<a name="thewpftimingsystem"></a>

## <a name="wpf-property-animation-system"></a>Система анимации свойств WPF

Если вы понимаете несколько важных концепций системы управления временем, удобнее использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации. Самое важное заключается в том, что в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]анимация объектов осуществляется путем применения анимации к отдельным свойствам. Например, чтобы увеличить элемент платформы, можно анимировать его свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>. Чтобы сделать объект эффектным от представления, можно анимировать его свойство <xref:System.Windows.UIElement.Opacity%2A>.

Свойство, поддерживающее анимацию, должно удовлетворять следующим трем требованиям.

- Свойство является свойством зависимостей.

- Он должен принадлежать классу, который наследуется от <xref:System.Windows.DependencyObject> и реализует интерфейс <xref:System.Windows.Media.Animation.IAnimatable>.

- Доступен совместимый тип анимации. (Если [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предоставляет его, можно создать собственный. См. раздел [Общие сведения о пользовательской анимации](custom-animations-overview.md).)

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержит множество объектов, которые имеют свойства <xref:System.Windows.Media.Animation.IAnimatable>. Такие элементы управления, как <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.TabControl>, а также <xref:System.Windows.Controls.Panel> и <xref:System.Windows.Shapes.Shape> объекты наследуют от <xref:System.Windows.DependencyObject>. Большинство их свойств являются свойствами зависимостей.

Анимацию можно использовать практически везде, где используются стили и шаблоны элементов управления. Анимация не обязательно должна быть визуальной; можно анимировать и объекты, не являющиеся частью пользовательского интерфейса, если они соответствуют описанным в этом разделе условиям.

<a name="storyboardwalkthrough"></a>

## <a name="example-make-an-element-fade-in-and-out-of-view"></a>Пример. Реализация исчезновения и появления элемента

В этом примере показано, как использовать анимацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для анимации значения свойства зависимостей. Он использует <xref:System.Windows.Media.Animation.DoubleAnimation>, который является типом анимации, создающей <xref:System.Double> значения, для анимации свойства <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Shapes.Rectangle>. В результате <xref:System.Windows.Shapes.Rectangle> исчезает и выходит из представления.

В первой части примера создается элемент <xref:System.Windows.Shapes.Rectangle>. Ниже показано, как создать анимацию и применить ее к свойству <xref:System.Windows.UIElement.Opacity%2A> прямоугольника.

Ниже показано, как создать элемент <xref:System.Windows.Shapes.Rectangle> в <xref:System.Windows.Controls.StackPanel> в XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]

Ниже показано, как создать элемент <xref:System.Windows.Shapes.Rectangle> в <xref:System.Windows.Controls.StackPanel> в коде.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]

<a name="opacity_animation_step1"></a>

### <a name="part-1-create-a-doubleanimation"></a>Часть 1. Создание объекта DoubleAnimation

Одним из способов сделать элемент недоступным для просмотра является анимация его свойства <xref:System.Windows.UIElement.Opacity%2A>. Так как свойство <xref:System.Windows.UIElement.Opacity%2A> имеет тип <xref:System.Double>, требуется анимация, создающая значения типа Double. Одной из таких анимаций является <xref:System.Windows.Media.Animation.DoubleAnimation>. <xref:System.Windows.Media.Animation.DoubleAnimation> создает переход между двумя значениями типа Double. Чтобы указать его начальное значение, необходимо задать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>. Чтобы указать конечное значение, необходимо задать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.

1. Значение непрозрачности `1.0` делает объект полностью непрозрачным, а значение непрозрачности `0.0` делает его полностью невидимым. Чтобы переход анимации с `1.0` на `0.0` вы установили для свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значение `1.0`, а для свойства <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> — значение `0.0`. Ниже показано, как создать <xref:System.Windows.Media.Animation.DoubleAnimation> в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]

    Ниже показано, как создать <xref:System.Windows.Media.Animation.DoubleAnimation> в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]

2. Далее необходимо указать <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимации указывает время перехода от начального значения к целевому значению. Ниже показано, как задать для <xref:System.Windows.Media.Animation.Timeline.Duration%2A> значение 5 секунд в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]

    Ниже показано, как установить <xref:System.Windows.Media.Animation.Timeline.Duration%2A> в течение пяти секунд в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]

3. Предыдущий код показал анимацию, которая переходит с `1.0` на `0.0`, что приводит к исчезновению целевого элемента от полностью непрозрачного до полного невидимого. Чтобы вернуть элемент в представление после исчезновения, установите для свойства <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> анимации значение `true`. Чтобы сделать анимацию неопределенной, установите для свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> значение <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. Ниже показано, как задать свойства <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]

    Ниже показано, как задать свойства <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]

<a name="opacity_animation_step2"></a>

### <a name="part-2-create-a-storyboard"></a>Часть 2. Создание раскадровки

Чтобы применить анимацию к объекту, создайте <xref:System.Windows.Media.Animation.Storyboard> и используйте присоединенные свойства <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty>, чтобы указать объект и свойство для анимации.

1. Создайте <xref:System.Windows.Media.Animation.Storyboard> и добавьте анимацию в качестве дочерней. Ниже показано, как создать <xref:System.Windows.Media.Animation.Storyboard> в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]

    Чтобы создать <xref:System.Windows.Media.Animation.Storyboard> в коде, объявите переменную <xref:System.Windows.Media.Animation.Storyboard> на уровне класса.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]

    Затем инициализируйте <xref:System.Windows.Media.Animation.Storyboard> и добавьте анимацию в качестве дочернего элемента.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]

2. <xref:System.Windows.Media.Animation.Storyboard> необходимо указать, куда применять анимацию. Используйте присоединенное свойство <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType>, чтобы указать объект для анимации. Ниже показано, как задать целевое имя <xref:System.Windows.Media.Animation.DoubleAnimation> для `MyRectangle` в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]

    Ниже показано, как задать целевое имя <xref:System.Windows.Media.Animation.DoubleAnimation> для `MyRectangle` в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]

3. Используйте присоединенное свойство <xref:System.Windows.Media.Animation.Storyboard.TargetProperty>, чтобы указать свойство для анимации. Ниже показано, как настроить анимацию для свойства <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Shapes.Rectangle> в XAML.

    [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]

    Ниже показано, как настроить анимацию для свойства <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Shapes.Rectangle> в коде.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]

Дополнительные сведения о синтаксисе <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> и дополнительные примеры см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).

<a name="opacity_animation_step3"></a>

### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>Часть 3 (XAML). Связывание раскадровки с триггером

Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] — использовать триггер события. В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с триггером в XAML.

1. Создайте объект <xref:System.Windows.Media.Animation.BeginStoryboard> и свяжите с ним раскадровку. <xref:System.Windows.Media.Animation.BeginStoryboard> — это тип <xref:System.Windows.TriggerAction>, который применяет и запускает <xref:System.Windows.Media.Animation.Storyboard>.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]

2. Создайте <xref:System.Windows.EventTrigger> и добавьте <xref:System.Windows.Media.Animation.BeginStoryboard> в коллекцию <xref:System.Windows.EventTrigger.Actions%2A>. Задайте для свойства <xref:System.Windows.EventTrigger.RoutedEvent%2A> <xref:System.Windows.EventTrigger> перенаправленное событие, которое необходимо запустить <xref:System.Windows.Media.Animation.Storyboard>. (Дополнительные сведения о перенаправленных событиях см. в разделе [Общие сведения о перенаправленных событиях](../advanced/routed-events-overview.md).)

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]

3. Добавьте <xref:System.Windows.EventTrigger> в коллекцию <xref:System.Windows.FrameworkElement.Triggers%2A> прямоугольника.

    [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]

<a name="opacity_animation_step3code"></a>

### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>Часть 3 (код). Связывание раскадровки с обработчиком событий

Самый простой способ применить и запустить <xref:System.Windows.Media.Animation.Storyboard> в коде — использовать обработчик событий. В этом разделе показано, как связать <xref:System.Windows.Media.Animation.Storyboard> с обработчиком событий в коде.

1. Зарегистрируйтесь для <xref:System.Windows.FrameworkElement.Loaded>ного события прямоугольника.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]

2. Объявите обработчик событий. В обработчике событий используйте метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>, чтобы применить раскадровку.

    [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
    [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]

### <a name="complete-example"></a>Полный пример

Ниже показано, как создать прямоугольник, который исчезает и выходит из представления в XAML.

[!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]

Далее показано, как создать прямоугольник, который исчезает и появляется, в коде.

[!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
[!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]

<a name="animationtypes"></a>

## <a name="animation-types"></a>Типы анимации

Поскольку анимация создает значения свойств, для различных типов свойств существуют различные типы анимации. Чтобы анимировать свойство, которое принимает <xref:System.Double>, например свойство <xref:System.Windows.FrameworkElement.Width%2A> элемента, используйте анимацию, которая создает значения <xref:System.Double>. Чтобы анимировать свойство, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д. Из-за количества различных типов свойств в <xref:System.Windows.Media.Animation> пространстве имен существует несколько классов анимации. Имена классов следуют строгому соглашению, благодаря чему их легко различать.

- \<*Type*>Animation

  Такая анимация называется "базовой" (или From/To/By) и производится либо от начального до конечного значения, либо посредством добавления значения смещения к начальному значению.

  - Чтобы установить начальное значение, присвойте значение свойству From анимации.

  - Чтобы установить конечное значение, присвойте значение свойству To анимации.

  - Чтобы установить значение смещения, присвойте значение свойству By анимации.

  В примерах этого раздела используются анимации этого класса, поскольку они являются наиболее простыми в использовании. Сведения об анимации From/To/By подробно описаны в обзоре анимации From/To/By.

- \<*Type*>AnimationUsingKeyFrames

  Анимация с использованием ключевых кадров является более эффективным средством, чем анимация класса From/To/By, поскольку при ее использовании можно задать любое число конечных значений, а также управлять методами их интерполяции. Некоторые типы могут быть анимированы только с помощью анимации с ключевыми кадрами. Анимация по ключевым кадрам подробно описана в разделе [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).

- \<*Type*>AnimationUsingPath

  Анимация с использованием пути позволяет использовать геометрический путь для создания анимации значений.

- \<*Type*>AnimationBase

  Абстрактный класс, при реализации которого анимируется значение типа \<*Type*>. Этот класс служит базовым классом для классов \<*Type*>Animation и \<*Type*>AnimationUsingKeyFrames. Эти классы используются непосредственно только для создания пользовательской анимации. В противном случае следует использовать классы \<*Type*>Animation или KeyFrame\<*Type*>Animation.

В большинстве случаев потребуется использовать \<*тип*> класс анимации, например <xref:System.Windows.Media.Animation.DoubleAnimation> и <xref:System.Windows.Media.Animation.ColorAnimation>.

В следующей таблице приведены несколько общих типов анимации, а также некоторые свойства, с которыми они используются.

|Тип свойства|Соответствующая базовая (From/To/By) анимация|Соответствующая анимация с ключевыми кадрами|Соответствующая анимация с использованием пути|Пример использования|
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Нет|Анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush> или <xref:System.Windows.Media.GradientStop>.|
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Анимация <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.Button>.|
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|Анимация <xref:System.Windows.Media.EllipseGeometry.Center%2A> расположения <xref:System.Windows.Media.EllipseGeometry>.|
|<xref:System.String>|Нет|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Нет|Анимация <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock> или <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Button>.|

<a name="animationsaretimelines"></a>

### <a name="animations-are-timelines"></a>Анимации представляет собой шкалу времени

Все типы анимации наследуются от класса <xref:System.Windows.Media.Animation.Timeline>; Таким образом, все анимации являются специализированными типами временных шкал. <xref:System.Windows.Media.Animation.Timeline> определяет сегмент времени. Можно указать *временные характеристики* временной шкалы: ее <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, количество повторений и даже время, в течение которого она выполняется.

Поскольку анимация является <xref:System.Windows.Media.Animation.Timeline>, она также представляет сегмент времени. Анимация также вычисляет выходные значения по мере продвижения по заданному сегменту времени (или <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). По мере выполнения (воспроизведения) анимации обновляется свойство, с которым она связана.

Три часто используемых свойства времени: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>и <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>.

#### <a name="the-duration-property"></a>Свойство Duration

Как упоминалось ранее, временная шкала представляет собой сегмент времени. Длина этого сегмента определяется <xref:System.Windows.Media.Animation.Timeline.Duration%2A> временной шкалы, которая обычно указывается с помощью <xref:System.Windows.Duration.TimeSpan%2A> значения. По достижении конца временной шкалы времени ее выполнение завершается.

Для определения текущего значения анимации используется свойство <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Если для анимации не указано значение <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, используется по умолчанию 1 секунда.

Следующий синтаксис демонстрирует упрощенную версию синтаксиса атрибута [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для свойства <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.

*часов* `:` *минут* `:` *секунд*

В следующей таблице показано несколько параметров <xref:System.Windows.Duration> и их результирующих значений.

|Параметр|Возвращаемое значение|
|-------------|---------------------|
|0:0:5.5|5,5 секунды.|
|0:30:5.5|30 минут и 5,5 секунды.|
|1:30:5.5|1 час, 30 минут и 5,5 секунды.|

Одним из способов указания <xref:System.Windows.Duration> в коде является использование метода <xref:System.TimeSpan.FromSeconds%2A> для создания <xref:System.TimeSpan>, а затем объявление новой структуры <xref:System.Windows.Duration> с помощью <xref:System.TimeSpan>.

Дополнительные сведения о <xref:System.Windows.Duration> значениях и полном синтаксисе [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] см. в разделе Структура <xref:System.Windows.Duration>.

#### <a name="autoreverse"></a>Свойство AutoReverse

Свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> указывает, будет ли временная шкала воспроизводиться назад после достижения конца <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Если задать для этого свойства анимации значение `true`, анимация будет отменяться после достижения конца <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, начиная с ее конечного значения и заканчивая начальным значением. По умолчанию это свойство имеет значение `false`.

#### <a name="repeatbehavior"></a>RepeatBehavior

Свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> указывает, сколько раз будет воспроизводиться временная шкала. По умолчанию временные шкалы имеют число итераций `1.0`. Это означает, что они воспроизводятся один раз и не повторяются.

Дополнительные сведения об этих свойствах и других см. в разделе [Общие сведения о поведении времени](timing-behaviors-overview.md).

<a name="applyanimationstoproperty"></a>

## <a name="applying-an-animation-to-a-property"></a>Применение анимации к свойству

В предыдущих разделах описаны различные типы анимации и их свойства времени. В этом подразделе показано, как применить анимацию к свойству. <xref:System.Windows.Media.Animation.Storyboard> объекты предоставляют один из способов применения анимации к свойствам. <xref:System.Windows.Media.Animation.Storyboard> — это *временная шкала контейнера* , которая предоставляет сведения о целевой информации для содержащихся в ней анимаций.

### <a name="targeting-objects-and-properties"></a>Целевые объекты и свойства

Класс <xref:System.Windows.Media.Animation.Storyboard> предоставляет <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> вложенные свойства. Эти свойства определяют анимируемые объекты. Чтобы использовать объект в качестве целевого объекта анимации, обычно следует присвоить ему имя.

Присвоение имени <xref:System.Windows.FrameworkElement> отличается от присвоения имени объекту <xref:System.Windows.Freezable>. Большинство элементов управления и панелей являются элементами среды. Однако большинство чисто графических объектов, в том числе кисти, преобразования и геометрические объекты, являются фиксируемыми объектами. Если вы не уверены, является ли тип <xref:System.Windows.FrameworkElement> или <xref:System.Windows.Freezable>, см. раздел **Иерархия наследования** в справочной документации.

- Чтобы создать <xref:System.Windows.FrameworkElement> цели анимации, присвойте ей имя, задав его свойство <xref:System.Windows.FrameworkElement.Name%2A>. В коде также необходимо использовать метод <xref:System.Windows.FrameworkElement.RegisterName%2A>, чтобы зарегистрировать имя элемента со страницей, к которой он принадлежит.

- Чтобы сделать объект <xref:System.Windows.Freezable> целевым объектом анимации в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте [директиву x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) , чтобы присвоить ей имя. В коде просто используется метод <xref:System.Windows.FrameworkElement.RegisterName%2A> для регистрации объекта со страницей, к которой он принадлежит.

В следующих разделах приводится пример именования элемента в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и коде. Более подробные сведения об именовании и нацеливании см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).

### <a name="applying-and-starting-storyboards"></a>Применение и запуск раскадровки

Чтобы запустить раскадровку в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], свяжите ее с <xref:System.Windows.EventTrigger>. <xref:System.Windows.EventTrigger> — это объект, который описывает действия, выполняемые при наступлении указанного события. Одно из этих действий может быть <xref:System.Windows.Media.Animation.BeginStoryboard> действием, которое используется для запуска раскадровки. Триггеры событий по концепции аналогичны обработчикам событий, так как они позволяют задать реакцию приложения на конкретное событие. В отличие от обработчиков событий, триггеры событий можно полностью описать в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; никакой другой код не требуется.

Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> в коде, можно использовать <xref:System.Windows.EventTrigger> или использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> класса <xref:System.Windows.Media.Animation.Storyboard>.

<a name="controllingstoryboards"></a>

## <a name="interactively-control-a-storyboard"></a>Интерактивное управление раскадровкой

В предыдущем примере показано, как запустить <xref:System.Windows.Media.Animation.Storyboard> при возникновении события. Можно также интерактивно управлять <xref:System.Windows.Media.Animation.Storyboard> после запуска: вы можете приостановить, возобновить, остановить, перейти к его периоду заполнения, найти и удалить <xref:System.Windows.Media.Animation.Storyboard>. Дополнительные сведения и пример, демонстрирующий интерактивное управление <xref:System.Windows.Media.Animation.Storyboard>, см. в разделе [Общие сведения о раскадровках](storyboards-overview.md).

<a name="fillbehaviorsection"></a>

## <a name="what-happens-after-an-animation-ends"></a>Что происходит по завершении анимации?

Свойство <xref:System.Windows.Media.Animation.FillBehavior> указывает, как ведет себя временная шкала при ее завершении. По умолчанию временная шкала начинается <xref:System.Windows.Media.Animation.ClockState.Filling> по завершении. Анимация, <xref:System.Windows.Media.Animation.ClockState.Filling>, содержит конечное выходное значение.

<xref:System.Windows.Media.Animation.DoubleAnimation> в предыдущем примере не заканчивается, так как свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> имеет значение <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>. В следующем примере прямоугольник анимируется с помощью аналогичной анимации. В отличие от предыдущего примера, свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> и <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> этой анимации остаются в значениях по умолчанию. Таким образом, анимация выполняется от 1 до 0 в течение пяти секунд, а затем останавливается.

[!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]

[!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
[!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]

Поскольку его <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> не были изменены по умолчанию, что <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, анимация сохраняет свое окончательное значение 0 при завершении. Таким образом, <xref:System.Windows.UIElement.Opacity%2A> прямоугольника остается в 0 после окончания анимации. Если задать для <xref:System.Windows.UIElement.Opacity%2A> прямоугольника другое значение, код не будет оказывать никакого влияния, так как анимация по-прежнему влияет на свойство <xref:System.Windows.UIElement.Opacity%2A>.

Одним из способов восстановить управление анимированным свойством в коде является использование метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> и указание значения NULL для параметра <xref:System.Windows.Media.Animation.AnimationTimeline>. Дополнительные сведения и пример см. в разделе [Задание свойства после его анимации с помощью раскадровки](how-to-set-a-property-after-animating-it-with-a-storyboard.md).

Обратите внимание, что, несмотря на то, что задание значения свойства с <xref:System.Windows.Media.Animation.ClockState.Active> или <xref:System.Windows.Media.Animation.ClockState.Filling> анимация не оказывает никакого влияния, значение свойства изменяется. Дополнительные сведения см. в разделе [Обзор анимации и системы управления временем](animation-and-timing-system-overview.md).

<a name="databindingAndAnimatingAnimationsSection"></a>

## <a name="data-binding-and-animating-animations"></a>Привязка данных и анимирование анимации

Большинство свойств анимации могут быть привязанными к данным или анимированными. Например, можно анимировать свойство <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation>. Однако в связи с особенностями работы системы времени поведение привязки данных или анимированных анимаций отличается от других случаев привязки данных и анимирования объектов. Чтобы понять их поведение, следует понять значение применения анимации к свойству.

См. пример в предыдущем разделе, в котором показано, как анимировать <xref:System.Windows.UIElement.Opacity%2A> прямоугольника. При загрузке прямоугольника в предыдущем примере его триггер события применяет <xref:System.Windows.Media.Animation.Storyboard>. Система времени создает копию <xref:System.Windows.Media.Animation.Storyboard> и ее анимацию. Эти копии заморожены (доступны только для чтения), а объекты <xref:System.Windows.Media.Animation.Clock> создаются из них. Эти объекты используются для выполнения фактических действий по анимации целевых свойств.

Система времени создает часы для <xref:System.Windows.Media.Animation.DoubleAnimation> и применяет ее к объекту и свойству, заданному <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> <xref:System.Windows.Media.Animation.DoubleAnimation>. В этом случае система времени применяет часы к свойству <xref:System.Windows.UIElement.Opacity%2A> объекта с именем «Миректангле».

Хотя для <xref:System.Windows.Media.Animation.Storyboard>также создаются часы, часы не применяются к свойствам. Он предназначен для управления дочерними часами, часов, созданных для <xref:System.Windows.Media.Animation.DoubleAnimation>.

Для отражения анимацией привязки данных или изменений анимации следует обновить ее часы. Автоматическое обновление часов не поддерживается. Чтобы анимация отражала изменения, повторно примените ее раскадровку с помощью <xref:System.Windows.Media.Animation.BeginStoryboard> или метода <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>. При использовании любого из этих методов анимация запускается повторно. В коде можно использовать метод <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>, чтобы переместить раскадровку обратно в предыдущую точку.

Пример анимации с привязкой к данным см. в разделе [Пример анимации по ключевым сплайнам](https://go.microsoft.com/fwlink/?LinkID=160011). Дополнительные сведения о работе анимации и системы управления временем см. в разделе [Общие сведения об анимации и системе](animation-and-timing-system-overview.md)управления временем.

<a name="otherWaysToAnimateSection"></a>

## <a name="other-ways-to-animate"></a>Другие способы анимации

В примерах этого раздела демонстрируется анимация с помощью раскадровок. При использовании кода можно выполнять анимацию различными способами. Дополнительные сведения см. в статье [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md).

<a name="animation_samples"></a>

## <a name="animation-samples"></a>Примеры анимации

В следующих примерах описывается порядок добавления анимации в приложения.

- [Пример целевых значений анимации From, To и By](https://go.microsoft.com/fwlink/?LinkID=159988)

  Описание различных параметров анимации From/To/By.

- [Пример поведения анимации с учетом времени](https://go.microsoft.com/fwlink/?LinkID=159970)

  Описание способов управления поведением анимации во времени. В этом примере также описывается порядок привязки данных для конечного значения анимации.

<a name="related_topics"></a>

## <a name="related-topics"></a>Связанные разделы

|Заголовок|Описание|
|-----------|-----------------|
|[Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md)|Описывает, как система управления временем использует классы <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock>, которые позволяют создавать анимации.|
|[Советы и рекомендации по анимации](animation-tips-and-tricks.md)|Список полезных советов по устранению проблем с анимацией, например проблем производительности.|
|[Общие сведения о пользовательской анимации](custom-animations-overview.md)|Описание способов расширения системы анимации полными кадрами, классами анимации и покадровым обратным вызовом.|
|[Общие сведения об анимациях From, To и By](from-to-by-animations-overview.md)|Описание способов создания анимации, которая переходит между двумя значениями.|
|[Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)|Описание способов создания анимации с несколькими целевыми значениями, включая возможность управления методом интерполяции.|
|[Функции плавности](easing-functions.md)|Описание способов применения математических формул к анимациям для получения реалистичного поведения, такого как подскок.|
|[Общие сведения об анимации с использованием пути](path-animations-overview.md)|Описание способов перемещения или поворота объекта по сложному пути.|
|[Общие сведения о методах анимации свойств](property-animation-techniques-overview.md)|Описание анимации свойств с помощью раскадровок, локальных анимаций, часов и покадровой анимации.|
|[Общие сведения о раскадровке](storyboards-overview.md)|Описание способов использования раскадровок с несколькими временными шкалами для создания сложных анимаций.|
|[Общие сведения о характере поведения во времени](timing-behaviors-overview.md)|Описывает типы <xref:System.Windows.Media.Animation.Timeline> и свойства, используемые в анимации.|
|[Общие сведения о временных событиях](timing-events-overview.md)|Описание событий, доступных в <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> объектов для выполнения кода в точках временной шкалы, таких как begin, пауза, возобновление, пропуск или остановка.|
|[Практические руководства](animation-and-timing-how-to-topics.md)|Примеры кода для использования анимаций и временных шкал в приложении.|
|[Разделы руководства, посвященные часам](clocks-how-to-topics.md)|Содержит примеры кода для использования объекта <xref:System.Windows.Media.Animation.Clock> в приложении.|
|[Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)|Примеры кода для использования покадровой анимации в приложении.|
|[Практические руководства, посвященные анимации по контуру](path-animation-how-to-topics.md)|Примеры кода для применения анимации с использованием пути в приложении.|

<a name="reference"></a>

## <a name="reference"></a>Справочные сведения

- <xref:System.Windows.Media.Animation.Timeline>

- <xref:System.Windows.Media.Animation.Storyboard>

- <xref:System.Windows.Media.Animation.BeginStoryboard>

- <xref:System.Windows.Media.Animation.Clock>
