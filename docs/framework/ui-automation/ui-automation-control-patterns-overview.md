---
title: Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns
- UI Automation, control patterns
ms.assetid: cc229b33-234b-469b-ad60-f0254f32d45d
ms.openlocfilehash: a3daf75417260d7e761da2e90c595471b2a4b2a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131515"
---
# <a name="ui-automation-control-patterns-overview"></a>Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом обзоре представлены шаблоны элементов управления [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] . Шаблоны элементов управления позволяют классифицировать и предоставлять функции элемента управления независимо от типа или внешнего вида элемента управления.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] использует шаблоны элементов управления для представления общих расширений функциональности элементов управления. Например, вы используете шаблон элемента управления Invoke для элементов управления, которые могут быть вызваны (таких как кнопки), а шаблон элемента управления Scroll — для элементов управления, имеющих полосы прокрутки (таких как списки или поля со списком). Поскольку каждый шаблон элемента управления предоставляет отдельную функциональность, их можно объединять для описания полного набора функциональных возможностей, поддерживаемых определенным элементом управления.  
  
> [!NOTE]
> Агрегатные элементы управления, построенные с помощью дочерних элементов управления, которые обеспечивают [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] для функциональности, предоставляемой родительским классом, должны реализовывать все шаблоны элементов управления, обычно связанные с каждым дочерним элементом управления. В свою очередь те же шаблоны элементов управления не обязательно должны быть реализованы дочерними элементами управления.  
  
<a name="uiautomation_control_pattern_includes"></a>   
## <a name="ui-automation-control-pattern-components"></a>Компоненты шаблонов элементов управления модели автоматизации пользовательского интерфейса  
 Шаблоны элементов управления поддерживают методы, свойства, события и связи, необходимые для определения дискретной части функциональности, доступной в элементе управления.  
  
- Связь между элементом модели автоматизации пользовательского интерфейса и его родительским, дочерними и одноуровневыми элементами описывает структуру элемента в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
- Методы позволяют клиентам автоматизации пользовательского интерфейса работать с элементом управления.  
  
- Свойства и события предоставляют сведения о функциональности шаблона элемента управления, а также сведения о состоянии элемента управления.  
  
 Шаблоны элементов управления связаны с [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] в виде интерфейсов, связанных с COM-объектами. В модели COM можно запросить объект, чтобы узнать, какие интерфейсы он поддерживает, а затем использовать эти интерфейсы для доступа к функциональным возможностям. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]клиенты автоматизации пользовательского интерфейса могут запрашивать у элемента управления, какие шаблоны элементов управления он поддерживает, а затем взаимодействовать с этим элементом управления посредством свойств, методов, событий и структур, предоставляемых поддерживаемыми шаблонами этого элемента управления. Например, для многострочного поля ввода поставщики автоматизации пользовательского интерфейса реализуют <xref:System.Windows.Automation.Provider.IScrollProvider>. Если клиенту известно, что <xref:System.Windows.Automation.AutomationElement> поддерживает шаблон элемента управления <xref:System.Windows.Automation.ScrollPattern> , он может использовать свойства, методы и события, предоставляемые данным шаблоном элемента управления, для работы с этим элементом управления или получения доступа к сведениям о нем.  
  
