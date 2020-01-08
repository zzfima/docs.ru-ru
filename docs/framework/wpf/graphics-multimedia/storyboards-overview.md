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
ms.openlocfilehash: 5c058dbaf2ae209a198a8299790d4002447ac443
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559698"
---
# <a name="storyboards-overview"></a>Общие сведения о Storyboard

В этом разделе показано, как использовать объекты <xref:System.Windows.Media.Animation.Storyboard> для Организации и применения анимаций. Он описывает, как интерактивно манипулировать <xref:System.Windows.Media.Animation.Storyboard> объектами и описывает синтаксис непрямого назначения свойств.

## <a name="prerequisites"></a>Prerequisites

Для понимания этого раздела необходимо ознакомиться с различными типами анимации и их основными возможностями. Общие сведения об анимации см. в разделе [Общие сведения об эффектах анимации](animation-overview.md). Вы также должны знать, как использовать вложенные свойства. Дополнительные сведения о вложенных свойствах см. в разделах [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>Что такое раскадровка?

Анимация — не единственный удобный тип временной шкалы. Существуют другие классы временной шкалы, с помощью которых вы сможете создать наборы временных шкал и применить временные шкалы к свойствам. Временные шкалы контейнера являются производными от класса <xref:System.Windows.Media.Animation.TimelineGroup> и включают <xref:System.Windows.Media.Animation.ParallelTimeline> и <xref:System.Windows.Media.Animation.Storyboard>.

<xref:System.Windows.Media.Animation.Storyboard> — это тип временной шкалы контейнера, который предоставляет сведения о целевых данных для временных шкал, которые она содержит. Раскадровка может содержать любой тип <xref:System.Windows.Media.Animation.Timeline>, включая другие временные шкалы и анимации контейнера. <xref:System.Windows.Media.Animation.Storyboard> объекты позволяют объединять временные шкалы, влияющие на различные объекты и свойства, в одно дерево временной шкалы, что упрощает организацию и управление сложными поведениями времени. Например, предположим, что вам необходима кнопка, которая выполняет следующие три действия.

- Увеличивается и изменяет цвет, когда пользователь выбирает кнопку.

- Сжимается, а затем увеличивается до исходного размера, когда пользователь нажимает на кнопку.

- Сжимается и изменяет яркость до 50-процентной прозрачности, если кнопка становится недоступной.

В этом случае у вас есть несколько наборов анимаций, которые применяются к одному объекту и которые требуется воспроизводить в разное время в зависимости от состояния кнопки. <xref:System.Windows.Media.Animation.Storyboard> объекты позволяют упорядочивать анимации и применять их в группах к одному или нескольким объектам.

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>Где можно использовать раскадровку?

<xref:System.Windows.Media.Animation.Storyboard> можно использовать для анимации свойств зависимостей классов с анимацией (Дополнительные сведения о том, что делает класс анимированным, см. в разделе [Общие сведения об анимации](animation-overview.md)). Однако, поскольку раскадровка является функцией уровня платформы, объект должен принадлежать <xref:System.Windows.NameScope> <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.

Например, можно использовать <xref:System.Windows.Media.Animation.Storyboard> для следующих действий:

- Анимировать <xref:System.Windows.Media.SolidColorBrush> (не являющийся элементом платформы), который рисует фон кнопки (тип <xref:System.Windows.FrameworkElement>),

- Анимировать <xref:System.Windows.Media.SolidColorBrush> (не являющийся элементом платформы), который рисует заливку <xref:System.Windows.Media.GeometryDrawing> (элемента, не являющегося элементом платформы), отображаемого с помощью <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).

- В коде анимировать <xref:System.Windows.Media.SolidColorBrush>, объявленный классом, который также содержит <xref:System.Windows.FrameworkElement>, если <xref:System.Windows.Media.SolidColorBrush> зарегистрировал свое имя с этим <xref:System.Windows.FrameworkElement>.

Однако нельзя использовать <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.SolidColorBrush>, который не зарегистрировал свое имя в <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>или не использовался для задания свойства <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>Применение анимации с помощью раскадровки

