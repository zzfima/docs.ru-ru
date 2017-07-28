---
title: "Общие сведения о Storyboard | Microsoft Docs"
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
  - "Storyboard - синтаксис"
  - "синтаксис, Раскадровка"
  - "Временные шкалы"
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Общие сведения о Storyboard
В этом разделе показано использование объектов <xref:System.Windows.Media.Animation.Storyboard> для организации и применения анимации.  В нем описывается, как интерактивно использовать объекты <xref:System.Windows.Media.Animation.Storyboard>, а также синтаксис косвенного выбора свойств.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Предварительные требования  
 Чтобы разобраться в этом разделе, необходимо ознакомиться с различными типами анимации и их основными характеристиками.  Введение в анимацию см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Следует также знать, как использовать вложенные свойства зависимостей.  Дополнительные сведения о вложенных свойствах зависимостей см. в разделе [Общие сведения о вложенных свойствах зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## Что такое раскадровка?  
 Анимация является не единственным полезным типом шкалы времени.  Другие классы шкал времени так же используются для организации наборов шкал времени и их применения к свойствам.  Шкалы времени контейнера являются производными от класса <xref:System.Windows.Media.Animation.TimelineGroup> и включают <xref:System.Windows.Media.Animation.ParallelTimeline> и <xref:System.Windows.Media.Animation.Storyboard>.  
  
 <xref:System.Windows.Media.Animation.Storyboard> является типом шкалы времени контейнера, который содержит сведения о содержащихся в нем шкалах времени.  Раскадровка может содержать тип <xref:System.Windows.Media.Animation.Timeline>, включая другие временные шкалы контейнера и анимации.  Объекты <xref:System.Windows.Media.Animation.Storyboard> позволяют объединить временные шкалы, влияющие на различные объекты и свойства, в одно дерево временной шкалы, упрощая организацию и управление сложным поведением времени.  Предположим, требуется кнопка, которая выполняет следующие три действия.  
  
-   Увеличивается и изменяет цвет, когда пользователь выбирает кнопку.  
  
-   Сжимается, а затем увеличивается до исходного размера при нажатии.  
  
-   Сжимается и переходит в состояние 50\-процентной прозрачности при отключении.  
  
 В этом случае имеется несколько наборов анимаций, которые применяются к одному объекту и которые требуется воспроизвести в разное время в зависимости от состояния кнопки.  Объекты <xref:System.Windows.Media.Animation.Storyboard> позволяют организовывать анимации в группы и применять к одному или нескольким объектам.  
  
<a name="wherecanyouuseastoryboard"></a>   
## Где можно использовать Storyboard?  
 <xref:System.Windows.Media.Animation.Storyboard> можно использовать для анимации [свойств зависимости](GTMT) анимируемых классов \(дополнительные сведения о том, что делает класс анимируемым, см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)\).  Однако поскольку раскадровка является средством уровня структуры, объект должен относиться к <xref:System.Windows.NameScope> <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  
  
 Например, <xref:System.Windows.Media.Animation.Storyboard> можно использовать для:  
  
-   анимации <xref:System.Windows.Media.SolidColorBrush> \(не является элементом структуры\), которая рисует фон кнопок \(тип <xref:System.Windows.FrameworkElement>\),  
  
-   анимации <xref:System.Windows.Media.SolidColorBrush> \(не является элементом структуры\), которая рисует заливку <xref:System.Windows.Media.GeometryDrawing> \(не является элементом структуры\), которая отображается с помощью <xref:System.Windows.Controls.Image> \(<xref:System.Windows.FrameworkElement>\).  
  