<a name="uiautomation_control_pattern_client_provider"></a>   
## <a name="ui-automation-providers-and-clients"></a>Поставщики и клиенты автоматизации пользовательского интерфейса  
 Поставщики автоматизации пользовательского интерфейса реализуют шаблоны элементов управления для предоставления соответствующего расширения функциональности для определенной части функциональных возможностей, поддерживаемых элементом управления.  
  
 Клиенты автоматизации пользовательского интерфейса получают доступ к методам и свойствам классов шаблонов элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и используют их для получения сведений о [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]или для работы с [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Эти классы шаблонов элементов управления находятся в пространстве имен <xref:System.Windows.Automation> (например, в <xref:System.Windows.Automation.InvokePattern> или в <xref:System.Windows.Automation.SelectionPattern>).  
  
 Клиенты используют <xref:System.Windows.Automation.AutomationElement> методов (например, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> или <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType>) или методы доступа среды CLR для доступа к свойствам [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] в шаблоне. Каждый класс шаблона элемента управления имеет элемент Field (например, <xref:System.Windows.Automation.InvokePattern.Pattern?displayProperty=nameWithType> или <xref:System.Windows.Automation.SelectionPattern.Pattern?displayProperty=nameWithType>), который определяет шаблон элемента управления и может быть передан в качестве параметра для <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> или <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> для получения этого шаблона для <xref:System.Windows.Automation.AutomationElement>.  
  
<a name="uiautomation_control_patterns_dynamic"></a>   
## <a name="dynamic-control-patterns"></a>Динамические шаблоны элементов управления  
 Некоторые элементы управления не всегда поддерживают один и тот же набор шаблонов элементов управления. Шаблоны элементов управления считаются поддерживаемыми, если они доступны для клиента автоматизации пользовательского интерфейса. Например, многострочное поле ввода включает вертикальную прокрутку, только если оно содержит больше строк текста, чем может быть отображено в его видимой области. Прокрутка отключается при удалении достаточного объема текста, когда она становится ненужной. Например, шаблон элемента управления ScrollPattern динамически поддерживается в зависимости от текущего состояния элемента управления (какой объем текста находится в поле ввода).  
  
<a name="Control_Pattern_Classes_and_Interfaces"></a>   
## <a name="control-pattern-classes-and-interfaces"></a>Классы шаблонов элементов управления и интерфейсы  
 В следующей таблице описываются шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . В этой таблице также приведены классы, используемые клиентами автоматизации пользовательского интерфейса для доступа к шаблонам элементов управления, а также интерфейсы, используемые поставщиками автоматизации пользовательского интерфейса для их реализации.  
  
|Класс шаблона элемента управления|Интерфейс поставщика|Описание|  
|---------------------------|------------------------|-----------------|  
|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.Provider.IDockProvider>|Используется для элементов управления, которые могут быть закреплены в контейнере закрепления. Например, это могут быть панели инструментов или палитры инструментов.|  
|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Используется для элементов управления, которые можно разворачивать и сворачивать. Например, это могут быть пункты меню в приложении, такие как меню **Файл** .|  
|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.Provider.IGridProvider>|Используется для элементов управления, которые поддерживают функциональные возможности сетки, такие как изменение размера и перемещение в указанную ячейку. Например, это могут быть простые таблицы без заголовков в [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)]или представление с крупными значками в проводнике.|  
|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Используется для элементов управления, имеющих ячейки в сетках. Отдельные ячейки должны поддерживать шаблон GridItem. Например, каждая ячейка в подробном представлении проводника Microsoft Windows.|  
|<xref:System.Windows.Automation.InvokePattern>|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Используется для элементов управления, которые могут быть вызваны, таких как кнопки.|  
|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.Provider.IMultipleViewProvider>|Используется для элементов управления, которые могут переключаться между несколькими представлениями одного и того же набора сведений, данных или дочерних элементов. Например, это может быть элемент управления представления списка, где данные доступны в виде эскизов, плиток, значков, списка или подробных представлений.|  
|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Используется для элементов управления, имеющих диапазон значений, которые могут быть применены к элементу управления. Например, элемент управления "Счетчик", содержащий годы, может иметь диапазон от 1900 до 2010, а другой элемент управления "Счетчик", представляющий месяцы, имеет диапазон от 1 до 12.|  
|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.Provider.IScrollProvider>|Используется для элементов управления, которые поддерживают прокрутку. Например, это может быть элемент управления, имеющий полосы прокрутки, которые активны, когда сведений больше, чем может быть отображено в видимой области элемента управления.|  
|<xref:System.Windows.Automation.ScrollItemPattern>|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Используется для элементов управления, имеющих отдельные элементы в прокручиваемом списке. Например, это может быть элемент управления с отдельными элементами в прокручиваемом списке, такой как элемент управления "Поле со списком".|  
|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Используется для элементов управления контейнера выделения. Например, это могут быть списки и поля со списком.|  
|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Используется для отдельных элементов в элементах управления контейнера выделения, таких как списки и поля со списком.|  
|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.Provider.ITableProvider>|Используется для элементов управления, имеющих сетку и сведения заголовка. Например, это могут быть листы [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] .|  
|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Используется для элементов в таблице.|  
|<xref:System.Windows.Automation.TextPattern>|<xref:System.Windows.Automation.Provider.ITextProvider>|Используется для элементов управления "Поле ввода" и документов, которые предоставляют текстовую информацию.|  
|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.Provider.IToggleProvider>|Используется для элементов управления, в которых можно переключать состояние. Например, это могут быть флажки и элементы меню с флажками.|  
|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.Provider.ITransformProvider>|Используется для элементов управления с возможностью изменения размера, перемещения и вращения. Обычно шаблон элемента управления Transform используется в конструкторах, формах, графических редакторах и графических приложениях.|  
|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.Provider.IValueProvider>|Позволяет клиентам получать или задавать значения для элементов управления, которые не поддерживают диапазон значений. Например, это может быть элемент управления "Выбор даты и времени".|  
|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.Provider.IWindowProvider>|Предоставляет сведения, относящиеся к Windows, фундаментальную концепцию операционной системы Microsoft Windows. Примерами элементов управления, являющихся окнами, являются окна приложений верхнего уровня ([!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)], проводник Microsoft Windows и т. д.), дочерние окна многодокументного интерфейса (MDI) и диалоговые окна.|  
  
## <a name="see-also"></a>См. также

- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Сопоставление шаблона элемента управления для клиентов автоматизации пользовательского интерфейса](control-pattern-mapping-for-ui-automation-clients.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
- [Свойства автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md)
- [События модели автоматизации пользовательского интерфейса для клиентов](ui-automation-events-for-clients.md)