Чтобы использовать <xref:System.Windows.Media.Animation.Storyboard> для упорядочения и применения анимаций, необходимо добавить анимацию как дочерние временные шкалы <xref:System.Windows.Media.Animation.Storyboard>. Класс <xref:System.Windows.Media.Animation.Storyboard> предоставляет <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> вложенные свойства. Эти свойства используются для указания целевого объекта и целевого свойства анимации.

Чтобы применить анимацию к своим целевым объектам, начните <xref:System.Windows.Media.Animation.Storyboard> с помощью действия триггера или метода. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]используется объект <xref:System.Windows.Media.Animation.BeginStoryboard> с <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>или <xref:System.Windows.DataTrigger>. В коде можно также использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.

В следующей таблице показаны различные места, где поддерживается каждый прием <xref:System.Windows.Media.Animation.Storyboard> Begin: на экземпляр, стиль, шаблон элемента управления и шаблон данных. Применение к конкретным экземплярам подразумевает применение анимации или раскадровки непосредственно к экземплярам объектов, а не в стилях, шаблонах элементов управления или шаблонах данных.

|Раскадровка запускается с помощью метода...|Применение к конкретным экземплярам|Стиль|Шаблон элемента управления|Шаблон данных|Пример|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.EventTrigger>|Да|Да|Да|Да|[Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard> и свойство <xref:System.Windows.Trigger>|Нет|Да|Да|Да|[Запуск анимации при изменении значения свойства](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.DataTrigger>|Нет|Да|Да|Да|[Практическое руководство. Запуск анимации при изменении данных](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|Метод<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Да|Нет|Нет|Нет|[Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)|

В следующем примере используется <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.FrameworkElement.Width%2A> элемента <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush>, используемого для рисования <xref:System.Windows.Shapes.Rectangle>.

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

В следующих разделах более подробно описаны <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> присоединенные свойства.

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Элементы целевой платформы, элементы содержимого платформы и объекты Freezable

В предыдущем разделе упоминалось, что для поиска целевого объекта анимации необходимо знать имя целевого объекта и анимируемое свойство. Указание свойства для анимации осуществляется прямо вперед: просто задайте <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> с именем анимируемого свойства.  Укажите имя объекта, свойство которого необходимо анимировать, задав свойство <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> в анимации.

Чтобы <xref:System.Windows.Setter.TargetName%2A> свойство работало, целевой объект должен иметь имя. Назначение имени <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] отличается от назначения имени объекту <xref:System.Windows.Freezable>.

Элементы платформы — это классы, которые наследуются от класса <xref:System.Windows.FrameworkElement>. Примерами элементов платформы могут служить <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>и <xref:System.Windows.Shapes.Rectangle>. По существу все окна, панели и элементы управления являются элементами. Элементы содержимого платформы — это классы, которые наследуются от класса <xref:System.Windows.FrameworkContentElement>. Примеры элементов содержимого платформы включают <xref:System.Windows.Documents.FlowDocument> и <xref:System.Windows.Documents.Paragraph>. Если вы не уверены, что этот элемент является элементом платформы или элементом содержимого платформы, проверьте, есть ли у этого элемента свойство Name. Если есть, скорее всего, это элемент платформы или элемент содержимого платформы. Чтобы убедиться в этом, обратитесь к разделу "Иерархия наследования" на странице типа элемента.

Чтобы включить целевой объект платформы или элемент содержимого платформы в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], необходимо задать свойство <xref:System.Windows.FrameworkElement.Name%2A>. В коде также необходимо использовать метод <xref:System.Windows.NameScope.RegisterName%2A> для регистрации имени элемента в элементе, для которого создан <xref:System.Windows.NameScope>.

В следующем примере, взятом из предыдущего примера, присваивается имя `MyRectangle` <xref:System.Windows.Shapes.Rectangle>типа <xref:System.Windows.FrameworkElement>.

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

После того как элемент получил имя, вы можете анимировать свойство этого элемента.

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable> типы — это классы, которые наследуются от класса <xref:System.Windows.Freezable>. Примеры <xref:System.Windows.Freezable> включают <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>и <xref:System.Windows.Media.GradientStop>.

Чтобы включить нацеливание <xref:System.Windows.Freezable> анимации в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте [директиву x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) , чтобы присвоить ей имя. В коде используйте метод <xref:System.Windows.NameScope.RegisterName%2A>, чтобы зарегистрировать его имя в элементе, для которого вы создали <xref:System.Windows.NameScope>.

В следующем примере имя присваивается объекту <xref:System.Windows.Freezable>.

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

Затем этот объект можно выбрать в качестве целевого с помощью анимации.

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard> объекты используют области имен для разрешения свойства <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>. Дополнительные сведения об областях видимости имен WPF см. в разделе [Области видимости имен XAML в WPF](../advanced/wpf-xaml-namescopes.md). Если свойство <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> опущено, анимация нацелена на элемент, на котором она определена, или, в случае Styles, элемент с стилем.

Иногда имя не может быть назначено объекту <xref:System.Windows.Freezable>. Например, если <xref:System.Windows.Freezable> объявляется как ресурс или используется для задания значения свойства в стиле, ему не может быть присвоено имя. Так как у объекта нет имени, к нему нельзя обратиться напрямую, но можно обратиться косвенно. В следующих разделах описано, как обращаться к целевым объектам косвенно.

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>Косвенное обращение

В некоторых случаях <xref:System.Windows.Freezable> не может быть нацелена на анимацию напрямую, например, когда <xref:System.Windows.Freezable> объявляется как ресурс или используется для задания значения свойства в стиле. В таких случаях, несмотря на то, что вы не можете напрямую ориентироваться на него, вы по-прежнему можете анимировать объект <xref:System.Windows.Freezable>. Вместо присвоения свойству <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> имени <xref:System.Windows.Freezable>присвойте ему имя элемента, которому принадлежит <xref:System.Windows.Freezable>. Например, <xref:System.Windows.Media.SolidColorBrush>, используемая для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента Rectangle, принадлежит этому прямоугольнику. Чтобы анимировать кисть, можно задать <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> анимации с помощью цепочки свойств, которые начинаются со свойства элемента Framework или элемента содержимого платформы, которые <xref:System.Windows.Freezable> использовались для установки и завершения свойства <xref:System.Windows.Freezable> для анимации.

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

Обратите внимание, что, если <xref:System.Windows.Freezable> заморожен, будет сделан клон, и этот клон будет анимирован. В этом случае свойство <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> исходного объекта продолжит возвращать `false`, так как исходный объект фактически не анимируется. Дополнительные сведения о клонировании см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).