-   В коде анимация <xref:System.Windows.Media.SolidColorBrush> объявляется с помощью класса, который также содержит <xref:System.Windows.FrameworkElement>, если <xref:System.Windows.Media.SolidColorBrush> зарегистрировал его имя с этим <xref:System.Windows.FrameworkElement>.  
  
 Однако, нельзя использовать <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.SolidColorBrush>, имя которого не зарегистрировано в качестве <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, или не было использовано для задания свойства <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## Как применить анимацию с использованием Storyboard  
 Чтобы использовать <xref:System.Windows.Media.Animation.Storyboard> для организации и применения анимации, следует добавить анимацию в качестве дочерней шкалы времени для <xref:System.Windows.Media.Animation.Storyboard>.  Класс <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> содержит вложенные свойства <xref:System.Windows.Media.Animation.Storyboard> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName>.  Эти свойства задаются для анимации, чтобы указать ее целевой объект и свойство.  
  
 Чтобы применить анимацию к целевому объекту, следует начать <xref:System.Windows.Media.Animation.Storyboard> с помощью действия триггера или метода.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] использует объект <xref:System.Windows.Media.Animation.BeginStoryboard> с <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger> или <xref:System.Windows.DataTrigger>.  В коде можно также использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 В следующей таблице приведены различные способы запуска <xref:System.Windows.Media.Animation.Storyboard>: для каждого экземпляра, стиля, шаблона элемента управления и шаблона данных. "  "Для каждого экземпляра" относится к способу применения анимации или раскадровки непосредственно к экземплярам объекта, а не к стилю, шаблону элемента управления или шаблону данных.  
  
