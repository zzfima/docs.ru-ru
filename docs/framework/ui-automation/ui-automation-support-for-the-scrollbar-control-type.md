---
title: Поддержка автоматизации пользовательского интерфейса для типа элемента управления ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll Bar control type
- control types, Scroll Bar
- Scroll Bar control type
ms.assetid: 329891d7-b609-49e6-920a-09ea8a627d07
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5c2f1ae77585576c8ad1c83b37e6ec530dd31598
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43778910"
---
# <a name="ui-automation-support-for-the-scrollbar-control-type"></a>Поддержка автоматизации пользовательского интерфейса для типа элемента управления ScrollBar
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержатся сведения о поддержке в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления ScrollBar. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 С помощью элементов управления "Полоса прокрутки" пользователи могут прокручивать содержимое внутри окна или контейнера элементов. Элемент управления состоит из набора кнопок и бегунка.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления ScrollBar. Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "Список", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления "Полоса прокрутки", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|------------------|------------------|  
|ScrollBar<br /><br /> -Кнопка (2 или 4)<br />-Thumb (0 или1)|Неприменимо. В элементе управления "Полоса прокрутки" отсутствует содержимое.|  
  
 Элемент управления "Полоса прокрутки" всегда имеет от трех до пяти дочерних элементов. Поскольку поддерево имеет несколько элементов управления "Кнопка", вы должны установить определенное значение <xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty> для каждого элемента, чтобы их могли обнаружить средства автоматизации тестирования.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Полоса прокрутки". Обратите внимание, что элемент управления "Полоса прокрутки" никогда не имеет содержимое; его функциональность предоставляется через шаблон элемента управления Scroll, который поддерживается в контейнере с возможностью прокрутки.  
  
 Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Значение|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|`Null`|Элемент управления "Полоса прокрутки" не имеет элементов содержимого, и свойство `NameProperty` устанавливать не требуется.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Не является числом.|Элемент управления "Полоса прокрутки" не имеет активных точек.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Полосы прокрутки не имеют меток.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ScrollBar|Это значение одинаково для всех инфраструктур. Полосы прокрутки, функционирующие как ползунки, должны использовать тип элемента управления Slider.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"полоса прокрутки"|Локализованная строка, соответствующая типу элемента управления Button.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|False|Элемент управления "Полоса прокрутки" никогда не является элементом содержимого. Если полоса прокрутки является автономным элементом управления, то она должна воплощать тип элемента управления Slider и возвращать `ControlType.Slider` для свойства `ControlType` .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Да|Полоса прокрутки всегда должна быть элементом управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.OrientationProperty>|Да|Элемент управления "Полоса прокрутки" всегда должен представлять горизонтальную или вертикальную ориентацию.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Полоса прокрутки". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md). Обратите внимание, что если полоса прокрутки используется как элемент управления только для работы с мышью, она не поддерживает шаблоны элементов управления. Если она используется как элемент управления "Ползунок" в приложении, ей необходимо предоставить тип элемента управления Slider.  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Никогда|Шаблон элемента управления Scroll никогда не поддерживается в полосе прокрутки напрямую.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Зависит от обстоятельств|Эта функциональность должна поддерживаться только в том случае, если шаблон элемента управления Scroll не поддерживается в контейнере, который содержит полосу прокрутки.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Полоса прокрутки". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Поддержка/значение|Примечания|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> |Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> |Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> |Обязательно|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> |Никогда|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> |Никогда|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> |Никогда|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> |Никогда|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> |Никогда|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> |Никогда|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> |Зависит от обстоятельств|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательно|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательно|Нет|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Automation.ControlType.ScrollBar>  
 [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [Общие сведения о модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-overview.md)
