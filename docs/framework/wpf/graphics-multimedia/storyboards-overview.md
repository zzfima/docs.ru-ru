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
ms.openlocfilehash: 36922dce795443a4c1136f6442eff1c297f3c641
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566903"
---
# <a name="storyboards-overview"></a>Общие сведения о Storyboard
В этом разделе показано, как использовать <xref:System.Windows.Media.Animation.Storyboard> объектов для организации и применения анимации. Описывает интерактивно использовать <xref:System.Windows.Media.Animation.Storyboard> объектов и описывает синтаксис косвенного выбора свойств.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела необходимо ознакомиться с различными типами анимации и их основными возможностями. Общие сведения об анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Вы также должны знать, как использовать вложенные свойства. Дополнительные сведения о вложенных свойствах см. в разделах [Общие сведения о вложенных свойствах](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>Что такое раскадровка?  
 Анимация — не единственный удобный тип временной шкалы. Существуют другие классы временной шкалы, с помощью которых вы сможете создать наборы временных шкал и применить временные шкалы к свойствам. Шкалы времени контейнера являются производными от <xref:System.Windows.Media.Animation.TimelineGroup> класса и включать <xref:System.Windows.Media.Animation.ParallelTimeline> и <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Объект <xref:System.Windows.Media.Animation.Storyboard> — это тип контейнера временной шкалы, предоставляющий сведения о содержащихся в нем шкалах. Раскадровка может содержать любой тип <xref:System.Windows.Media.Animation.Timeline>, включая другие временные шкалы контейнера и анимации. <xref:System.Windows.Media.Animation.Storyboard> объекты позволяют объединить временные шкалы, влияющие на различные объекты и свойства в одно дерево временной шкалы, упрощая организацию и управление сложным поведением времени. Например, предположим, что вам необходима кнопка, которая выполняет следующие три действия.  
  
-   Увеличивается и изменяет цвет, когда пользователь выбирает кнопку.  
  
-   Сжимается, а затем увеличивается до исходного размера, когда пользователь нажимает на кнопку.  
  
-   Сжимается и изменяет яркость до 50-процентной прозрачности, если кнопка становится недоступной.  
  
 В этом случае у вас есть несколько наборов анимаций, которые применяются к одному объекту и которые требуется воспроизводить в разное время в зависимости от состояния кнопки. <xref:System.Windows.Media.Animation.Storyboard> объекты позволяют организовывать анимации и применить их в группах для одного или нескольких объектов.  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>Где можно использовать раскадровку?  
 Объект <xref:System.Windows.Media.Animation.Storyboard> можно использовать для анимации свойства зависимостей анимации классов (Дополнительные сведения о том, что делает класс анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)). Однако поскольку раскадровка — это функция уровня платформы, объекта должны принадлежать <xref:System.Windows.NameScope> из <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  
  
 Например, можно использовать <xref:System.Windows.Media.Animation.Storyboard> делать следующее:  
  
-   Анимация <xref:System.Windows.Media.SolidColorBrush> (Non-framework элемент), который закрашивает фон кнопки (тип <xref:System.Windows.FrameworkElement>),  
  
-   Анимация <xref:System.Windows.Media.SolidColorBrush> (Non-framework элемент), которая закрашивает заполнения <xref:System.Windows.Media.GeometryDrawing> (Non-framework элемент) отображается с помощью <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).  
  
-   В коде анимация <xref:System.Windows.Media.SolidColorBrush> объявляется с помощью класса, который также содержит <xref:System.Windows.FrameworkElement>, если <xref:System.Windows.Media.SolidColorBrush> зарегистрирована, его имя <xref:System.Windows.FrameworkElement>.  
  
 Однако не удалось использовать <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.SolidColorBrush> , не зарегистрировала со <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, или не использовался для задания свойства <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>Применение анимации с помощью раскадровки  
 Для использования <xref:System.Windows.Media.Animation.Storyboard> для организации и применения анимации, Добавление анимации как дочерние временные шкалы для <xref:System.Windows.Media.Animation.Storyboard>. <xref:System.Windows.Media.Animation.Storyboard> Класс предоставляет <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> вложенные свойства. Эти свойства используются для указания целевого объекта и целевого свойства анимации.  
  
 Чтобы применить анимацию к целевым объектам, перед <xref:System.Windows.Media.Animation.Storyboard> с помощью действия триггера или метода. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используется <xref:System.Windows.Media.Animation.BeginStoryboard> объекта с <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>, или <xref:System.Windows.DataTrigger>. В коде, можно также использовать <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метода.  
  
 В следующей таблице показаны в разных местах где каждого <xref:System.Windows.Media.Animation.Storyboard> начать прием поддерживается: каждого экземпляра, стиль, шаблон элемента управления и шаблон данных. Применение к конкретным экземплярам подразумевает применение анимации или раскадровки непосредственно к экземплярам объектов, а не в стилях, шаблонах элементов управления или шаблонах данных.  
  