|Запуск раскадровки при помощи…|"Для каждого экземпляра"|Стиль|Шаблон элемента управления|Шаблон данных|Пример|  
|------------------------------------|------------------------------|-----------|--------------------------------|-------------------|------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.EventTrigger>|Да|Да|Да|Да|[Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и свойство <xref:System.Windows.Trigger>|Нет|Да|Да|Да|[Запуск анимации при изменении значения свойства](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.DataTrigger>|Нет|Да|Да|Да|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/ru-ru/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Да|Нет|Нет|Нет|[Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 В следующем примере <xref:System.Windows.Media.Animation.Storyboard> используется для анимации <xref:System.Windows.FrameworkElement.Width%2A> элемента <xref:System.Windows.Shapes.Rectangle> и <xref:System.Windows.Media.SolidColorBrush.Color%2A> для <xref:System.Windows.Media.SolidColorBrush>, который используется для рисования <xref:System.Windows.Shapes.Rectangle>.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 В следующих разделах более подробно описываются вложенные свойства <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>.  
  
<a name="targetingelementsandfreezables"></a>   
## Выбор элементов Framework, элементов содержимого Framework и элементов Freezable  
 В предыдущем разделе упоминалось, что для поиска целевого объекта, анимация должна знать его имя и анимируемое свойство.  Указание свойства для анимации: просто задайте в <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName> имя анимируемого свойства.  Укажите имя объекта, свойство которого требуется анимировать, задав для свойства <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> значение анимации.  
  
 Для работы свойства <xref:System.Windows.Setter.TargetName%2A> целевой объект должен иметь имя.  Присвоение имени объекту <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] отличается от присвоения имени объекту <xref:System.Windows.Freezable>.  
  
 Элементами Framework являются те классы, которые наследуют от класса <xref:System.Windows.FrameworkElement>.  К элементам Framework относятся, например, <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button> и <xref:System.Windows.Shapes.Rectangle>.  По сути к ним относятся все окна, панели и элементы управления.  Элементами содержимого Framework являются те классы, которые наследуют от класса <xref:System.Windows.FrameworkContentElement>.  К элементам содержимого Framework относятся <xref:System.Windows.Documents.FlowDocument> и <xref:System.Windows.Documents.Paragraph>.  Если нет уверенности, является тип элементом Framework или элементом содержимого Framework, следует проверить наличие у него свойства Name.  Если имеется свойство Name, вероятно, что это элемент Framework или элемент содержимого Framework.  Чтобы убедиться в этом, следует проверить раздел **иерархии наследования** его страницы типа.  
  
 Чтобы включить заданный элемент Framework или элемент содержимого Framework в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], следует задать его свойство <xref:System.Windows.FrameworkElement.Name%2A>.  В коде также необходимо использовать метод <xref:System.Windows.NameScope.RegisterName%2A> для регистрации имени элемента с элементом, для которого был создан <xref:System.Windows.NameScope>.  
  
 В следующем примере, взятом из предыдущего примера, присваивается имя `MyRectangle` для <xref:System.Windows.Shapes.Rectangle>, типа <xref:System.Windows.FrameworkElement>.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 После того, как элемент получит имя, можно анимировать его свойство.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 Типы <xref:System.Windows.Freezable> являются классами, которые наследуют от класса <xref:System.Windows.Freezable>.  К примерам <xref:System.Windows.Freezable> относятся <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform> и <xref:System.Windows.Media.GradientStop>.  
  
 Чтобы включить настройку <xref:System.Windows.Freezable> с помощью анимации в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], следует использовать [Директива x:Name](../../../../docs/framework/xaml-services/x-name-directive.md) для назначения его имени.  В коде используется метод <xref:System.Windows.NameScope.RegisterName%2A> для регистрации его имени с элементом, для которого был создан <xref:System.Windows.NameScope>.  
  
 В следующем примере присваивается имя для объекта <xref:System.Windows.Freezable>.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 Затем объект может стать целевым объектом анимации.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 Объекты <xref:System.Windows.Media.Animation.Storyboard> используют области имен, чтобы разрешить свойство <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>.  Дополнительные сведения об области имен WPF см. в разделе [Области видимости имен XAML в WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  Если свойство <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> опущено, анимация применяется к элементам, на которых она определена, или к элементам стиля.  
  
 Иногда имя не может быть присвоено объекту <xref:System.Windows.Freezable>.  Например, если <xref:System.Windows.Freezable> объявлен как ресурс или используется для задания значения свойства в стиле, ему нельзя присвоить имя.  Поскольку он не имеет имени, к нему нельзя обращаться непосредственно, но можно делать это косвенно.  В следующих разделах объясняется, как использовать косвенные ссылки.  
  
<a name="pathsyntaxforchangeable"></a>   
## Косвенные ссылки  
 Бывают случаи, когда анимация не может ссылаться на <xref:System.Windows.Freezable> напрямую, например, когда <xref:System.Windows.Freezable> объявляется как ресурс или используется для задания значения свойства в стиле.  В этих случаях объект <xref:System.Windows.Freezable> все равно можно анимировать, даже при отсутствии возможности ссылаться на него напрямую.  Вместо задания свойства <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> с именем для <xref:System.Windows.Freezable> присвойте ему имя элемента, к которому <xref:System.Windows.Freezable> «принадлежит». Например, <xref:System.Windows.Media.SolidColorBrush>, используемый для задания <xref:System.Windows.Shapes.Shape.Fill%2A> прямоугольника, «принадлежит» к этому прямоугольнику.  Для анимации кисти следует задать элемент анимации <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> с цепочкой свойств, которая начинается свойством элемента Framework или элемента содержимого Framework, установленного с помощью <xref:System.Windows.Freezable>, и завершается анимируемым свойством <xref:System.Windows.Freezable>.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Обратите внимание, что если <xref:System.Windows.Freezable> зафиксирован, будет создан клон и этот клон будет анимироваться.  Если это происходит, свойство <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> исходного объекта продолжает возвращать значение `false`, так как исходный объект не анимируется.  Дополнительные сведения о клонировании см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Также обратите внимание, что использование косвенной ссылки на свойство позволяет ссылаться на несуществующий объект.  Например, можно предположить, что <xref:System.Windows.Controls.Control.Background%2A> конкретной кнопки был установлен с <xref:System.Windows.Media.SolidColorBrush> и пытается анимировать ее цвет, в то время как в действительности <xref:System.Windows.Media.LinearGradientBrush> используется для задания фона кнопки.  В этих случаях исключение не вызывается. Анимация не имеет видимого эффекта, так как <xref:System.Windows.Media.LinearGradientBrush> не реагирует на изменение свойства <xref:System.Windows.Media.SolidColorBrush.Color%2A>.  
  
 В следующих разделах синтаксис косвенной ссылки на свойство описывается более подробно.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### Косвенная ссылка на свойства Freezable в языке XAML  
 Чтобы обратиться к свойству Freezable в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], следует использовать следующий синтаксис.  
  
||  
|-|  
|*ElementPropertyName*`.`*FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* является свойством <xref:System.Windows.FrameworkElement>, которое задается с помощью <xref:System.Windows.Freezable>, а  
  
