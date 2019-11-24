---
title: Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns
- UI Automation, control patterns
ms.assetid: cc229b33-234b-469b-ad60-f0254f32d45d
ms.openlocfilehash: 252e6ccf6d2980610bb8879834db5bf9e3e5dd61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448835"
---
# <a name="ui-automation-control-patterns-overview"></a>Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
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
  
 Control patterns relate to [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] as interfaces relate to Component Object Model (COM) objects. In COM, you can query an object to ask what interfaces it supports and then use those interfaces to access functionality. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]клиенты автоматизации пользовательского интерфейса могут запрашивать у элемента управления, какие шаблоны элементов управления он поддерживает, а затем взаимодействовать с этим элементом управления посредством свойств, методов, событий и структур, предоставляемых поддерживаемыми шаблонами этого элемента управления. Например, для многострочного поля ввода поставщики автоматизации пользовательского интерфейса реализуют <xref:System.Windows.Automation.Provider.IScrollProvider>. Если клиенту известно, что <xref:System.Windows.Automation.AutomationElement> поддерживает шаблон элемента управления <xref:System.Windows.Automation.ScrollPattern> , он может использовать свойства, методы и события, предоставляемые данным шаблоном элемента управления, для работы с этим элементом управления или получения доступа к сведениям о нем.  
  
<a name="uiautomation_control_pattern_client_provider"></a>   
## <a name="ui-automation-providers-and-clients"></a>Поставщики и клиенты автоматизации пользовательского интерфейса  
 Поставщики автоматизации пользовательского интерфейса реализуют шаблоны элементов управления для предоставления соответствующего расширения функциональности для определенной части функциональных возможностей, поддерживаемых элементом управления.  
  
 Клиенты автоматизации пользовательского интерфейса получают доступ к методам и свойствам классов шаблонов элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и используют их для получения сведений о [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]или для работы с [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Эти классы шаблонов элементов управления находятся в пространстве имен <xref:System.Windows.Automation> (например, в <xref:System.Windows.Automation.InvokePattern> или в <xref:System.Windows.Automation.SelectionPattern>).  
  
 Clients use <xref:System.Windows.Automation.AutomationElement> methods (such as <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> or <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType>) or the common language runtime (CLR) accessors to access the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties on a pattern. Each control pattern class has a field member (for example, <xref:System.Windows.Automation.InvokePattern.Pattern?displayProperty=nameWithType> or <xref:System.Windows.Automation.SelectionPattern.Pattern?displayProperty=nameWithType>) that identifies that control pattern and can be passed as a parameter to <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> to retrieve that pattern for an <xref:System.Windows.Automation.AutomationElement>.  
  
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
|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.Provider.IGridProvider>|Используется для элементов управления, которые поддерживают функциональные возможности сетки, такие как изменение размера и перемещение в указанную ячейку. For example, the large icon view in Windows Explorer or simple tables without headers in Microsoft Word.|  
|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Используется для элементов управления, имеющих ячейки в сетках. Отдельные ячейки должны поддерживать шаблон GridItem. For example, each cell in Microsoft Windows Explorer detail view.|  
|<xref:System.Windows.Automation.InvokePattern>|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Используется для элементов управления, которые могут быть вызваны, таких как кнопки.|  
|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.Provider.IMultipleViewProvider>|Используется для элементов управления, которые могут переключаться между несколькими представлениями одного и того же набора сведений, данных или дочерних элементов. Например, это может быть элемент управления представления списка, где данные доступны в виде эскизов, плиток, значков, списка или подробных представлений.|  
|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Используется для элементов управления, имеющих диапазон значений, которые могут быть применены к элементу управления. Например, элемент управления "Счетчик", содержащий годы, может иметь диапазон от 1900 до 2010, а другой элемент управления "Счетчик", представляющий месяцы, имеет диапазон от 1 до 12.|  
|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.Provider.IScrollProvider>|Используется для элементов управления, которые поддерживают прокрутку. Например, это может быть элемент управления, имеющий полосы прокрутки, которые активны, когда сведений больше, чем может быть отображено в видимой области элемента управления.|  
|<xref:System.Windows.Automation.ScrollItemPattern>|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Используется для элементов управления, имеющих отдельные элементы в прокручиваемом списке. Например, это может быть элемент управления с отдельными элементами в прокручиваемом списке, такой как элемент управления "Поле со списком".|  
|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Используется для элементов управления контейнера выделения. Например, это могут быть списки и поля со списком.|  
|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Используется для отдельных элементов в элементах управления контейнера выделения, таких как списки и поля со списком.|  
|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.Provider.ITableProvider>|Используется для элементов управления, имеющих сетку и сведения заголовка. For example, Microsoft Excel worksheets.|  
|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Используется для элементов в таблице.|  
|<xref:System.Windows.Automation.TextPattern>|<xref:System.Windows.Automation.Provider.ITextProvider>|Используется для элементов управления "Поле ввода" и документов, которые предоставляют текстовую информацию.|  
|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.Provider.IToggleProvider>|Используется для элементов управления, в которых можно переключать состояние. Например, это могут быть флажки и элементы меню с флажками.|  
|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.Provider.ITransformProvider>|Используется для элементов управления с возможностью изменения размера, перемещения и вращения. Обычно шаблон элемента управления Transform используется в конструкторах, формах, графических редакторах и графических приложениях.|  
|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.Provider.IValueProvider>|Позволяет клиентам получать или задавать значения для элементов управления, которые не поддерживают диапазон значений. Например, это может быть элемент управления "Выбор даты и времени".|  
|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.Provider.IWindowProvider>|Exposes information specific to windows, a fundamental concept to the Microsoft Windows operating system. Examples of controls that are windows are top-level application windows (Microsoft Word, Microsoft Windows Explorer, and so on), multiple-document interface (MDI) child windows, and dialogs.|  
  
## <a name="see-also"></a>См. также

- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Сопоставление шаблона элемента управления для клиентов автоматизации пользовательского интерфейса](control-pattern-mapping-for-ui-automation-clients.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
- [Свойства автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md)
- [События модели автоматизации пользовательского интерфейса для клиентов](ui-automation-events-for-clients.md)
