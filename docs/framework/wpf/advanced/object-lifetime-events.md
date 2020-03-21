---
title: События времени жизни объекта
ms.date: 03/30/2017
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
ms.openlocfilehash: 3b761674bd2464ee87e07d9299c805431f8fdeb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141111"
---
# <a name="object-lifetime-events"></a>События времени жизни объекта
В этом разделе описываются определенные события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обозначающие этапы создания, использования и удаления времени жизни объекта.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](dependency-properties-overview.md). Чтобы выполнить примеры в этом разделе, следует также иметь представление о [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (см. раздел [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)) и знать, как создаются приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>
## <a name="object-lifetime-events"></a>События времени жизни объекта  
 Все объекты в управляемом коде Microsoft .NET Framework проходят аналогичный набор этапов жизни, создания, использования и разрушения. Многие объекты также имеют этап завершения, который возникает как часть этапа удаления. Объекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно визуальные объекты, которые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет как элементы, также имеют набор общих этапов жизни объекта. Модель приложений и модель программирования [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляют эти этапы как последовательность событий. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] существует четыре основных типа объектов, связанных с событиями времени жизни: элементы в целом, элементы окна, узлы навигации и объекты приложения. Узлы окон и навигации также входят в более крупные группы визуальных объектов (элементов). В этом разделе описываются события времени жизни, которые являются общими для всех элементов, а затем даются общие сведения о конкретных событиях, которые относятся к определениям приложений, узлам окон или навигации.  
  
<a name="common_events"></a>
## <a name="common-lifetime-events-for-elements"></a>Общие события времени жизни для элементов  
 Любой элемент уровня WPF (эти объекты, вытекающие <xref:System.Windows.FrameworkElement> из любого или) <xref:System.Windows.FrameworkContentElement>имеет три общих события жизни: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>и <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>инициализированные  
 <xref:System.Windows.FrameworkElement.Initialized>поднят во-первых, и примерно соответствует инициализации объекта путем вызова к его конструктору. Поскольку событие происходит в ответ на инициализацию, можно гарантировать, что все свойства объекта установлены. (Исключением являются использование выражений, такие как динамические ресурсы или связывание; это будут неоцененные выражения.) Как следствие требования о наборе всех свойств, <xref:System.Windows.FrameworkElement.Initialized> последовательность поднятия вложенными элементами, которые определяются в разметке, как представляется, происходит в порядке самых глубоких элементов в дереве элемента, а затем родительских элементов к корню. Этот порядок обусловлен тем, что отношения и вложения «родитель/потомок» являются свойствами, и поэтому родитель не может завершить инициализацию, пока дочерние элементы, указанные в свойстве, не будут полностью инициализированы.  
  
 Когда вы пишете обработчики в ответ на <xref:System.Windows.FrameworkElement.Initialized> событие, вы должны учитывать, что нет никакой гарантии, что все другие элементы в дереве элементов (логическое дерево или визуальное дерево) вокруг, где обработчик прилагается были созданы, особенно родительские элементы. Переменные члены могут быть null, или источники данных могут быть еще не заполненными через базовую привязку (даже на уровне выражения).  
  
### <a name="loaded"></a>Загружен  
 <xref:System.Windows.FrameworkElement.Loaded>поднимается следующим. Событие <xref:System.Windows.FrameworkElement.Loaded> поднимается до окончательного рендеринга, но после того, как система компоновки рассчитала все необходимые значения для рендеринга. <xref:System.Windows.FrameworkElement.Loaded>влечет за собой завершение логического дерева, в котором содержится элемент, и подключается к источнику презентации, обеспечивающему HWND и поверхность рендеринга. Стандартная привязка данных (привязка к местным источникам, таким <xref:System.Windows.FrameworkElement.Loaded>как другие свойства или непосредственно определенные источники данных) будет происходить до . Асинхронная привязка данных (к внешним или динамическим источникам) может произойти, но по определению асинхронности не обязательно произойдет.  
  
 Механизм, с <xref:System.Windows.FrameworkElement.Loaded> помощью которого <xref:System.Windows.FrameworkElement.Initialized>происходит событие отличается от . Событие <xref:System.Windows.FrameworkElement.Initialized> поднимается элемент за элементом, без прямой координации завершенным деревом элемента. В отличие <xref:System.Windows.FrameworkElement.Loaded> от этого, событие поднимается как скоординированное усилие по всему дереву элементов (в частности, логическое дерево). Когда все элементы дерева находятся в состоянии, <xref:System.Windows.FrameworkElement.Loaded> когда они считаются загруженными, событие сначала поднимается на корневой элемент. Затем <xref:System.Windows.FrameworkElement.Loaded> событие последовательно поднимается на каждый элемент ребенка.  
  
> [!NOTE]
> Такое поведение может внешне напоминать туннелирование для перенаправленного события. Тем не менее информация не переносится от события к событию. Каждый элемент всегда имеет <xref:System.Windows.FrameworkElement.Loaded> возможность обрабатывать свое событие, и маркировка данных события в качестве обрабатываемых не имеет никакого эффекта за пределами этого элемента.  
  
### <a name="unloaded"></a>Выгружен  
 <xref:System.Windows.FrameworkElement.Unloaded>поднимается последним и инициируется либо источником презентации, либо визуальным родителем, удаляется. При <xref:System.Windows.FrameworkElement.Unloaded> поднятии и обработке элемент, который является родителем источника событий (определяемым свойством) или любым определенным элементом <xref:System.Windows.FrameworkElement.Parent%2A> вверх в логических или визуальных деревьях, может быть уже неустановлен, а это означает, что связывание данных, ссылки на ресурсы и стили не могут быть установлены на их нормальное или последнее известное значение времени выполнения.  
  
<a name="application_model_elements"></a>
## <a name="lifetime-events-application-model-elements"></a>Элементы модели приложений событий времени жизни  
 Основываясь на общих событиях жизни для <xref:System.Windows.Application>элементов следующие элементы модели приложения: , <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationWindow>и <xref:System.Windows.Controls.Frame>. Они расширяют общие события времени жизни дополнительными событиями, которые связаны с их конкретными целями. Эти темы подробно рассматриваются в следующих разделах.  
  
- <xref:System.Windows.Application>: [Обзор управления приложениями](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Обзор Windows WPF](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>и : [Навигация Обзор](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Приоритет стоимости свойств зависимости](dependency-property-value-precedence.md)
- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