-   *FreezablePropertyName* является анимируемым свойством <xref:System.Windows.Freezable>.  
  
 В следующем коде показано, как анимировать <xref:System.Windows.Media.SolidColorBrush.Color%2A> для <xref:System.Windows.Media.SolidColorBrush>, который используется для задания  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.  
  
  
  
 Иногда требуется обратиться к элементу Freezable, содержащемуся в коллекции или массиве.  
  
 Чтобы обратиться к элементу Freezable, содержащемуся в коллекции, следует использовать следующий синтаксис пути.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Где *CollectionIndex* — это индекс объекта в массиве или коллекции.  
  
 Например, предположим, что прямоугольник имеет ресурс <xref:System.Windows.Media.TransformGroup>, который применяется к его свойству <xref:System.Windows.UIElement.RenderTransform%2A> и требуется анимировать одно из содержащихся в нем преобразований.  
  
  
  
 В следующем коде демонстрируется анимация свойства <xref:System.Windows.Media.RotateTransform.Angle%2A> для <xref:System.Windows.Media.RotateTransform>, как показано в предыдущем примере.  
  
  
  
<a name="targetingpropertyofchangeableincode"></a>   
### Косвенная ссылка на свойство элемента Freezable в коде  
 В коде можно создать объект <xref:System.Windows.PropertyPath>.  При создании <xref:System.Windows.PropertyPath>, указывается <xref:System.Windows.PropertyPath.Path%2A> и <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 Чтобы создать <xref:System.Windows.PropertyPath.PathParameters%2A>, следует создать массив типа <xref:System.Windows.DependencyProperty>, который содержит список полей идентификаторов свойств зависимостей.  Первое поле идентификатора используется для свойства <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, которое было задано с помощью <xref:System.Windows.Freezable>.  Следующее поле идентификатора представляет целевое свойство <xref:System.Windows.Freezable>.  Его следует представлять как цепочку свойств, которая соединяет <xref:System.Windows.Freezable> и объект <xref:System.Windows.FrameworkElement>.  
  
 Ниже приведен пример цепочки свойств зависимостей, которая обращается к <xref:System.Windows.Media.SolidColorBrush.Color%2A> для <xref:System.Windows.Media.SolidColorBrush>, который используется для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 Кроме того, необходимо указать <xref:System.Windows.PropertyPath.Path%2A>.  <xref:System.Windows.PropertyPath.Path%2A> является <xref:System.String>, которая указывает <xref:System.Windows.PropertyPath.Path%2A>, как интерпретировать его <xref:System.Windows.PropertyPath.PathParameters%2A>.  При этом используется следующий синтаксис.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(`*FreezablePropertyArrayIndex*`)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* — индекс массива <xref:System.Windows.DependencyProperty>, который содержит идентификатор свойства объекта <xref:System.Windows.FrameworkElement>, заданного с помощью <xref:System.Windows.Freezable>, а  
  