|Раскадровка запускается с помощью метода...|Применение к конкретным экземплярам|Стиль|Шаблон элемента управления|Шаблон данных|Пример|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.EventTrigger>|Да|Да|Да|Да|[Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и свойство <xref:System.Windows.Trigger>|Нет|Да|Да|Да|[Запуск анимации при изменении значения свойства](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.DataTrigger>|Нет|Да|Да|Да|[Практическое руководство. Запуск анимации при изменении данных](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Да|Нет|Нет|Нет|[Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.FrameworkElement.Width%2A> из <xref:System.Windows.Shapes.Rectangle> элемент и <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> используется для рисования <xref:System.Windows.Shapes.Rectangle>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 В следующих разделах описаны <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> вложенные свойства более подробно.  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Элементы целевой платформы, элементы содержимого платформы и объекты Freezable  
 В предыдущем разделе упоминалось, что для поиска целевого объекта анимации необходимо знать имя целевого объекта и анимируемое свойство. Указание анимируемое свойство прост: просто установите <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> с именем анимируемое свойство.  Укажите имя объекта, для которого нужно анимировать, задав свойство <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> свойства анимации.  
  
 Для <xref:System.Windows.Setter.TargetName%2A> работы свойства целевого объекта должен иметь имя. Назначение имени для <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] отличается от назначения имени <xref:System.Windows.Freezable> объекта.  
  
 Элементами Framework являются те классы, которые наследуют от <xref:System.Windows.FrameworkElement> класса. Примеры элементов платформы <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>, и <xref:System.Windows.Shapes.Rectangle>. По существу все окна, панели и элементы управления являются элементами. Элементы содержимого Framework являются те классы, которые наследуют от <xref:System.Windows.FrameworkContentElement> класса. Примеры элементов содержимого framework <xref:System.Windows.Documents.FlowDocument> и <xref:System.Windows.Documents.Paragraph>. Если вы не уверены, что этот элемент является элементом платформы или элементом содержимого платформы, проверьте, есть ли у этого элемента свойство Name. Если есть, скорее всего, это элемент платформы или элемент содержимого платформы. Чтобы убедиться в этом, обратитесь к разделу "Иерархия наследования" на странице типа элемента.  
  
 Чтобы включить заданный элемент framework или элемент содержимого framework в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], задать его <xref:System.Windows.FrameworkElement.Name%2A> свойство. В коде также необходимо использовать <xref:System.Windows.NameScope.RegisterName%2A> метода для регистрации имени элемента с элементом, для которого был создан <xref:System.Windows.NameScope>.  
  
 В следующем примере, взяты из примера, присваивается имя `MyRectangle` <xref:System.Windows.Shapes.Rectangle>, тип <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 После того как элемент получил имя, вы можете анимировать свойство этого элемента.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable> типы являются те классы, которые наследуют от <xref:System.Windows.Freezable> класса. Примеры <xref:System.Windows.Freezable> включают <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>, и <xref:System.Windows.Media.GradientStop>.  
  
 Чтобы включить определение <xref:System.Windows.Freezable> анимация в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используется [директива x: Name](../../../../docs/framework/xaml-services/x-name-directive.md) присвоить имя. В коде используйте <xref:System.Windows.NameScope.RegisterName%2A> метода для регистрации имени с элементом, для которого был создан <xref:System.Windows.NameScope>.  
  
 В следующем примере присваивается имя <xref:System.Windows.Freezable> объекта.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 Затем этот объект можно выбрать в качестве целевого с помощью анимации.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> объекты используют области имен для разрешения <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> свойство. Дополнительные сведения об областях видимости имен WPF см. в разделе [Области видимости имен XAML в WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md). Если <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> свойство опущено, анимация обращается к элементам, на которой он определен, или, в случае стили элемента со стилем.  
  
 Иногда имя не может быть назначен <xref:System.Windows.Freezable> объекта. Например если <xref:System.Windows.Freezable> объявлен как ресурс или используется для задания значения свойства в стиле, ему нельзя присвоить имя. Так как у объекта нет имени, к нему нельзя обратиться напрямую, но можно обратиться косвенно. В следующих разделах описано, как обращаться к целевым объектам косвенно.  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>Косвенное обращение  
 Иногда <xref:System.Windows.Freezable> нельзя указать напрямую с помощью анимации, например когда <xref:System.Windows.Freezable> объявлен как ресурс или используется для задания значения свойства в стиле. Таким образом, несмотря на то, что вы не может ссылаться на него напрямую, можно по-прежнему анимировать <xref:System.Windows.Freezable> объекта. Вместо параметра <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> свойство с именем <xref:System.Windows.Freezable>, присвойте ему имя элемента, к которому <xref:System.Windows.Freezable> «документы». Например <xref:System.Windows.Media.SolidColorBrush> используется для задания <xref:System.Windows.Shapes.Shape.Fill%2A> прямоугольника элемент принадлежит к этому прямоугольнику. Чтобы анимировать кисть, необходимо установить анимации <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> с цепочкой свойств, начинается свойством элемента framework или элемента содержимого framework <xref:System.Windows.Freezable> используется для задания и заканчивается <xref:System.Windows.Freezable> анимируемое свойство.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Обратите внимание, что если <xref:System.Windows.Freezable> будет зафиксирован, будет создан клон и этот клон будет анимации. Если это происходит, исходный объект <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> продолжает возвращать свойство `false`, так как исходный объект не анимируется. Дополнительные сведения о клонировании см. в разделе [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Обратите внимание, что при косвенном обращении к целевым объектам можно обращаться к объектам, которых не существует. Например, можно предположить, что <xref:System.Windows.Controls.Control.Background%2A> конкретной кнопки был установлен <xref:System.Windows.Media.SolidColorBrush> и пытается анимировать ее цвет, когда на самом деле <xref:System.Windows.Media.LinearGradientBrush> используется для задания фона кнопки. В этих случаях исключение не возникает; анимация не имеет видимого эффекта, так как <xref:System.Windows.Media.LinearGradientBrush> не реагирует на изменения в <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойство.  
  
 В следующих разделах более подробно описан синтаксис косвенного обращения к целевым объектам.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Косвенное обращение к свойству объекта Freezable в XAML  
 Чтобы обратиться к свойству Freezable в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте следующий синтаксис.  
  
||  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* свойство <xref:System.Windows.FrameworkElement> которого <xref:System.Windows.Freezable> используется для задания, и  
  
-   *FreezablePropertyName* свойство <xref:System.Windows.Freezable> для анимации.  
  
 Ниже показано, как анимировать <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> используется для задания  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 Иногда требуется обратиться к объекту Freezable, который содержится в коллекции или массиве.  
  
 Чтобы обратиться к объекту Freezable, который содержится в коллекции, используйте следующий синтаксис пути.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Где *CollectionIndex* — это индекс объекта в его массива или коллекции.  
  
 Например, предположим, что прямоугольник имеет <xref:System.Windows.Media.TransformGroup> ресурс, примененный к его <xref:System.Windows.UIElement.RenderTransform%2A> свойство и требуется анимировать одно из содержащихся в нем преобразований.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 Ниже показано, как анимировать <xref:System.Windows.Media.RotateTransform.Angle%2A> свойство <xref:System.Windows.Media.RotateTransform> показано в предыдущем примере.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Косвенное обращение к свойству объекта Freezable в коде  
 Создайте в коде <xref:System.Windows.PropertyPath> объекта. При создании <xref:System.Windows.PropertyPath>, указать <xref:System.Windows.PropertyPath.Path%2A> и <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 Для создания <xref:System.Windows.PropertyPath.PathParameters%2A>, создать массив объектов типа <xref:System.Windows.DependencyProperty> , содержащий список поля идентификатора свойства зависимостей. Первое поле идентификатора используется для свойства <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> , <xref:System.Windows.Freezable> используется для задания. Следующее поле идентификатора представляет свойство <xref:System.Windows.Freezable> целевой объект. Представьте себе, как цепочка свойства, которое подключается <xref:System.Windows.Freezable> для <xref:System.Windows.FrameworkElement> объекта.  
  
 Ниже приведен пример цепочки свойств зависимостей, предназначенное <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> используется для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 Необходимо указать <xref:System.Windows.PropertyPath.Path%2A>. Объект <xref:System.Windows.PropertyPath.Path%2A> — <xref:System.String> сообщающее <xref:System.Windows.PropertyPath.Path%2A> способ интерпретации его <xref:System.Windows.PropertyPath.PathParameters%2A>. Для этого используется следующий синтаксис.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* — это индекс <xref:System.Windows.DependencyProperty> массив, содержащий идентификатор <xref:System.Windows.FrameworkElement> свойства объекта, <xref:System.Windows.Freezable> используется для задания, и  
  
-   *FreezablePropertyArrayIndex* — это индекс <xref:System.Windows.DependencyProperty> массив, который содержит идентификатор свойства целевой объект.  
  
 В следующем примере показан <xref:System.Windows.PropertyPath.Path%2A> , будет сопровождать <xref:System.Windows.PropertyPath.PathParameters%2A> определенный в предыдущем примере.
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 В следующем примере объединяются код в предыдущих примерах для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> используется для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 Иногда требуется обратиться к объекту Freezable, который содержится в коллекции или массиве. Например, предположим, что прямоугольник имеет <xref:System.Windows.Media.TransformGroup> ресурс, примененный к его <xref:System.Windows.UIElement.RenderTransform%2A> свойство и требуется анимировать одно из содержащихся в нем преобразований.  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Целевой объект <xref:System.Windows.Freezable> содержатся в коллекции, используйте следующий синтаксис пути.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 Где *CollectionIndex* — это индекс объекта в его массива или коллекции.  
  
 Целевой объект <xref:System.Windows.Media.RotateTransform.Angle%2A> свойство <xref:System.Windows.Media.RotateTransform>, второе преобразование в <xref:System.Windows.Media.TransformGroup>, следует ввести следующую <xref:System.Windows.PropertyPath.Path%2A> и <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 В примере показан полный код для анимации <xref:System.Windows.Media.RotateTransform.Angle%2A> из <xref:System.Windows.Media.RotateTransform> внутри <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Косвенное обращение с использованием объекта Freezable в качестве начальной точки  
 В предыдущих разделах описаны способы косвенной ссылки <xref:System.Windows.Freezable> , начиная с <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> и создания цепочки свойств к <xref:System.Windows.Freezable> подсвойств. Можно также использовать <xref:System.Windows.Freezable> качестве отправной точки и косвенной ссылки одного из его <xref:System.Windows.Freezable> вложенных свойств. Одно дополнительное ограничение применяется при использовании <xref:System.Windows.Freezable> отправной точки для косвенной ссылки: начальная <xref:System.Windows.Freezable> и каждый <xref:System.Windows.Freezable> между ним и косвенно целевой подсвойств должен не зафиксирован.  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Интерактивное управление раскадровкой в XAML  
 Запуск раскадровки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], используется <xref:System.Windows.Media.Animation.BeginStoryboard> запустить действие. <xref:System.Windows.Media.Animation.BeginStoryboard> распределяет анимации объекты и свойства и запускает раскадровкой. (Дополнительные сведения об этом процессе см. в разделе [анимации и общие сведения о синхронизации системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).) Если вы предоставите <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав его <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> свойства, можно упростить управляемой раскадровки. Вы можете затем интерактивно управлять раскадровкой после ее запуска. Ниже приведен список действий для управляемой раскадровки, которые используются совместно с триггерами событий для управления раскадровкой.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Приостанавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Перемещает раскадровки в конец периода заполнения, если он есть.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку.  
  
 В следующем примере показано использование действий для интерактивного управления раскадровкой.  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Интерактивное управление раскадровкой с помощью кода  
 В предыдущих примерах было показано, как анимировать свойства с помощью действий триггера. В коде можно также управлять раскадровкой с помощью интерактивных методов класса <xref:System.Windows.Media.Animation.Storyboard> класса. Для <xref:System.Windows.Media.Animation.Storyboard> сделать интерактивным в коде, необходимо использовать соответствующую перегрузку раскадровки <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод и укажите `true` чтобы сделать его управляемым. В разделе <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> более подробную информацию.  
  
 Ниже перечислены методы, которые можно использовать для управления <xref:System.Windows.Media.Animation.Storyboard> после его запуска:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 С помощью этих методов преимущество состоит в том, что не нужно создавать <xref:System.Windows.Trigger> или <xref:System.Windows.TriggerAction> объектов; можно просто требуется ссылка на управляемый <xref:System.Windows.Media.Animation.Storyboard> требуется работать.  
  
 **Примечание:** все интерактивные действия, выполняемые <xref:System.Windows.Media.Animation.Clock>и поэтому на <xref:System.Windows.Media.Animation.Storyboard> будет выполняться в следующем делении ядра времени, который произойдет незадолго перед следующей визуализацией. Например, если вы используете <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> способ перехода к другой точке в анимации, значение свойства не измениться мгновенно, вместо этого значение изменится на следующем делении ядра времени.  
  
 В следующем примере показано, как применение и управление анимацией с помощью интерактивных методов <xref:System.Windows.Media.Animation.Storyboard> класса.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>Анимация с использованием стилей  
 Можно использовать <xref:System.Windows.Media.Animation.Storyboard> объектов для определения анимации в <xref:System.Windows.Style>. Анимация с <xref:System.Windows.Media.Animation.Storyboard> в <xref:System.Windows.Style> аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в другом месте, со следующими тремя исключениями:  
  
-   Не указан <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; <xref:System.Windows.Media.Animation.Storyboard> всегда указывает элемент, к которому <xref:System.Windows.Style> применяется. Целевой объект <xref:System.Windows.Freezable> объектов, необходимо использовать косвенные ссылки. Дополнительные сведения о косвенных ссылках см. в разделе [косвенной ссылки](#pathsyntaxforchangeable) раздела.  
  
-   Нельзя указать <xref:System.Windows.EventTrigger.SourceName%2A> для <xref:System.Windows.EventTrigger> или <xref:System.Windows.Trigger>.  
  
-   Динамический ресурс ссылки или выражения привязки данных нельзя использовать для установки <xref:System.Windows.Media.Animation.Storyboard> или значения свойств для анимации. Это потому, что весь код внутри <xref:System.Windows.Style> должен быть поточно защищенным и система времени необходимо <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> сделать поточно-объекты. Объект <xref:System.Windows.Media.Animation.Storyboard> нельзя зафиксировать при его или ее дочерние временные шкалы содержит динамический ресурс ссылки или выражения привязки данных. Дополнительные сведения о фиксации и других <xref:System.Windows.Freezable> возможности, см. [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], нельзя объявлять обработчики событий для <xref:System.Windows.Media.Animation.Storyboard> или событий анимации.  
  
 Пример, показывающий, как определить раскадровку в стиле см. в разделе [анимировать в стиле](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) примере.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>Анимация в ControlTemplate  
 Можно использовать <xref:System.Windows.Media.Animation.Storyboard> объектов для определения анимации в <xref:System.Windows.Controls.ControlTemplate>. Анимация с <xref:System.Windows.Media.Animation.Storyboard> в <xref:System.Windows.Controls.ControlTemplate> аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в другом месте, с помощью следующих двух исключений:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Может обращаться только к дочерним объектам <xref:System.Windows.Controls.ControlTemplate>. Если <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> не указан, анимация обращается элемент, в который <xref:System.Windows.Controls.ControlTemplate> применяется.  
  
-   <xref:System.Windows.EventTrigger.SourceName%2A> Для <xref:System.Windows.EventTrigger> или <xref:System.Windows.Trigger> может обращаться только к дочерним объектам <xref:System.Windows.Controls.ControlTemplate>.  
  
-   Динамический ресурс ссылки или выражения привязки данных нельзя использовать для установки <xref:System.Windows.Media.Animation.Storyboard> или значения свойств для анимации. Это потому, что весь код внутри <xref:System.Windows.Controls.ControlTemplate> должен быть поточно защищенным и система времени необходимо <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> сделать поточно-объекты. Объект <xref:System.Windows.Media.Animation.Storyboard> нельзя зафиксировать при его или ее дочерние временные шкалы содержит динамический ресурс ссылки или выражения привязки данных. Дополнительные сведения о фиксации и других <xref:System.Windows.Freezable> возможности, см. [Freezable Общие сведения об объектах](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], нельзя объявлять обработчики событий для <xref:System.Windows.Media.Animation.Storyboard> или событий анимации.  
  
 Пример, показывающий, как определить раскадровку в <xref:System.Windows.Controls.ControlTemplate>, в разделе [анимировать в шаблоне ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) примере.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>Анимация при изменении значения свойства  
 В стилях и шаблонах элементов можно использовать объекты триггеров для запуска раскадровки при изменении свойства. Примеры см. в разделе [триггер анимации при изменении значения свойства](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) и [анимировать в шаблоне ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Анимации с помощью свойства <xref:System.Windows.Trigger> объекты ведут себя в сложнее, чем <xref:System.Windows.EventTrigger> анимации или анимации работы с использованием <xref:System.Windows.Media.Animation.Storyboard> методов.  Они «передаваться» с анимацией определенные другими <xref:System.Windows.Trigger> объектов, но объединено <xref:System.Windows.EventTrigger> и запустить метод анимации.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
