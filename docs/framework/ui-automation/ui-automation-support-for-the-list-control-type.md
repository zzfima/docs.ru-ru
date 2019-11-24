---
title: Поддержка модели автоматизации пользовательского интерфейса для элемента управления "Список"
ms.date: 03/30/2017
helpviewer_keywords:
- control types, List
- List control type
- UI Automation, List control type
ms.assetid: 0e959fcb-50f2-413b-948d-7167d279bc11
ms.openlocfilehash: c5ea011651537aa5836eeebe217239234fec40ae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446732"
---
# <a name="ui-automation-support-for-the-list-control-type"></a>Поддержка модели автоматизации пользовательского интерфейса для элемента управления "Список"
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления List. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 Тип элемента управления List обеспечивает способ организации плоской группы или групп элементов и предоставляет пользователю возможность выбрать один или несколько этих элементов. Тип элемента управления List не имеет ограничений на типы дочерних элементов, которые он может содержать. Это позволяет поставщикам автоматизации пользовательского интерфейса поддерживать знакомые элементы для контейнеров выбора.  
  
 Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , приведенные в следующих разделах, относятся ко всем элементам управления, реализующим тип элемента управления List, будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]. Контейнерные элементы управления "Список" являются примерами элементов управления, которые реализуют тип элемента управления List.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице приводятся два представления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые относятся к элементам управления "Список", и описывается, что может содержаться в каждом представлении. Представление элемента управления содержит только элементы, которые являются элементами управления, и представление содержимого удаляет избыточные сведения из дерева. Например, элемент управления "Текст", используемый для метки поля со списком, будет представляться как `ComboBox NameProperty`. Поскольку элемент управления "Текст" уже предоставлен таким образом через представление элемента управления, не нужно предоставлять его дважды; следовательно, он удаляется из представления содержимого. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|------------------|------------------|  
|Содержит элементы, соответствующие элементам управления.|Удаляет избыточные сведения из дерева, чтобы специальные возможности имели дело с наименьшим набором значимой информации для конечного пользователя.|  
|Списка<br /><br /> -   DataItem (0 or more)<br />-   ListItem (0 or more)<br />-   Group (0 or more)<br />-   ScrollBar (0, 1 or 2)|Списка<br /><br /> -   DataItem (0 or more)<br />-   ListItem (0 or more)<br />-   Group (0 or more)|  
  
 Представление для элемента управления, который реализует тип List (например, элемент управления "Список"), включает следующие элементы:  
  
- Zero or more items within the list control (items can be based on the List Item or Data Item control types).
  
- Zero or more group controls within a list control.
  
- Zero, one, or two scroll bar controls.
  
Представление содержимого элемента управления, который реализует тип List (например, элемент управления "Список"), включает следующие элементы:  
  
- Zero or more items within the list control (items can be based on the List Item or Data Item control types).
  
- Zero or more groups within the list control.

Элемент управления "Список" не должен содержать элементы, которые имеют какую-либо иерархическую связь кроме общей группы. Если элементы в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] имеют дочерние элементы, то контейнер списка должен быть построен на типе элемента управления Tree.  
  
 Выбираемые элементы в элементе управления "Список" будут доступны из потомков в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента управления "Список". Все элементы в элементе управления "Список" должны принадлежать одной группе выбора. Выбираемые элементы в списке должны предоставляться как типы элемента управления ListItem (вместо DataItem).  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Список". For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|значения|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Если элемент управления "Список" имеет активную точку (точка, которую можно щелкнуть, чтобы перенести фокус в этот список), то такая точка должна предоставляться через это свойство.<br /><br /> If the value of the `IsOffScreen` property is true, then the <xref:System.Windows.Automation.NoClickablePointException> will be raised.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Значение свойства Name элемента управления "Список" должно передавать категорию параметров, выбор из которой запрашивается у пользователя. Обычно это свойство получает имя из статической текстовой метки. Если статическая текстовая метка не предусмотрена, разработчик приложения должен предоставить значение для свойства Name.<br /><br /> Единственный случай, когда данное свойство не является обязательным для элементов управления "Список", — если этот элемент управления используется в поддереве другого элемента управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|См. примечания.|Если имеется статическая текстовая метка, то данное свойство должно предоставлять ссылку на этот элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Списка|Это значение является одинаковым для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"список"|Локализованная строка, соответствующая типу элемента управления List.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Элемент управления "Список" всегда включается в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элемент управления "Список" всегда включается в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Если контейнер может принимать ввод с клавиатуры, это свойство должно иметь значение true.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|См. примечания.|Текст справки для элементов управления "Список" должен объяснять, почему пользователю предлагается сделать выбор из списка параметров. Например, "Выбор элемента из этого списка установит разрешение экрана для монитора".|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns-and-properties"></a>Необходимые шаблоны и свойства элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться элементами управления "Список". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления/свойство шаблона|Поддержка/значение|Примечания|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Обязательное значение|Все элементы управления, поддерживаемые типом элемента управления List, должны реализовывать `ISelectionProvider` , когда состояние выбора поддерживается между элементами, содержащимися в элементе управления. Если элементы в контейнере не могут быть выбраны, должен использоваться тип элемента управления Group.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Зависит от обстоятельств|Элементы управления "Список" не всегда требуют, чтобы элемент был выбран.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Зависит от обстоятельств|Элементы управления "Список" могут быть контейнерами, разрешающими выбор одного или нескольких элементов.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Зависит от обстоятельств|Реализуйте этот шаблон элемента управления, если элементы в контейнере являются прокручиваемыми.|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|Зависит от обстоятельств|Реализуйте этот шаблон, если для отдельных элементов должна быть доступна навигация по сетке.|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider>|Зависит от обстоятельств|Реализуйте этот шаблон элемента управления, если элемент управления может поддерживать несколько представлений элементов в контейнере.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|Никогда|`ITableProvider` никогда не поддерживается для типа элемента управления List. Если элемент управления должен поддерживать этот шаблон элемента управления, то он должен быть построен на типе элемента управления Data Grid.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Список". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка/значение|Примечания|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Зависит от обстоятельств|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Зависит от обстоятельств|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty>|Зависит от обстоятельств|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>|Зависит от обстоятельств|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty>|Зависит от обстоятельств|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty>|Зависит от обстоятельств|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty>|Зависит от обстоятельств|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty>|Зависит от обстоятельств|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty>|Зависит от обстоятельств|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное значение|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное значение|Отсутствуют|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType.List>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