Обратите внимание, что при косвенном обращении к целевым объектам можно обращаться к объектам, которых не существует. Например, можно предположить, что <xref:System.Windows.Controls.Control.Background%2A> определенной кнопки было задано <xref:System.Windows.Media.SolidColorBrush> и попытаться анимировать ее цвет, когда на самом деле <xref:System.Windows.Media.LinearGradientBrush> использовалась для установки фона кнопки. В таких случаях исключение не создается; анимация не может получить видимый эффект, так как <xref:System.Windows.Media.LinearGradientBrush> не реагирует на изменения свойства <xref:System.Windows.Media.SolidColorBrush.Color%2A>.

В следующих разделах более подробно описан синтаксис косвенного обращения к целевым объектам.

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Косвенное обращение к свойству объекта Freezable в XAML

Чтобы указать свойство объекта Freezable в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте следующий синтаксис.

| |
|-|
|*Елементпропертинаме* `.` *фризаблепропертинаме*|

Where

- *Елементпропертинаме* — это свойство <xref:System.Windows.FrameworkElement>, для которого задается <xref:System.Windows.Freezable>, и

- *Фризаблепропертинаме* — это свойство <xref:System.Windows.Freezable> для анимации.

В следующем коде показано, как анимировать <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush>, используемого для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента Rectangle.

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

Иногда требуется обратиться к объекту Freezable, который содержится в коллекции или массиве.

Чтобы обратиться к объекту Freezable, который содержится в коллекции, используйте следующий синтаксис пути.

| |
|-|
|*Елементпропертинаме* `.Children[` *коллектиониндекс* `].` *фризаблепропертинаме*|

Где *коллектиониндекс* — индекс объекта в массиве или коллекции.

