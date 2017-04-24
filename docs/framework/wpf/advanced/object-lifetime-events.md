---
title: "События времени жизни объекта | Microsoft Docs"
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
  - "События - активированные"
  - "объекты приложения, события времени жизни"
  - "классы, Frame"
  - "классы, NavigationWindow"
  - "События - закрытые"
  - "События - закрытие"
  - "ContentRendered - события"
  - "события - деактивированные"
  - "события, активированные"
  - "события, Закрытый"
  - "события, закрытие"
  - "события, ContentRendered"
  - "события, деактивированные"
  - "события, инициализированные"
  - "события, Загруженные"
  - "события, выгружаемые"
  - "события выхода"
  - "Frame - класс"
  - "Инициализированные события"
  - "события времени жизни объектов"
  - "загружаемые события"
  - "NavigationWindow - класс"
  - "объекты - события времени жизни"
  - "запуск - события"
  - "События - выгружаемые"
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# События времени жизни объекта
В этом разделе описываются конкретные события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обозначающие этапы времени жизни объекта, а именно создание, использование и уничтожение.  
  
   
  
<a name="prerequisites"></a>   
## Предварительные требования  
 В этом разделе предполагается, что вы понимаете [свойства зависимости](GTMT) с точки зрения потребителя существующих свойств зависимости классов [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомлены с разделом [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Чтобы следовать примерам в этой главе, необходимо также понимать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] \(см. [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)\) и знать как писать приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## События времени жизни объекта  
 Все объекты в управляемом коде [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] проходят через один и тот же набор жизненных этапов, а именно создание, использование и уничтожение.  У многих объектов также существует этап завершения как часть этапа уничтожения.  Объекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно визуальные объекты, которые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет как элементы, также имеют набор общих этапов жизни объекта.  Программирование [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и модели приложений предоставляет эти этапы как последовательность событий.  Существуют четыре основных типа объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по отношению к времени жизни события; элементы в общем, элементы окна, узлы переходов и объекты приложения.  узлы окон и переходов также подвергаются группировке визуальных объектов \(элементов\).  В этом разделе описываются события времени жизни, которые являются общими для всех элементов, а затем представлены конкретные, которые применяются к определениям приложений, узлам окон и переходов.  
  
<a name="common_events"></a>   
## Общие для элементов события времени жизни  
 Любой элемент [уровня WPF framework](GTMT) \(объекты, производные от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>\) имеют три общих события времени жизни: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, и <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### Initialized  
 <xref:System.Windows.FrameworkElement.Initialized> возникает первым и примерно соответствует инициализации объекта при вызове его конструктора.  Так как событие произошло в ответ на инициализацию, есть гарантия, что все свойства объекта установлены.  \(Исключением является применение таких выражений, как динамические ресурсы или привязки; это будут необработанные выражения.\) Как следствие потребностей, установленных для всем свойств, последовательность <xref:System.Windows.FrameworkElement.Initialized>, вызванных вложенными элементами, которые определены в разметке, сначала отображается в порядке вложенности элементов в дереве элементов, затем от родительского элемента к корню.  Этот последовательность вызвана тем, что связь типа «родители\-потомки» и объединение являются свойствами, и, таким образом, родитель не завершит инициализацию до тех пор, пока дочерние элементы, заполняющие свойство, также не будут полностью инициализированы.  
  
 При написании обработчика в ответ на событие <xref:System.Windows.FrameworkElement.Initialized> следует учитывать, что нет гарантии, что все остальные элементы в дереве элементов \([логическом дереве](GTMT) или [визуальном дереве](GTMT)\), к которому прикреплен обработчик, уже были созданы, особенно родительские элементы.  Переменные\-члены могут быть NULL, или источники данных могут не еще заполняться через базовую привязку \(даже на уровне выражения\).  
  
### Loaded  
 <xref:System.Windows.FrameworkElement.Loaded> вызывается далее.  Событие <xref:System.Windows.FrameworkElement.Loaded> создается перед окончательной отрисовкой, но после того, как система макета вычислила все необходимые значения для отображения.  Из события <xref:System.Windows.FrameworkElement.Loaded> следует, что логическое дерево, в котором содержится элемент, готово и связано с источником представления, который предоставляет HWND и поверхность для отрисовки.  Стандартная привязка данных \(привязка к локальному источнику, такому как другие свойства или явно определенные источник данных\) произойдет до <xref:System.Windows.FrameworkElement.Loaded>.  Асинхронная привязка данных \(к внешнем или динамическим источникам\) может произойти, но, по определению асинхронности, нет гарантии, что она произошла.  
  
 Механизм, по которому возникает событие <xref:System.Windows.FrameworkElement.Loaded>, отличается от <xref:System.Windows.FrameworkElement.Initialized>.  Событие <xref:System.Windows.FrameworkElement.Initialized> является вызванным элементом, без прямого согласования с завершенным деревом элементов.  Напротив, событие <xref:System.Windows.FrameworkElement.Loaded> вызывается в качестве согласованного усилия по всему дереву элементов \(в частности, [логическому дереву](GTMT)\).  Когда все элементы в дереве находятся в состоянии, в котором они считаются загруженными, событие <xref:System.Windows.FrameworkElement.Loaded> сначала вызывается в корневом элементе.  Затем событие <xref:System.Windows.FrameworkElement.Loaded> вызывается последовательно для каждого дочернего элемента.  
  
> [!NOTE]
>  Такое поведение может внешне напоминать нисходящую маршрутизацию [маршрутизированного события](GTMT).  Однако, сведения не переносятся от события к событию.  Каждый элемент всегда имеет возможность обработать свое событие <xref:System.Windows.FrameworkElement.Loaded>, и пометить данные о событии, как не имеющие эффекта за пределами этого элемента.  
  
### Unloaded  
 <xref:System.Windows.FrameworkElement.Unloaded> вызывается последним и инициируется источником представления или визуальным родительским элементом при его удалении.  Когда <xref:System.Windows.FrameworkElement.Unloaded> возникает и обрабатывается, элемент, который является родительским источником события \(как определено свойством <xref:System.Windows.FrameworkElement.Parent%2A>\), или любой заданный элемент в логических или визуальных деревьях могут уже быть сброшен, что означает, что связывание данных, ссылки на ресурсы и стили могут быть не установлены в обычное или последнее известное значение времени выполнения.  
  
<a name="application_model_elements"></a>   
## Элементы модели приложения событий времени жизни  
 Следующие элементы модели приложения построены на общих событиях времени жизни: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, и <xref:System.Windows.Controls.Frame>.  Это расширяет общие события времени жизни дополнительными событиями, предназначенными для определенных целей.  Они описаны в подробно в следующих разделах:  
  
-   <xref:System.Windows.Application>: [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Общие сведения об окнах WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, и <xref:System.Windows.Controls.Frame>: [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
## См. также  
 [Приоритет значения свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)