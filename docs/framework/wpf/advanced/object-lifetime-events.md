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
ms.openlocfilehash: c0858a0194bc0e9efa60a42d4029bdba9f4f3fef
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458574"
---
# <a name="object-lifetime-events"></a>События времени жизни объекта
В этом разделе описываются определенные события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обозначающие этапы создания, использования и удаления времени жизни объекта.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Необходимые компоненты  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](dependency-properties-overview.md). Чтобы выполнить примеры в этом разделе, следует также иметь представление о [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (см. раздел [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)) и знать, как создаются приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>События времени жизни объекта  
 Все объекты в управляемом коде платформы Microsoft .NET Framework проходят по аналогичному набору этапов жизни, создания, использования и уничтожения. Многие объекты также имеют этап завершения, который возникает как часть этапа удаления. Объекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно визуальные объекты, которые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет как элементы, также имеют набор общих этапов жизни объекта. Модель приложений и модель программирования [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляют эти этапы как последовательность событий. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] существует четыре основных типа объектов, связанных с событиями времени жизни: элементы в целом, элементы окна, узлы навигации и объекты приложения. Узлы окон и навигации также входят в более крупные группы визуальных объектов (элементов). В этом разделе описываются события времени жизни, которые являются общими для всех элементов, а затем даются общие сведения о конкретных событиях, которые относятся к определениям приложений, узлам окон или навигации.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Общие события времени жизни для элементов  
 Любой элемент уровня платформы WPF (объекты, производные от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>) имеет три общих события времени существования: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>и <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>инициализированные  
 Сначала вызывается <xref:System.Windows.FrameworkElement.Initialized>, и примерно соответствует инициализации объекта с помощью вызова его конструктора. Поскольку событие происходит в ответ на инициализацию, можно гарантировать, что все свойства объекта установлены. (Исключением являются использование выражений, таких как динамические ресурсы или привязка; эти выражения будут неоцененными.) Как следствие того, что все свойства заданы, последовательность <xref:System.Windows.FrameworkElement.Initialized>, создаваемых вложенными элементами, которые определены в разметке, выполняется в порядке первых элементов в дереве элементов, а потом родительские элементы к корню. Этот порядок обусловлен тем, что отношения и вложения «родитель/потомок» являются свойствами, и поэтому родитель не может завершить инициализацию, пока дочерние элементы, указанные в свойстве, не будут полностью инициализированы.  
  
 При написании обработчиков в ответ на событие <xref:System.Windows.FrameworkElement.Initialized> необходимо учитывать, что не существует гарантии, что все остальные элементы в дереве элементов (логическое дерево или визуальное дерево), где был присоединен обработчик, были созданы, особенно родительские элементов. Переменные члены могут быть null, или источники данных могут быть еще не заполненными через базовую привязку (даже на уровне выражения).  
  
### <a name="loaded"></a>Загружен  
 Далее вызывается <xref:System.Windows.FrameworkElement.Loaded>. Событие <xref:System.Windows.FrameworkElement.Loaded> возникает перед завершающей отрисовкой, но после того, как система макета вычислила все необходимые значения для подготовки к просмотру. <xref:System.Windows.FrameworkElement.Loaded> предполагает, что логическое дерево, в котором содержится элемент, завершено и подключается к источнику представления, который предоставляет HWND и область отрисовки. Стандартная привязка данных (привязка к локальным источникам, таким как другие свойства или непосредственно определенные источники данных) будет выполнена до <xref:System.Windows.FrameworkElement.Loaded>. Асинхронная привязка данных (к внешним или динамическим источникам) может произойти, но по определению асинхронности не обязательно произойдет.  
  
 Механизм, с помощью которого вызывается событие <xref:System.Windows.FrameworkElement.Loaded>, отличается от <xref:System.Windows.FrameworkElement.Initialized>. Событие <xref:System.Windows.FrameworkElement.Initialized> вызывается элементом по элементу без непосредственной координации завершенного дерева элементов. Напротив, событие <xref:System.Windows.FrameworkElement.Loaded> вызывается как координированное усилия во всем дереве элементов (в частности, в логическом дереве). Когда все элементы в дереве находятся в состоянии, в котором они считаются загруженными, событие <xref:System.Windows.FrameworkElement.Loaded> впервые возникает в корневом элементе. Затем событие <xref:System.Windows.FrameworkElement.Loaded> создается последовательно для каждого дочернего элемента.  
  
> [!NOTE]
> Такое поведение может внешне напоминать туннелирование для перенаправленного события. Тем не менее информация не переносится от события к событию. Каждый элемент всегда имеет возможность обрабатывать свое <xref:System.Windows.FrameworkElement.Loaded> событие, и пометка данных события как обработанных не влияет на этот элемент.  
  
### <a name="unloaded"></a>Выгружен  
 <xref:System.Windows.FrameworkElement.Unloaded> вызывается последним и инициируется источником презентации или удаляемым визуальным элементом. При возникновении и обработке <xref:System.Windows.FrameworkElement.Unloaded> элемент, который является родительским источником события (как определено свойством <xref:System.Windows.FrameworkElement.Parent%2A>) или любой заданный элемент в логических или визуальных деревьях, может быть уже удален, что означает, что привязка данных, ссылки на ресурсы и стили не может быть задано как стандартное или Последнее известное значение времени выполнения.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Элементы модели приложений событий времени жизни  
 Создание общих событий времени существования для элементов — это следующие элементы модели приложения: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>и <xref:System.Windows.Controls.Frame>. Они расширяют общие события времени жизни дополнительными событиями, которые связаны с их конкретными целями. Эти темы подробно рассматриваются в следующих разделах.  
  
- <xref:System.Windows.Application>. [Общие сведения об управлении приложениями](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Общие сведения об окнах WPF](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>и <xref:System.Windows.Controls.Frame>: [Общие сведения о навигации](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>См. также

- [Приоритет значения свойства зависимостей](dependency-property-value-precedence.md)
- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