-   *FreezablePropertyArrayIndex*  — индекс массива <xref:System.Windows.DependencyProperty>, который содержит идентификатор целевого свойства.  
  
 В следующем примере показан <xref:System.Windows.PropertyPath.Path%2A>, который будет сопровождать <xref:System.Windows.PropertyPath.PathParameters%2A>, определенные в предыдущем примере.  
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 В следующем примере объединяется код из предыдущих примеров для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush> используемой для задания <xref:System.Windows.Shapes.Shape.Fill%2A> элемента прямоугольника.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 Иногда требуется обратиться к элементу Freezable, содержащемуся в коллекции или массиве.  Например, предположим, что прямоугольник имеет ресурс <xref:System.Windows.Media.TransformGroup>, который применяется к его свойству <xref:System.Windows.UIElement.RenderTransform%2A> и требуется анимировать одно из содержащихся в нем преобразований.  
  
 [!code-xml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Чтобы обратиться к <xref:System.Windows.Freezable>, содержащемуся в коллекции, следует использовать следующий синтаксис пути.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(` *CollectionChildrenPropertyArrayIndex*`)` `[`*CollectionIndex* `].(`*FreezablePropertyArrayIndex*`)`|  
  
 Где *CollectionIndex* — это индекс объекта в массиве или коллекции.  
  
 Для обращения к свойству <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform>, второго преобразования в <xref:System.Windows.Media.TransformGroup>, следует использовать следующий <xref:System.Windows.PropertyPath.Path%2A> и <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 В следующем примере показан полный код анимации <xref:System.Windows.Media.RotateTransform.Angle%2A> для <xref:System.Windows.Media.RotateTransform>, содержащегося внутри <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### Косвенная ссылка с использованием элемента Freezable в качестве начальной точки  
 В предыдущих разделах описаны способы косвенной ссылки на <xref:System.Windows.Freezable> с помощью запуска с <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> и создания цепочки свойств к подсвойству <xref:System.Windows.Freezable>.  Можно также использовать <xref:System.Windows.Freezable> в качестве отправной точки и косвенной ссылки на одно из его подсвойств <xref:System.Windows.Freezable>.  Одно дополнительное ограничение применяется при использовании <xref:System.Windows.Freezable> в качестве отправной точки для косвенной ссылки. Начальный <xref:System.Windows.Freezable> и ни один <xref:System.Windows.Freezable> между ним и целевым подсвойством не должен быть зафиксирован.  
  
<a name="controllable_storyboards"></a>   
## Интерактивное управление Storyboard в языке XAML  
 Чтобы запустить раскадровку в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], используйте действие триггера <xref:System.Windows.Media.Animation.BeginStoryboard>.  <xref:System.Windows.Media.Animation.BeginStoryboard> распределяет анимации объектам и анимируемым свойствам, а затем запускает раскадровку.  \(Дополнительные сведения об этом процессе см. в разделе [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).\) Если присвоить <xref:System.Windows.Media.Animation.BeginStoryboard> имя, задав его свойство <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>, раскадровка станет управляемой.  После запуска раскадровки ей можно будет управлять в интерактивном режиме.  Ниже приведен список действий управляемой раскадровки, которые используются с триггерами событий для управления раскадровкой.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: приостанавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: возобновляет приостановленную раскадровку.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: изменяет скорость раскадровки.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: перемещает раскадровку к концу ее периода заполнения, если он есть.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: останавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: удаляет раскадровку.  
  
 В следующем примере управляемые действия раскадровки используются для интерактивного управления раскадровкой.  
  
 [!code-xml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## Интерактивное управление раскадровкой с помощью кода  
 В предыдущих примерах показано, как выполнять анимацию с помощью действий триггера.  В коде можно также управлять раскадровкой с помощью интерактивных методов класса <xref:System.Windows.Media.Animation.Storyboard>.  Чтобы сделать <xref:System.Windows.Media.Animation.Storyboard> интерактивным в коде, необходимо использовать соответствующие перегрузки метода <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> раскадровки и указать `true`, чтобы сделать его управляемым.  Дополнительные сведения см. на странице <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>.  
  
 Ниже перечислены методы, которые могут быть использованы для управления <xref:System.Windows.Media.Animation.Storyboard> после его запуска.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 Преимущество использования этих методов заключается в том, что не требуется создавать объекты <xref:System.Windows.Trigger> или <xref:System.Windows.TriggerAction>. Просто требуется ссылка на управляемый <xref:System.Windows.Media.Animation.Storyboard>, которым требуется управлять.  
  
 **Примечание.** Все интерактивные действия, выполняемые на <xref:System.Windows.Media.Animation.Clock> и, соответственно, на <xref:System.Windows.Media.Animation.Storyboard>, будут выполнены на следующем делении ядра времени, который произойдет незадолго перед следующей визуализацией.  Например, при использовании метода <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> для перехода к другой точке в анимации, значение свойства не измениться мгновенно: оно изменится на следующем делении ядра времени.  
  
 В следующем примере демонстрируется применение и управление анимацией с помощью интерактивных методов класса <xref:System.Windows.Media.Animation.Storyboard>.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## Анимация с использованием стилей  
 Можно использовать объекты <xref:System.Windows.Media.Animation.Storyboard> для определения анимации в <xref:System.Windows.Style>.  Анимация с <xref:System.Windows.Media.Animation.Storyboard> в <xref:System.Windows.Style> аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в другом месте, но существуют три исключения:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> не задается; <xref:System.Windows.Media.Animation.Storyboard> всегда указывает элемент, к которому применяется <xref:System.Windows.Style>.  Для ссылки на объекты <xref:System.Windows.Freezable> необходимо использовать косвенные ссылки.  Дополнительные сведения о косвенных ссылках см. в разделе [Косвенные ссылки](#pathsyntaxforchangeable).  
  
-   Нельзя указать <xref:System.Windows.EventTrigger.SourceName%2A> для <xref:System.Windows.EventTrigger> или <xref:System.Windows.Trigger>.  
  
-   Нельзя использовать ссылки на динамические ресурсы или выражения привязки данных для задания значений свойств <xref:System.Windows.Media.Animation.Storyboard> или свойств анимации.  Это объясняется тем, что все внутри <xref:System.Windows.Style> должно быть потокобезопасным, и система расчета времени должна сделать объекты <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> потокобезопасными.  <xref:System.Windows.Media.Animation.Storyboard> не может быть зафиксирован, если он или его дочерние шкалы времени содержат ссылки на динамические ресурсы или выражения связывания данных.  Дополнительные сведения о фиксации и других возможностях <xref:System.Windows.Freezable> см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] нельзя объявить обработчик событий для <xref:System.Windows.Media.Animation.Storyboard> или событий анимации.  
  
 Пример, показывающий, как определить раскадровку в стиле, см. в разделе [Анимация с использованием стилей](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md).  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## Анимация в ControlTemplate  
 Можно использовать объекты <xref:System.Windows.Media.Animation.Storyboard> для определения анимации в <xref:System.Windows.Controls.ControlTemplate>.  Анимация с помощью <xref:System.Windows.Media.Animation.Storyboard> в <xref:System.Windows.Controls.ControlTemplate> в аналогична использованию <xref:System.Windows.Media.Animation.Storyboard> в другом месте, но существуют два исключения.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> может обращаться только к дочерним объектам <xref:System.Windows.Controls.ControlTemplate>.  Если <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> не указан, анимация обращается к элементам, к которым применяется <xref:System.Windows.Controls.ControlTemplate>.  
  
-   <xref:System.Windows.EventTrigger.SourceName%2A> для <xref:System.Windows.EventTrigger> или <xref:System.Windows.Trigger> может обращаться только к дочерним объектам <xref:System.Windows.Controls.ControlTemplate>.  
  
-   Нельзя использовать ссылки на динамические ресурсы или выражения привязки данных для задания значений свойств <xref:System.Windows.Media.Animation.Storyboard> или свойств анимации.  Это объясняется тем, что все внутри <xref:System.Windows.Controls.ControlTemplate> должно быть потокобезопасным, и система расчета времени должна сделать объекты <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> потокобезопасными.  <xref:System.Windows.Media.Animation.Storyboard> не может быть зафиксирован, если он или его дочерние шкалы времени содержат ссылки на динамические ресурсы или выражения связывания данных.  Дополнительные сведения о фиксации и других возможностях <xref:System.Windows.Freezable> см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] нельзя объявить обработчик событий для <xref:System.Windows.Media.Animation.Storyboard> или событий анимации.  
  
 Пример, показывающий, как определить раскадровку в <xref:System.Windows.Controls.ControlTemplate>, см. в разделе [Анимация в ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## Анимация при изменении значения свойства  
 В стилях и шаблонах элементов управления можно использовать объекты\-триггеры для запуска раскадровки при изменении свойств.  Примеры см. в разделах [Запуск анимации при изменении значения свойства](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) и [Анимация в ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Запуск анимации с помощью свойства объектов <xref:System.Windows.Trigger> выполняется сложнее, чем анимация <xref:System.Windows.EventTrigger>, или анимация с помощью методов <xref:System.Windows.Media.Animation.Storyboard>.  Она «перекликается» с анимацией, определенной другими объектами <xref:System.Windows.Trigger>, но состоит из <xref:System.Windows.EventTrigger> и анимации, запускаемой методами.  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)