Например, предположим, что прямоугольник имеет <xref:System.Windows.Media.TransformGroup>ный ресурс, примененный к его свойству <xref:System.Windows.UIElement.RenderTransform%2A>, и вы хотите анимировать одно из преобразований, содержащихся в нем.

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

В следующем коде показано, как анимировать свойство <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform>, как показано в предыдущем примере.

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Косвенное обращение к свойству объекта Freezable в коде

В коде создается объект <xref:System.Windows.PropertyPath>. При создании <xref:System.Windows.PropertyPath>указываются <xref:System.Windows.PropertyPath.Path%2A> и <xref:System.Windows.PropertyPath.PathParameters%2A>.

Чтобы создать <xref:System.Windows.PropertyPath.PathParameters%2A>, необходимо создать массив типа <xref:System.Windows.DependencyProperty>, содержащий список полей идентификаторов свойств зависимостей. Первое поле идентификатора предназначено для свойства <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, которое используется для установки <xref:System.Windows.Freezable>. Следующее поле идентификатора представляет свойство целевого <xref:System.Windows.Freezable>. Его можно рассматривать как цепочку свойств, соединяющих <xref:System.Windows.Freezable> с объектом <xref:System.Windows.FrameworkElement>.

Ниже приведен пример цепочки свойств зависимостей, нацеленной на <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush>, используемого для установки <xref:System.Windows.Shapes.Shape.Fill%2A> элемента Rectangle.

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

Также необходимо указать <xref:System.Windows.PropertyPath.Path%2A>. <xref:System.Windows.PropertyPath.Path%2A> — это <xref:System.String>, который сообщает <xref:System.Windows.PropertyPath.Path%2A>, как интерпретировать его <xref:System.Windows.PropertyPath.PathParameters%2A>. Для этого используется следующий синтаксис.

| |
|-|
|`(` *овнерпропертяррайиндекс* `).(` *фризаблепропертяррайиндекс* `)`|

Where

- *Овнерпропертяррайиндекс* — это индекс массива <xref:System.Windows.DependencyProperty>, который содержит идентификатор свойства объекта <xref:System.Windows.FrameworkElement>, которое используется <xref:System.Windows.Freezable> для установки, и

- *Фризаблепропертяррайиндекс* — индекс массива <xref:System.Windows.DependencyProperty>, который содержит идентификатор свойства для целевого объекта.

В следующем примере показаны <xref:System.Windows.PropertyPath.Path%2A>, сопровождающие <xref:System.Windows.PropertyPath.PathParameters%2A>, определенные в предыдущем примере.

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

Следующий пример сочетает код из предыдущих примеров, чтобы анимировать <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush>, используемого для установки <xref:System.Windows.Shapes.Shape.Fill%2A> элемента Rectangle.

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

Иногда требуется обратиться к объекту Freezable, который содержится в коллекции или массиве. Например, предположим, что прямоугольник имеет <xref:System.Windows.Media.TransformGroup>ный ресурс, примененный к его свойству <xref:System.Windows.UIElement.RenderTransform%2A>, и вы хотите анимировать одно из преобразований, содержащихся в нем.

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

Для назначения <xref:System.Windows.Freezable>, содержащихся в коллекции, используется следующий синтаксис пути.

| |
|-|
|`(` *овнерпропертяррайиндекс* `).(` *Коллектиончилдренпропертяррайиндекс* `)` `[` *коллектиониндекс* `].(` *фризаблепропертяррайиндекс* `)`|

Где *коллектиониндекс* — индекс объекта в массиве или коллекции.

Чтобы выбрать свойство <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform>, во втором преобразовании в <xref:System.Windows.Media.TransformGroup>необходимо использовать следующие <xref:System.Windows.PropertyPath.Path%2A> и <xref:System.Windows.PropertyPath.PathParameters%2A>.

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

В следующем примере показан полный код для анимации <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform>, содержащихся в <xref:System.Windows.Media.TransformGroup>.

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Косвенное обращение с использованием объекта Freezable в качестве начальной точки

