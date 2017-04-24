---
title: "Общие сведения о базовых элементах | Microsoft Docs"
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
  - "базовые элементы"
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Общие сведения о базовых элементах
Многие классы в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] являются производными от четырех классов, на которые в документации [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] часто ссылаются как на базовые классы элементов.  Этими классами являются <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement> <xref:System.Windows.ContentElement> и <xref:System.Windows.FrameworkContentElement>.  Класс <xref:System.Windows.DependencyObject> также связан, поскольку это общий базовый класс <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement>  
  
   
  
<a name="base_apis"></a>   
## Базовый элемент интерфейсов API в классах WPF  
 <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> являются производными от <xref:System.Windows.DependencyObject>, через несколько различных путей.  При разделении на этом уровне учитывается, как классы <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> используются в интерфейсе пользователя и для какой цели они применяются в приложении.  <xref:System.Windows.UIElement> также содержит <xref:System.Windows.Media.Visual> в иерархии классов. Этот класс предоставляет низкоуровневую поддержку графики, лежащую в основе [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  <xref:System.Windows.Media.Visual> предоставляет структуру отрисовки путем определения независимых прямоугольных областей экрана.  На практике <xref:System.Windows.UIElement> предназначен для элементов, которые будут поддерживать большую объектную модель и используются для отрисовки и применения макета в областях, которые можно описать как области прямоугольного экрана, и в которых модель содержимого намеренно более открыта, чтобы разрешить различные сочетания элементов.  <xref:System.Windows.ContentElement> не является производным от <xref:System.Windows.Media.Visual>; его модель <xref:System.Windows.ContentElement> будет принята какой\-либо еще, такой как программа чтения или просмотра, которая будет затем интерпретировать элементы и создавать законченный <xref:System.Windows.Media.Visual> для использования [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Определенные классы <xref:System.Windows.UIElement> предназначены для размещения содержимого: они обеспечивают размещение и отрисовку одного или нескольких классов <xref:System.Windows.ContentElement> \(<xref:System.Windows.Controls.DocumentViewer> является примером такого класса\).  <xref:System.Windows.ContentElement> используется как базовый класс для элементов с меньшими объектными моделями и элементов, предназначенных для текста, информации и содержимого документов, которые могут размещаться в <xref:System.Windows.UIElement>.  
  
### Уровень структуры и уровень ядра  
 <xref:System.Windows.UIElement> служит в качестве базового класса для <xref:System.Windows.FrameworkElement>, а <xref:System.Windows.ContentElement> служит в качестве базового класса для <xref:System.Windows.FrameworkContentElement>.  Причиной для этого следующего уровня классов является поддержка [уровня ядра WPF](GTMT), который отличается от [уровня структуры WPF](GTMT), с этим разделением также существуют, как и [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], разделенные между сборками PresentationCore и PresentationFramework.  [Уровень структуры WPF](GTMT) предоставляет более полное решение для нужд основного приложения, включая реализацию диспетчера макета для представления.  [уровень ядра WPF](GTMT) позволяет использовать большую часть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] без загрузки дополнительной сборки.  Различие между этими уровнями очень редко имеет значение для большинства обычных скриптов разработки приложения, и в общем вы должны представлять [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]как единое целое, и вам не нужно заботиться о разнице между [уровнем ядра WPF](GTMT) и [уровнем структуры WPF](GTMT).  Возможно, вам необходимо знать о различии уровней, если при разработке вашего приложения вам придется заменить значительное количество функциональных возможностей [уровня структуры WPF](GTMT), если ваше общее решение уже имеет свои собственные реализации композиции [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] и макет.  
  
<a name="subclassing_elements"></a>   
## Выбор элемента для наследования  
 Наиболее удобным способом создать другой класс, расширяющий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], является создание производного одного из классов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], откуда вы получите максимум ваших наследуемых функциональных возможностей через существующую иерархию класса.  В этом разделе перечислены возможности, поставляемые вместе с тремя наиболее важными классами элементов, которые помогут вам выбрать, из какого класса наследовать.  
  
 Если вы реализуете элемент управления, который в действительности является одним из наиболее распространенных причин для создания производного от класса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вам, возможно, потребуется создать класс, производный от класса, который является практическим элементом управления, базовым классом семейства элементов управления, или по крайней мере классом из базового класса <xref:System.Windows.Controls.Control>.  Некоторые рекомендации и практические примеры содержатся в [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Если вы не создаете элемент управления и вам надо создать производный от класса, находящегося выше в иерархии, то следующие разделы предназначены в качестве руководства того, какие характеристики определяются в каждом классе базового элемента.  
  
 Если вы создаете класс, производный от <xref:System.Windows.DependencyObject>, вы наследуете следующие функциональные возможности:  
  
-   Поддержку <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> и общую системную поддержку свойств.  
  
-   Возможность использовать [свойства зависимости](GTMT) и [вложенные свойства](GTMT), которые реализованы в качестве [свойств зависимостей](GTMT).  
  
 Если вы создаете класс, производный от <xref:System.Windows.UIElement>, вы наследуете следующие функциональные возможности в дополнение к предоставляемым <xref:System.Windows.DependencyObject>:  
  
-   Базовая поддержка для анимируемых значений свойств.  Дополнительные сведения см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Базовая поддержка событий ввода и поддержка команд.  Дополнительные сведения см. в разделах [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md) и [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
-   Виртуальные методы, которые могут быть переопределены, чтобы предоставить сведения системе макета.  
  
 Если вы создаете класс, производный от <xref:System.Windows.FrameworkElement>, вы наследуете следующие функциональные возможности в дополнение к предоставляемым <xref:System.Windows.UIElement>:  
  
-   Поддержка стилей и раскадровок.  Дополнительные сведения см. в разделах <xref:System.Windows.Style> и [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
-   Поддержка привязки данных.  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Поддержка ссылок динамического ресурса.  Дополнительные сведения см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Поддержка наследования значений свойств и другие флаги в метаданных, которые помогают уведомить о состояниях свойств службы структуры, таких как привязка данных, стили или реализация структуры макета.  Дополнительные сведения см. в разделе [Метаданные свойств среды](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Понятие [логического дерева](GTMT).  Дополнительные сведения см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
-   Поддержка практической реализации [уровня структуры WPF](GTMT) системы макета, включая переопределение <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>, которое может обнаружить изменения в свойствах, влияющих на макет.  
  
 Если вы создаете класс, производный от <xref:System.Windows.ContentElement>, вы наследуете следующие функциональные возможности в дополнение к предоставляемым <xref:System.Windows.DependencyObject>:  
  
-   Поддержка анимации.  Дополнительные сведения см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Базовая поддержка событий ввода и поддержка команд.  Дополнительные сведения см. в разделах [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md) и [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 Если вы создаете класс, производный от <xref:System.Windows.FrameworkContentElement>, вы наследуете следующие функциональные возможности в дополнение к предоставляемым <xref:System.Windows.ContentElement>:  
  
-   Поддержка стилей и раскадровок.  Дополнительные сведения см. в разделах <xref:System.Windows.Style> и [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Поддержка привязки данных.  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Поддержка ссылок динамического ресурса.  Дополнительные сведения см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Поддержка наследования значений свойств и другие флаги в метаданных, которые помогают уведомить о состояниях свойств службы структуры, таких как привязка данных, стили или реализация структуры макета.  Дополнительные сведения см. в разделе [Метаданные свойств среды](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Вы не наследуете доступ к изменениям системы макета \(например, <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\).  Реализации системы макета доступны только на <xref:System.Windows.FrameworkElement>.  Однако вы наследуете переопределение<xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>, которое может обнаружить изменения свойств, которые влияют на макет, и сообщить это любым узлам содержимого.  
  
 Модели содержимого описаны для различных классов.  Модель содержимого для класса является одним возможным фактором, который следует рассмотреть, если вам требуется найти соответствующий класс для наследования.  Дополнительные сведения см. в разделе [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## Другие базовые классы  
  
### Объект\-диспетчер  
 <xref:System.Windows.Threading.DispatcherObject> обеспечивает поддержку для поточной модели [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и включает все объекты, созданные для приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], связанных с <xref:System.Windows.Threading.Dispatcher>.  Даже если не создается производный объект от <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject> или <xref:System.Windows.Media.Visual>, следует рассмотреть создание производного объекта от <xref:System.Windows.Threading.DispatcherObject>, чтобы получить поддержку потоковой модели.  Дополнительные сведения см. в разделе [Модель потоков](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
### Визуальный элемент  
 <xref:System.Windows.Media.Visual> реализует концепцию 2D объекта, обычно требующего визуального представления в примерную прямоугольную область.  Фактическая отрисовка <xref:System.Windows.Media.Visual> происходит в других классах \(не автономно\), но класс <xref:System.Windows.Media.Visual> предоставляет известный тип, который используется в отображении процессов на различных уровнях.  <xref:System.Windows.Media.Visual> реализует проверку попадания курсора, но он не предоставляет события, сообщающие, что проверка попадания увенчалась успехом \(они располагаются в <xref:System.Windows.UIElement>\).  Дополнительные сведения см. в разделе [Программирование визуального слоя](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md).  
  
### Freezable  
 <xref:System.Windows.Freezable> имитирует постоянство в изменяемом объекте, предоставляя средства для создания копий объекта, когда постоянный объект требуется или необходим по причине производительности.  Тип <xref:System.Windows.Freezable> обеспечивает общую основу для определенных графических элементов, таких как геометрические формы и кисти, а также анимации.  Часто <xref:System.Windows.Freezable> не является <xref:System.Windows.Media.Visual>; он может содержать свойства, которые становятся подсвойствами, когда <xref:System.Windows.Freezable> применяется к заполнению значения свойства другого объекта, и эти подсвойства могут влиять на отрисовку.  Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> представляет собой производный класс <xref:System.Windows.Freezable>, который специально добавляет уровень управления анимацией и некоторые служебные члены, так что в настоящее время анимационные свойства могут быть выделены из неанимационных свойств.  
  
### Элемент управления  
 <xref:System.Windows.Controls.Control> является предполагаемым базовым классом для типа объекта, который называется либо элементом управления, либо компонентом, в зависимости от технологии.  В общем случае классы элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются классами, которые либо непосредственно представляют элемент управления пользовательского интерфейса или близко участствуют в композиции элемента управления.  Основной функциональной возможностью, которую предоставляет <xref:System.Windows.Controls.Control>, является шаблон элемента управления.  
  
## См. также  
 <xref:System.Windows.Controls.Control>   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Архитектура WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)