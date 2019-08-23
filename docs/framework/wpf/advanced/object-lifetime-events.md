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
ms.openlocfilehash: dd2e116c4241a44786af3a56b931b0c3c0571814
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933486"
---
# <a name="object-lifetime-events"></a>События времени жизни объекта
В этом разделе описываются определенные события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обозначающие этапы создания, использования и удаления времени жизни объекта.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](dependency-properties-overview.md). Чтобы выполнить примеры в этом разделе, следует также иметь представление о [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (см. раздел [Обзор XAML (WPF)](xaml-overview-wpf.md)) и знать, как создаются приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="object-lifetime-events"></a>События времени жизни объекта  
 Все объекты в управляемом коде платформы Microsoft .NET Framework проходят по аналогичному набору этапов жизни, создания, использования и уничтожения. Многие объекты также имеют этап завершения, который возникает как часть этапа удаления. Объекты [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], особенно визуальные объекты, которые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет как элементы, также имеют набор общих этапов жизни объекта. Модель приложений и модель программирования [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляют эти этапы как последовательность событий. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] существует четыре основных типа объектов, связанных с событиями времени жизни: элементы в целом, элементы окна, узлы навигации и объекты приложения. Узлы окон и навигации также входят в более крупные группы визуальных объектов (элементов). В этом разделе описываются события времени жизни, которые являются общими для всех элементов, а затем даются общие сведения о конкретных событиях, которые относятся к определениям приложений, узлам окон или навигации.  
  
<a name="common_events"></a>   
## <a name="common-lifetime-events-for-elements"></a>Общие события времени жизни для элементов  
 Любой элемент уровня среды WPF <xref:System.Windows.FrameworkElement> (объекты, производные от или <xref:System.Windows.FrameworkContentElement>) имеют три общих события времени существования: <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded>и <xref:System.Windows.FrameworkElement.Unloaded>.  
  
### <a name="initialized"></a>инициализированные  
 <xref:System.Windows.FrameworkElement.Initialized>вызывается первым, и примерно соответствует инициализации объекта с помощью вызова его конструктора. Поскольку событие происходит в ответ на инициализацию, можно гарантировать, что все свойства объекта установлены. (Исключением является использование таких выражений, как динамические ресурсы или привязки; это будут необработанные выражения.) В результате требования, чтобы все свойства были заданы, последовательность <xref:System.Windows.FrameworkElement.Initialized> , создаваемая вложенными элементами, которые определены в разметке, помещается в порядке самого глубокого элемента в дереве элементов, а затем родительские элементы — к корню. Этот порядок обусловлен тем, что отношения и вложения «родитель/потомок» являются свойствами, и поэтому родитель не может завершить инициализацию, пока дочерние элементы, указанные в свойстве, не будут полностью инициализированы.  
  
 При написании обработчиков в ответ на <xref:System.Windows.FrameworkElement.Initialized> событие необходимо учитывать, что не существует гарантии, что все остальные элементы в дереве элементов (логическое дерево или визуальное дерево), на которых присоединен обработчик, были созданы, особенно родительские элементы. Переменные члены могут быть null, или источники данных могут быть еще не заполненными через базовую привязку (даже на уровне выражения).  
  
### <a name="loaded"></a>Загружен  
 <xref:System.Windows.FrameworkElement.Loaded>вызывается Next. <xref:System.Windows.FrameworkElement.Loaded> Событие возникает перед завершающим рендерингом, но после того, как система макета вычислила все необходимые значения для подготовки к просмотру. <xref:System.Windows.FrameworkElement.Loaded>подразумевает, что логическое дерево, в котором содержится элемент, завершено и подключается к источнику представления, который предоставляет HWND и область отрисовки. Стандартная привязка данных (привязка к локальным источникам, таким как другие свойства или непосредственно определенные источники данных) будет выполнена до <xref:System.Windows.FrameworkElement.Loaded>. Асинхронная привязка данных (к внешним или динамическим источникам) может произойти, но по определению асинхронности не обязательно произойдет.  
  
 Механизм, с помощью которого <xref:System.Windows.FrameworkElement.Loaded> вызывается событие, отличается от <xref:System.Windows.FrameworkElement.Initialized>механизма. <xref:System.Windows.FrameworkElement.Initialized> Событие вызывается элементом по элементу без непосредственной координации завершенного дерева элементов. Напротив, <xref:System.Windows.FrameworkElement.Loaded> событие вызывается как координированное усилия во всем дереве элементов (в частности, в логическом дереве). Когда все элементы в дереве находятся в состоянии, в котором они считаются загруженными, <xref:System.Windows.FrameworkElement.Loaded> событие впервые создается в корневом элементе. Затем <xref:System.Windows.FrameworkElement.Loaded> событие создается последовательно для каждого дочернего элемента.  
  
> [!NOTE]
> Такое поведение может внешне напоминать туннелирование для перенаправленного события. Тем не менее информация не переносится от события к событию. Каждый элемент всегда имеет возможность обрабатывать свое <xref:System.Windows.FrameworkElement.Loaded> событие, и пометка данных события как обработанных не влияет на этот элемент.  
  
### <a name="unloaded"></a>Выгружен  
 <xref:System.Windows.FrameworkElement.Unloaded>вызывается последним и инициируется источником представления или удаляемым визуальным элементом. Когда <xref:System.Windows.FrameworkElement.Unloaded> вызывается и обрабатывается, элемент, который является родительским источником события (как <xref:System.Windows.FrameworkElement.Parent%2A> определено свойством) или любой заданный элемент в логических или визуальных деревьях, может быть уже удален, что означает, что привязка данных, ссылки на ресурсы , и для стилей не может быть задано значение обычного или последнего известного времени выполнения.  
  
<a name="application_model_elements"></a>   
## <a name="lifetime-events-application-model-elements"></a>Элементы модели приложений событий времени жизни  
 Создание общих событий времени существования для элементов — это следующие элементы модели приложения: <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>и <xref:System.Windows.Controls.Frame>. Они расширяют общие события времени жизни дополнительными событиями, которые связаны с их конкретными целями. Эти темы подробно рассматриваются в следующих разделах.  
  
- <xref:System.Windows.Application>: [Общие сведения об управлении приложениями](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [Общие сведения об окнах WPF](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>и :<xref:System.Windows.Controls.Frame> [Общие сведения о навигации](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>См. также

- [Приоритет значения свойства зависимостей](dependency-property-value-precedence.md)
- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