В предыдущих разделах было описано, как косвенно ориентироваться на <xref:System.Windows.Freezable>, начиная с <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> и создавая цепочку свойств для <xref:System.Windows.Freezable> подсвойства. Можно также использовать <xref:System.Windows.Freezable> в качестве отправной точки и косвенно ориентироваться на одно из его <xref:System.Windows.Freezable> вложенных свойств. При использовании <xref:System.Windows.Freezable> в качестве отправной точки для косвенного нацеливания применяется одно дополнительное ограничение: Начальная <xref:System.Windows.Freezable> и все <xref:System.Windows.Freezable> между ним и косвенно целевым вспомогательным свойством не должны быть заморожены.

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Интерактивное управление раскадровкой в XAML

Для запуска раскадровки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]используется действие триггера <xref:System.Windows.Media.Animation.BeginStoryboard>. <xref:System.Windows.Media.Animation.BeginStoryboard> передает анимацию в объекты и свойства, которые они анимированы, и запускает раскадровку. (Дополнительные сведения об этом процессе см. в разделе [Общие сведения о анимации и системе управления временем](animation-and-timing-system-overview.md).) Если присвоить <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав его свойство <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>, вы сделаете его управляемой раскадровкой. Вы можете затем интерактивно управлять раскадровкой после ее запуска. Ниже приведен список действий для управляемой раскадровки, которые используются совместно с триггерами событий для управления раскадровкой.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: приостанавливает раскадровку.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: изменяет скорость раскадровки.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: переносит раскадровку в конец периода заполнения, если он имеется.

- <xref:System.Windows.Media.Animation.StopStoryboard>: останавливает раскадровку.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: удаляет раскадровку.

В следующем примере показано использование действий для интерактивного управления раскадровкой.

[!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]

<a name="controllable_storyboards_procedural"></a>

## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Интерактивное управление раскадровкой с помощью кода

В предыдущих примерах было показано, как анимировать свойства с помощью действий триггера. В коде вы также можете управлять раскадровкой с помощью интерактивных методов класса <xref:System.Windows.Media.Animation.Storyboard>. Чтобы <xref:System.Windows.Media.Animation.Storyboard> сделать интерактивным в коде, необходимо использовать подходящую перегрузку метода <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> раскадровки и указать `true`, чтобы сделать ее управляемой. Дополнительные сведения см. на странице <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>.

В следующем списке показаны методы, которые можно использовать для работы с <xref:System.Windows.Media.Animation.Storyboard> после его запуска.

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

Преимущество использования этих методов заключается в том, что не нужно создавать <xref:System.Windows.Trigger> или <xref:System.Windows.TriggerAction> объекты. требуется только ссылка на управляемый <xref:System.Windows.Media.Animation.Storyboard>, которым требуется управлять.

> [!NOTE]
> Все интерактивные действия, выполненные на <xref:System.Windows.Media.Animation.Clock>, и, следовательно, на <xref:System.Windows.Media.Animation.Storyboard> будут происходить в следующий такт обработчика времени, который будет происходить вскоре перед следующей отрисовкой. Например, при использовании метода <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> для перехода к другой точке анимации значение свойства не изменяется мгновенно, а значение изменяется на следующий такт обработчика времени.

В следующем примере показано, как применять анимацию и управлять ей с помощью интерактивных методов класса <xref:System.Windows.Media.Animation.Storyboard>.

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>Анимация с использованием стилей

<xref:System.Windows.Media.Animation.Storyboard> объекты можно использовать для определения анимации в <xref:System.Windows.Style>. Анимация с <xref:System.Windows.Media.Animation.Storyboard> в <xref:System.Windows.Style> аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в других местах, за исключением следующих трех исключений:

