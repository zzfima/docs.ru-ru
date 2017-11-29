---
title: "События времени жизни объекта"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e31997cfc1ff7500317bdfc59ac6ad12d3d27a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-lifetime-events"></a>События времени жизни объекта
В этом разделе описываются определенные события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обозначающие этапы создания, использования и удаления времени жизни объекта.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Чтобы выполнить примеры в этом разделе, следует также иметь представление о [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (см. раздел [Обзор XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)) и знать, как создаются приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>События времени жизни объекта  
 Все объекты в управляемом коде [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] проходят через одни и те же этапы создания, использования и удаления. Многие объекты также имеют этап завершения, который возникает как часть этапа удаления. Объекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно визуальные объекты, которые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет как элементы, также имеют набор общих этапов жизни объекта. Модель приложений и модель программирования [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляют эти этапы как последовательность событий. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] существует четыре основных типа объектов, связанных с событиями времени жизни: элементы в целом, элементы окна, узлы навигации и объекты приложения. Узлы окон и навигации также входят в более крупные группы визуальных объектов (элементов). В этом разделе описываются события времени жизни, которые являются общими для всех элементов, а затем даются общие сведения о конкретных событиях, которые относятся к определениям приложений, узлам окон или навигации.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Общие события времени жизни для элементов  
 Любой элемент уровня платформы WPF (эти объекты, производные от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>) имеет три общие события времени жизни: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>, и <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>инициализированные  
 <xref:System.Windows.FrameworkElement.Initialized>Сначала вызывается и примерно соответствует инициализации объекта при вызове его конструктору. Поскольку событие происходит в ответ на инициализацию, можно гарантировать, что все свойства объекта установлены. (Исключением является использование таких выражений, как динамические ресурсы или привязки; это будут необработанные выражения.) Как следствие, заданы все свойства, требование последовательность <xref:System.Windows.FrameworkElement.Initialized> , вызванных вложенными элементами, которые определены в разметке в порядке вложенности элементов в дереве элементов сначала отображается, затем от родительского элемента к корню. Этот порядок обусловлен тем, что отношения и вложения «родитель/потомок» являются свойствами, и поэтому родитель не может завершить инициализацию, пока дочерние элементы, указанные в свойстве, не будут полностью инициализированы.  
  
 При написании обработчика в ответ на <xref:System.Windows.FrameworkElement.Initialized> событий, необходимо учитывать, что нет никакой гарантии, что все остальные элементы в дереве элементов (логического дерева или визуального дерева), по которому присоединен обработчик были созданы, особенно родительские элементы. Переменные члены могут быть null, или источники данных могут быть еще не заполненными через базовую привязку (даже на уровне выражения).  
  
### <a name="loaded"></a>Загружен  
 <xref:System.Windows.FrameworkElement.Loaded>вызывается далее. <xref:System.Windows.FrameworkElement.Loaded> События до окончательной подготовки отчетов, но после система макета вычислила все необходимые значения для подготовки к просмотру. <xref:System.Windows.FrameworkElement.Loaded>влечет за собой логического дерева, в котором элемент завершения, которое подключается к источнику презентации, который предоставляет HWND и поверхность для отрисовки. Стандартная привязка данных (привязки локальных источников, таких как другие свойства или явно определенные источник данных) произойдет до <xref:System.Windows.FrameworkElement.Loaded>. Асинхронная привязка данных (к внешним или динамическим источникам) может произойти, но по определению асинхронности не обязательно произойдет.  
  
 Механизм, по которому <xref:System.Windows.FrameworkElement.Loaded> события отличается от <xref:System.Windows.FrameworkElement.Initialized>. <xref:System.Windows.FrameworkElement.Initialized> Событие является вызванным элементом, без прямого согласования с завершенным деревом элементов. В отличие от этого <xref:System.Windows.FrameworkElement.Loaded> событие вызывается в качестве согласованного усилия по всему дереву элементов (в частности, логическое дерево). Если все элементы в дереве находятся в состоянии, где они считаются загружены <xref:System.Windows.FrameworkElement.Loaded> сначала события для корневого элемента. <xref:System.Windows.FrameworkElement.Loaded> Затем события последовательно для каждого дочернего элемента.  
  
> [!NOTE]
>  Такое поведение может внешне напоминать туннелирование для перенаправленного события. Тем не менее информация не переносится от события к событию. Каждый элемент всегда имеет возможность обработать его <xref:System.Windows.FrameworkElement.Loaded> событий и пометить данные о событии как обработанное не оказывает влияния за пределами этого элемента.  
  
### <a name="unloaded"></a>Выгружен  
 <xref:System.Windows.FrameworkElement.Unloaded>вызывается последним и инициируется источником представления или удаления визуального родителя. Когда <xref:System.Windows.FrameworkElement.Unloaded> возникает и обрабатывается, элемент, который является родительским источником события (как определено <xref:System.Windows.FrameworkElement.Parent%2A> свойство) или любой заданный элемент в логических или визуальных деревьях могут уже быть сброшен, это означает, что связывание данных, ссылки на ресурсы , и стили, не могут быть установлены в обычное или последнее известное значение времени выполнения.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Элементы модели приложений событий времени жизни  
 Основываясь на общие события времени жизни для элементов являются следующие элементы модели приложения: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, и <xref:System.Windows.Controls.Frame>. Они расширяют общие события времени жизни дополнительными событиями, которые связаны с их конкретными целями. Эти темы подробно рассматриваются в следующих разделах.  
  
-   <xref:System.Windows.Application>: [Общие сведения об управлении приложения](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [Обзор Windows WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, и <xref:System.Windows.Controls.Frame>: [Общие сведения о навигации](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Приоритет значения свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
