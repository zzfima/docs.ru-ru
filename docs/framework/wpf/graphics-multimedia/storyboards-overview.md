---
title: Общие сведения о Storyboard
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
ms.openlocfilehash: 4d5a5ee3f1fcbd09fad9e25773d0e508209e1492
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855840"
---
# <a name="storyboards-overview"></a>Общие сведения о Storyboard

В этом разделе показано, как <xref:System.Windows.Media.Animation.Storyboard> использовать объекты для Организации и применения анимаций. Он описывает, как интерактивно манипулировать <xref:System.Windows.Media.Animation.Storyboard> объектами и описывает синтаксис косвенных назначений свойств.

## <a name="prerequisites"></a>Предварительные требования

Для понимания этого раздела необходимо ознакомиться с различными типами анимации и их основными возможностями. Общие сведения об анимации см. в разделе [Общие сведения об эффектах анимации](animation-overview.md). Вы также должны знать, как использовать вложенные свойства. Дополнительные сведения о вложенных свойствах см. в разделах [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>Что такое раскадровка?

Анимация — не единственный удобный тип временной шкалы. Существуют другие классы временной шкалы, с помощью которых вы сможете создать наборы временных шкал и применить временные шкалы к свойствам. Временные шкалы контейнера являются производными <xref:System.Windows.Media.Animation.TimelineGroup> от класса и включают <xref:System.Windows.Media.Animation.ParallelTimeline> и <xref:System.Windows.Media.Animation.Storyboard>.

<xref:System.Windows.Media.Animation.Storyboard> — Это тип временной шкалы контейнера, который предоставляет сведения о целевых данных для временных шкал, которые она содержит. Раскадровка может содержать любой тип <xref:System.Windows.Media.Animation.Timeline>, включая другие временные шкалы и анимации контейнера. <xref:System.Windows.Media.Animation.Storyboard>объекты позволяют объединять временные шкалы, влияющие на различные объекты и свойства, в одно дерево временной шкалы, что упрощает организацию и управление сложными поведениями времени. Например, предположим, что вам необходима кнопка, которая выполняет следующие три действия.

- Увеличивается и изменяет цвет, когда пользователь выбирает кнопку.

- Сжимается, а затем увеличивается до исходного размера, когда пользователь нажимает на кнопку.

- Сжимается и изменяет яркость до 50-процентной прозрачности, если кнопка становится недоступной.

В этом случае у вас есть несколько наборов анимаций, которые применяются к одному объекту и которые требуется воспроизводить в разное время в зависимости от состояния кнопки. <xref:System.Windows.Media.Animation.Storyboard>объекты позволяют организовывать анимации и применять их в группах к одному или нескольким объектам.

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>Где можно использовать раскадровку?

<xref:System.Windows.Media.Animation.Storyboard> можно использовать для анимации свойств зависимостей классов с анимацией (Дополнительные сведения о том, что делает класс анимированным, см. в разделе [Общие сведения об анимации](animation-overview.md)). Однако, поскольку раскадровка является функцией уровня платформы, объект должен принадлежать <xref:System.Windows.NameScope> <xref:System.Windows.FrameworkElement> к или <xref:System.Windows.FrameworkContentElement>.

Например, можно использовать <xref:System.Windows.Media.Animation.Storyboard> для того, чтобы сделать следующее:

- Анимировать элемент <xref:System.Windows.FrameworkElement>(не являющийся платформой), который рисует фон кнопки (тип), <xref:System.Windows.Media.SolidColorBrush>

- Анимация элемента <xref:System.Windows.Media.GeometryDrawing> <xref:System.Windows.Controls.Image> <xref:System.Windows.FrameworkElement>(не являющегося элементом платформы), который рисует заливку элемента (не являющегося элементом платформы), отображаемого с помощью (). <xref:System.Windows.Media.SolidColorBrush>

- <xref:System.Windows.Media.SolidColorBrush> В коде анимируйте объект, объявленный классом, который также <xref:System.Windows.FrameworkElement>содержит, если <xref:System.Windows.Media.SolidColorBrush> зарегистрировано его имя <xref:System.Windows.FrameworkElement>.

<xref:System.Windows.Media.Animation.Storyboard> Однако нельзя использовать для <xref:System.Windows.Media.SolidColorBrush> анимации, которая не <xref:System.Windows.FrameworkElement> зарегистрировала свое имя в или <xref:System.Windows.FrameworkContentElement> <xref:System.Windows.FrameworkElement> , или не использовалась для задания свойства объекта или <xref:System.Windows.FrameworkContentElement>.

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>Применение анимации с помощью раскадровки

Чтобы использовать <xref:System.Windows.Media.Animation.Storyboard> для упорядочивания и применения анимаций, необходимо добавить анимацию как дочерние временные <xref:System.Windows.Media.Animation.Storyboard>шкалы. Класс предоставляет вложенные свойства <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType>и. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> <xref:System.Windows.Media.Animation.Storyboard> Эти свойства используются для указания целевого объекта и целевого свойства анимации.

Чтобы применить анимацию к своим целевым объектам, начните <xref:System.Windows.Media.Animation.Storyboard> с использования действия триггера или метода. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используется<xref:System.Windows.EventTrigger>объект с ,<xref:System.Windows.Trigger>или .<xref:System.Windows.DataTrigger> <xref:System.Windows.Media.Animation.BeginStoryboard> В коде можно также использовать <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод.

В следующей таблице показаны различные места, где поддерживается <xref:System.Windows.Media.Animation.Storyboard> каждый прием Begin: на экземпляр, стиль, шаблон элемента управления и шаблон данных. Применение к конкретным экземплярам подразумевает применение анимации или раскадровки непосредственно к экземплярам объектов, а не в стилях, шаблонах элементов управления или шаблонах данных.

|Раскадровка запускается с помощью метода...|Применение к конкретным экземплярам|Стиль|Шаблон элемента управления|Шаблон данных|Пример|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard>и<xref:System.Windows.EventTrigger>|Да|Да|Да|Да|[Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>и свойство<xref:System.Windows.Trigger>|Нет|Да|Да|Да|[Запуск анимации при изменении значения свойства](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>и<xref:System.Windows.DataTrigger>|Нет|Да|Да|Да|[Практическое руководство. Запускать анимацию при изменении данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|Метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Да|Нет|Нет|Нет|[Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)|

В следующем примере используется <xref:System.Windows.Media.Animation.Storyboard> для <xref:System.Windows.FrameworkElement.Width%2A> анимации <xref:System.Windows.Shapes.Rectangle> элемента <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush>иобъекта , используемого для рисования. <xref:System.Windows.Shapes.Rectangle>

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

В следующих разделах более подробно <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> описаны <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> присоединенные свойства и.

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Элементы целевой платформы, элементы содержимого платформы и объекты Freezable

В предыдущем разделе упоминалось, что для поиска целевого объекта анимации необходимо знать имя целевого объекта и анимируемое свойство. Указание свойства для анимации осуществляется прямо вперед: просто задайте <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> вместе с именем анимируемого свойства.  Укажите имя объекта, свойство которого необходимо анимировать, задав <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> свойство в анимации.

<xref:System.Windows.Setter.TargetName%2A> Чтобы свойство работало, целевой объект должен иметь имя. Назначение имени <xref:System.Windows.FrameworkElement> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или в в отличается от присвоения имени <xref:System.Windows.Freezable> объекту. <xref:System.Windows.FrameworkContentElement>

Элементы платформы — это классы, которые наследуются от <xref:System.Windows.FrameworkElement> класса. <xref:System.Windows.Window>Примеры элементов платформы: <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Button>,, и <xref:System.Windows.Shapes.Rectangle>. По существу все окна, панели и элементы управления являются элементами. Элементы содержимого платформы — это классы, которые наследуются от <xref:System.Windows.FrameworkContentElement> класса. Примеры элементов содержимого платформы включают <xref:System.Windows.Documents.FlowDocument> и. <xref:System.Windows.Documents.Paragraph> Если вы не уверены, что этот элемент является элементом платформы или элементом содержимого платформы, проверьте, есть ли у этого элемента свойство Name. Если есть, скорее всего, это элемент платформы или элемент содержимого платформы. Чтобы убедиться в этом, обратитесь к разделу "Иерархия наследования" на странице типа элемента.

Чтобы включить целевой объект платформы или элемент содержимого платформы в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], необходимо задать его <xref:System.Windows.FrameworkElement.Name%2A> свойство. В коде также необходимо использовать <xref:System.Windows.NameScope.RegisterName%2A> метод для регистрации имени элемента в элементе, для которого создан объект. <xref:System.Windows.NameScope>

В следующем примере, взятом из предыдущего примера, присваивается имя `MyRectangle` a <xref:System.Windows.Shapes.Rectangle>, тип <xref:System.Windows.FrameworkElement>.

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

После того как элемент получил имя, вы можете анимировать свойство этого элемента.

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable>типы — это классы, которые наследуются от <xref:System.Windows.Freezable> класса. <xref:System.Windows.Freezable> Примеры включения <xref:System.Windows.Media.SolidColorBrush>, и<xref:System.Windows.Media.RotateTransform>. <xref:System.Windows.Media.GradientStop>

Чтобы включить нацеливание на <xref:System.Windows.Freezable> анимацию в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте [директиву x:Name](../../xaml-services/x-name-directive.md) , чтобы присвоить ей имя. В коде <xref:System.Windows.NameScope.RegisterName%2A> метод используется для регистрации его имени в элементе, для которого вы <xref:System.Windows.NameScope>создали.

В следующем примере имя <xref:System.Windows.Freezable> присваивается объекту.

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

Затем этот объект можно выбрать в качестве целевого с помощью анимации.

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard>объекты используют области имен для разрешения <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> свойства. Дополнительные сведения об областях видимости имен WPF см. в разделе [Области видимости имен XAML в WPF](../advanced/wpf-xaml-namescopes.md). <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Если свойство пропущено, анимация нацелена на элемент, на котором она определена, или, в случае Styles, элемент с стилем.

Иногда имя не может быть назначено <xref:System.Windows.Freezable> объекту. Например, если объект <xref:System.Windows.Freezable> объявляется как ресурс или используется для задания значения свойства в стиле, ему не может быть присвоено имя. Так как у объекта нет имени, к нему нельзя обратиться напрямую, но можно обратиться косвенно. В следующих разделах описано, как обращаться к целевым объектам косвенно.

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>Косвенное обращение

Иногда <xref:System.Windows.Freezable> анимация не может быть нацелена непосредственно на анимацию, например при объявлении <xref:System.Windows.Freezable> в качестве ресурса или при использовании для задания значения свойства в стиле. В таких случаях, даже если вы не можете напрямую ориентироваться на <xref:System.Windows.Freezable> него, вы все равно можете анимировать объект. Вместо присвоения <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> свойству имени <xref:System.Windows.Freezable>, присвойте ему имя элемента <xref:System.Windows.Freezable> , которому принадлежит. Например, объект <xref:System.Windows.Media.SolidColorBrush> , используемый для <xref:System.Windows.Shapes.Shape.Fill%2A> задания элемента Rectangle, принадлежит этому прямоугольнику. Чтобы анимировать кисть, необходимо задать для анимации <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> цепочку свойств, которая начинается со свойства элемента Framework или элемента содержимого платформы, <xref:System.Windows.Freezable> который использовался для <xref:System.Windows.Freezable> установки и заканчивается свойством для анимации.

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

Обратите внимание, что <xref:System.Windows.Freezable> , если зазаморожено, будет создан клон и этот клон будет анимирован. В этом случае <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> свойство исходного объекта по-своему возвращается `false`, так как исходный объект фактически не анимируется. Дополнительные сведения о клонировании см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).

Обратите внимание, что при косвенном обращении к целевым объектам можно обращаться к объектам, которых не существует. Например, можно предположить, что <xref:System.Windows.Controls.Control.Background%2A> для определенной кнопки задано <xref:System.Windows.Media.SolidColorBrush> значение, и попытаться анимировать ее цвет <xref:System.Windows.Media.LinearGradientBrush> , когда на самом деле используется для задания фона кнопки. В таких случаях исключение не создается; анимация не может получить видимый эффект, так <xref:System.Windows.Media.LinearGradientBrush> как не реагирует на изменения <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойства.

В следующих разделах более подробно описан синтаксис косвенного обращения к целевым объектам.

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Косвенное обращение к свойству объекта Freezable в XAML

Чтобы указать свойство объекта Freezable в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте следующий синтаксис.

| |
|-|
|*ElementPropertyName* `.` *FreezablePropertyName*|

Where

- *Елементпропертинаме* — это свойство <xref:System.Windows.FrameworkElement> , которое <xref:System.Windows.Freezable> используется для задания, и

- *Фризаблепропертинаме* — свойство объекта <xref:System.Windows.Freezable> для анимации.

В следующем коде показано, как анимировать <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush> объект, используемый для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

Иногда требуется обратиться к объекту Freezable, который содержится в коллекции или массиве.

Чтобы обратиться к объекту Freezable, который содержится в коллекции, используйте следующий синтаксис пути.

| |
|-|
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|

Где *коллектиониндекс* — индекс объекта в массиве или коллекции.

Например, предположим, что прямоугольник имеет <xref:System.Windows.Media.TransformGroup> ресурс, примененный к его <xref:System.Windows.UIElement.RenderTransform%2A> свойству, и необходимо анимировать одно из преобразований, содержащихся в нем.

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

В следующем коде показано, как анимировать <xref:System.Windows.Media.RotateTransform.Angle%2A> свойство объекта, <xref:System.Windows.Media.RotateTransform> показанного в предыдущем примере.

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Косвенное обращение к свойству объекта Freezable в коде

В коде создается <xref:System.Windows.PropertyPath> объект. При создании <xref:System.Windows.PropertyPath>вы <xref:System.Windows.PropertyPath.Path%2A> указываете и <xref:System.Windows.PropertyPath.PathParameters%2A>.

Для создания <xref:System.Windows.PropertyPath.PathParameters%2A>создается массив типа <xref:System.Windows.DependencyProperty> , содержащий список полей идентификаторов свойств зависимостей. Первое поле идентификатора предназначено для свойства объекта <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> , <xref:System.Windows.Freezable> используемого для задания. Следующее поле идентификатора представляет свойство <xref:System.Windows.Freezable> целевого объекта. <xref:System.Windows.Freezable> Его<xref:System.Windows.FrameworkElement> можно рассматривать как цепочку свойств, которые соединяют объект с объектом.

Ниже приведен пример цепочки свойств зависимостей, предназначенной <xref:System.Windows.Media.SolidColorBrush.Color%2A> для <xref:System.Windows.Media.SolidColorBrush> объекта, который используется для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

Также необходимо указать <xref:System.Windows.PropertyPath.Path%2A>. Значение типа ,указывающее<xref:System.Windows.PropertyPath.Path%2A> способ интерпретации <xref:System.Windows.PropertyPath.PathParameters%2A>. <xref:System.String> <xref:System.Windows.PropertyPath.Path%2A> Для этого используется следующий синтаксис.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|

Where

- *Овнерпропертяррайиндекс* — это индекс <xref:System.Windows.DependencyProperty> массива, содержащий идентификатор <xref:System.Windows.FrameworkElement> свойства объекта, которое <xref:System.Windows.Freezable> используется для задания, и

- *Фризаблепропертяррайиндекс* — это индекс <xref:System.Windows.DependencyProperty> массива, который содержит идентификатор свойства для целевого объекта.

В следующем примере показано <xref:System.Windows.PropertyPath.Path%2A> , что будет сопровождать объект <xref:System.Windows.PropertyPath.PathParameters%2A> , определенный в предыдущем примере.

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

Следующий пример сочетает код в предыдущих примерах для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush> объекта, используемого для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

Иногда требуется обратиться к объекту Freezable, который содержится в коллекции или массиве. Например, предположим, что прямоугольник имеет <xref:System.Windows.Media.TransformGroup> ресурс, примененный к его <xref:System.Windows.UIElement.RenderTransform%2A> свойству, и необходимо анимировать одно из преобразований, содержащихся в нем.

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

Для нацеливания на объект <xref:System.Windows.Freezable> , содержащийся в коллекции, используется следующий синтаксис пути.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|

Где *коллектиониндекс* — индекс объекта в массиве или коллекции.

Чтобы <xref:System.Windows.Media.RotateTransform.Angle%2A> нацелить свойство <xref:System.Windows.Media.TransformGroup> <xref:System.Windows.Media.RotateTransform>, второе преобразование в, следует использовать следующие <xref:System.Windows.PropertyPath.Path%2A> и <xref:System.Windows.PropertyPath.PathParameters%2A>.

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

В следующем примере показан полный код для анимации <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform> элемента, содержащегося в <xref:System.Windows.Media.TransformGroup>.

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Косвенное обращение с использованием объекта Freezable в качестве начальной точки

В предыдущих разделах было описано, как косвенно <xref:System.Windows.Freezable> нацелить объект <xref:System.Windows.FrameworkElement> , <xref:System.Windows.FrameworkContentElement> начав с или и создав цепочку <xref:System.Windows.Freezable> свойств для подсвойства. Можно также использовать в качестве <xref:System.Windows.Freezable> отправной точки и косвенно ориентироваться на <xref:System.Windows.Freezable> одно из его вложенных свойств. При использовании в <xref:System.Windows.Freezable> качестве отправной точки для косвенного нацеливания применяется одно дополнительное ограничение <xref:System.Windows.Freezable> : начальное и каждое <xref:System.Windows.Freezable> между ним и косвенно целевое вспомогательное свойство не должны быть заморожены.

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Интерактивное управление раскадровкой в XAML

Чтобы запустить раскадровку [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]в, <xref:System.Windows.Media.Animation.BeginStoryboard> используйте действие триггера. <xref:System.Windows.Media.Animation.BeginStoryboard>распределяет анимации между объектами и свойствами, которые они анимированы, и запускает раскадровку. (Дополнительные сведения об этом процессе см. в разделе [Общие сведения о анимации и системе управления временем](animation-and-timing-system-overview.md).) Если вы придаете <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав его <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> свойство, вы сделаете его управляемой раскадровкой. Вы можете затем интерактивно управлять раскадровкой после ее запуска. Ниже приведен список действий для управляемой раскадровки, которые используются совместно с триггерами событий для управления раскадровкой.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Приостанавливает раскадровку.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Перемещает раскадровку в конец периода заполнения, если он имеет значение.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку.

В следующем примере показано использование действий для интерактивного управления раскадровкой.

[!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]

<a name="controllable_storyboards_procedural"></a>

## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Интерактивное управление раскадровкой с помощью кода

В предыдущих примерах было показано, как анимировать свойства с помощью действий триггера. В коде вы также можете управлять раскадровкой с помощью интерактивных методов <xref:System.Windows.Media.Animation.Storyboard> класса. Чтобы сделать его интерактивным в коде, необходимо использовать подходящую перегрузку <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метода раскадровки и указать `true` , чтобы она стала управляемой. <xref:System.Windows.Media.Animation.Storyboard> Дополнительные сведения <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> см. на странице.

В следующем списке показаны методы, которые можно использовать для работы с <xref:System.Windows.Media.Animation.Storyboard> после запуска.

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

Преимущество использования этих методов заключается в том, что вам не нужно создавать <xref:System.Windows.Trigger> объекты <xref:System.Windows.TriggerAction> или; вам просто нужна ссылка <xref:System.Windows.Media.Animation.Storyboard> на управляемый элемент управления.

> [!NOTE]
> Все интерактивные действия <xref:System.Windows.Media.Animation.Clock>, выполненные в, и, следовательно <xref:System.Windows.Media.Animation.Storyboard> , будут выполняться в следующий такт обработчика времени, который будет происходить вскоре перед следующей отрисовкой. Например, если для перехода к другой <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> точке анимации используется метод, значение свойства не изменяется мгновенно, а значение изменяется на следующий такт обработчика времени.

В следующем примере показано, как применять анимацию и управлять ей с помощью интерактивных <xref:System.Windows.Media.Animation.Storyboard> методов класса.

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>Анимация с использованием стилей

Для определения анимации <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Style>в можно использовать объекты. Анимация с <xref:System.Windows.Media.Animation.Storyboard> помощью <xref:System.Windows.Style> в аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в других случаях со следующими тремя исключениями:

- Вы не указываете <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>, <xref:System.Windows.Media.Animation.Storyboard> значение всегда указывает <xref:System.Windows.Style> на элемент, к которому применяется. Для целевых <xref:System.Windows.Freezable> объектов необходимо использовать косвенное нацеливание. Дополнительные сведения о косвенном нацеливании см. в разделе [косвенная нацеливание](#pathsyntaxforchangeable) .

- Нельзя указать <xref:System.Windows.EventTrigger.SourceName%2A> <xref:System.Windows.EventTrigger> для или .<xref:System.Windows.Trigger>

- Нельзя использовать динамические ссылки на ресурсы или выражения привязки данных для задания <xref:System.Windows.Media.Animation.Storyboard> значений свойств или анимации. Это обусловлено тем, что <xref:System.Windows.Style> все, что находится внутри, должно быть потокобезопасным, а <xref:System.Windows.Freezable.Freeze%2A> система управления временем должна <xref:System.Windows.Media.Animation.Storyboard> обеспечить потокобезопасность объектов. Объект <xref:System.Windows.Media.Animation.Storyboard> не может быть заморожен, если он или его дочерние временные шкалы содержат ссылки на динамические ресурсы или выражения привязки данных. Дополнительные сведения о замораживании и других <xref:System.Windows.Freezable> возможностях см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).

- В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]нельзя объявлять обработчики событий для <xref:System.Windows.Media.Animation.Storyboard> событий анимации или.

Пример, в котором показано, как определить раскадровку в стиле, см. в примере [анимации в стиле](how-to-animate-in-a-style.md) .

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>Анимация в ControlTemplate

Для определения анимации <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Controls.ControlTemplate>в можно использовать объекты. Анимация с <xref:System.Windows.Media.Animation.Storyboard> помощью <xref:System.Windows.Controls.ControlTemplate> в аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в других случаях со следующими двумя исключениями:

- Может ссылаться только на дочерние объекты <xref:System.Windows.Controls.ControlTemplate>объекта. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Если <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> параметр не указан, анимация нацелена на элемент, к <xref:System.Windows.Controls.ControlTemplate> которому применяется.

- <xref:System.Windows.EventTrigger.SourceName%2A> Для<xref:System.Windows.EventTrigger> или может<xref:System.Windows.Trigger> ссылаться только на дочерние объекты объекта. <xref:System.Windows.Controls.ControlTemplate>

- Нельзя использовать динамические ссылки на ресурсы или выражения привязки данных для задания <xref:System.Windows.Media.Animation.Storyboard> значений свойств или анимации. Это обусловлено тем, что <xref:System.Windows.Controls.ControlTemplate> все, что находится внутри, должно быть потокобезопасным, а <xref:System.Windows.Freezable.Freeze%2A> система управления временем должна <xref:System.Windows.Media.Animation.Storyboard> обеспечить потокобезопасность объектов. Объект <xref:System.Windows.Media.Animation.Storyboard> не может быть заморожен, если он или его дочерние временные шкалы содержат ссылки на динамические ресурсы или выражения привязки данных. Дополнительные сведения о замораживании и других <xref:System.Windows.Freezable> возможностях см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).

- В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]нельзя объявлять обработчики событий для <xref:System.Windows.Media.Animation.Storyboard> событий анимации или.

Пример <xref:System.Windows.Controls.ControlTemplate>, показывающий, как определить раскадровку в, см. в примере [анимации в](how-to-animate-in-a-controltemplate.md) образце ControlTemplate.

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>Анимация при изменении значения свойства

В стилях и шаблонах элементов можно использовать объекты триггеров для запуска раскадровки при изменении свойства. Примеры см. в разделе [Триггер анимации при изменении значения свойства](how-to-trigger-an-animation-when-a-property-value-changes.md) и [анимации в ControlTemplate](how-to-animate-in-a-controltemplate.md).

Анимации, примененные <xref:System.Windows.Trigger> объектами свойств, ведут себя более сложным способом <xref:System.Windows.EventTrigger> , чем анимация или анимация <xref:System.Windows.Media.Animation.Storyboard> , запущенные с помощью методов.  Они "передаются" с анимациями <xref:System.Windows.Trigger> , определенными другими объектами <xref:System.Windows.EventTrigger> , но сопоставлены с анимациями и, запускающими методы.

## <a name="see-also"></a>См. также

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md)
- [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md)