- <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>не указывается; <xref:System.Windows.Media.Animation.Storyboard> всегда обращается к элементу, к которому применяется <xref:System.Windows.Style>. Для целевых объектов <xref:System.Windows.Freezable> необходимо использовать косвенное нацеливание. Дополнительные сведения о косвенном нацеливании см. в разделе [косвенная нацеливание](#pathsyntaxforchangeable) .

- Нельзя указать <xref:System.Windows.EventTrigger.SourceName%2A> для <xref:System.Windows.EventTrigger> или <xref:System.Windows.Trigger>.

- Для задания значений свойств <xref:System.Windows.Media.Animation.Storyboard> или анимации нельзя использовать динамические ссылки на ресурсы или выражения привязки данных. Это связано с тем, что все, что находится внутри <xref:System.Windows.Style>, должно быть потокобезопасным, и система времени должна <xref:System.Windows.Freezable.Freeze%2A><xref:System.Windows.Media.Animation.Storyboard> объекты, чтобы сделать их потокобезопасными. <xref:System.Windows.Media.Animation.Storyboard> нельзя зафиксировать, если она или ее дочерние временные шкалы содержат ссылки на динамические ресурсы или выражения привязки данных. Дополнительные сведения о замораживании и других <xref:System.Windows.Freezable>ных функциях см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).

- В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]нельзя объявлять обработчики событий для событий <xref:System.Windows.Media.Animation.Storyboard> или анимации.

Пример, в котором показано, как определить раскадровку в стиле, см. в примере [анимации в стиле](how-to-animate-in-a-style.md) .

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>Анимация в ControlTemplate

<xref:System.Windows.Media.Animation.Storyboard> объекты можно использовать для определения анимации в <xref:System.Windows.Controls.ControlTemplate>. Анимация с <xref:System.Windows.Media.Animation.Storyboard> в <xref:System.Windows.Controls.ControlTemplate> аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в других местах, за исключением следующих двух исключений:

- <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> может ссылаться только на дочерние объекты <xref:System.Windows.Controls.ControlTemplate>. Если <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> не указан, анимация нацелена на элемент, к которому применяется <xref:System.Windows.Controls.ControlTemplate>.

- <xref:System.Windows.EventTrigger.SourceName%2A> для <xref:System.Windows.EventTrigger> или <xref:System.Windows.Trigger> могут ссылаться только на дочерние объекты <xref:System.Windows.Controls.ControlTemplate>.

- Для задания значений свойств <xref:System.Windows.Media.Animation.Storyboard> или анимации нельзя использовать динамические ссылки на ресурсы или выражения привязки данных. Это связано с тем, что все, что находится внутри <xref:System.Windows.Controls.ControlTemplate>, должно быть потокобезопасным, и система времени должна <xref:System.Windows.Freezable.Freeze%2A><xref:System.Windows.Media.Animation.Storyboard> объекты, чтобы сделать их потокобезопасными. <xref:System.Windows.Media.Animation.Storyboard> нельзя зафиксировать, если она или ее дочерние временные шкалы содержат ссылки на динамические ресурсы или выражения привязки данных. Дополнительные сведения о замораживании и других <xref:System.Windows.Freezable>ных функциях см. в разделе [Общие сведения об объектах Freezable](../advanced/freezable-objects-overview.md).

- В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]нельзя объявлять обработчики событий для событий <xref:System.Windows.Media.Animation.Storyboard> или анимации.

Пример, показывающий, как определить раскадровку в <xref:System.Windows.Controls.ControlTemplate>, см. в примере [анимации в виде ControlTemplate](how-to-animate-in-a-controltemplate.md) .

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>Анимация при изменении значения свойства

В стилях и шаблонах элементов можно использовать объекты триггеров для запуска раскадровки при изменении свойства. Примеры см. в разделе [Триггер анимации при изменении значения свойства](how-to-trigger-an-animation-when-a-property-value-changes.md) и [анимации в ControlTemplate](how-to-animate-in-a-controltemplate.md).

Анимации, применяемые объектами <xref:System.Windows.Trigger> свойств, ведут себя более сложным способом, чем <xref:System.Windows.EventTrigger> анимация или анимация, запущенные с помощью методов <xref:System.Windows.Media.Animation.Storyboard>.  Они "передаются" с анимациями, определенными другими <xref:System.Windows.Trigger>ными объектами, но сопоставлены с <xref:System.Windows.EventTrigger> и анимациями, запускаемыми методом.

## <a name="see-also"></a>См. также:

- [Общие сведения об анимации](animation-overview.md)
- [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md)
- [Общие сведения об объектах класса Freezable](../advanced/freezable-objects-overview.md)
