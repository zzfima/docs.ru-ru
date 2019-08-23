---
title: Поддержка автоматизированного пользовательского интерфейса для типа элемента управления Document
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Document
- Document control type
- UI Automation, Document control type
ms.assetid: a79d594b-1ca0-4543-8dac-afd2c645201d
ms.openlocfilehash: 5e33a50db9359667efe38fafdb6386a50cb0694a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911915"
---
# <a name="ui-automation-support-for-the-document-control-type"></a>Поддержка автоматизированного пользовательского интерфейса для типа элемента управления Document
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления Document. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Эти условия включают определенные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 С помощью элементов управления "Документ" пользователи могут просматривать несколько страниц текста и управлять ими. В отличие от элементов управления "Поле ввода", которые поддерживают только простую строку неформатированного текста, элементы управления "Документ" могут содержать текст со сложным стилем и форматированием.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления Document. Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "Документ", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления "Документ", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|------------------|------------------|  
|Document<br /><br /> — Изменяется|Document<br /><br /> — Изменяется|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Документ". Дополнительные сведения о свойствах см. в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] разделе [Свойства модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Значение|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Документ имеет активную точку, при щелчке которой фокус перемещается в один из его элементов в контейнере документа.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Document|Это значение является одинаковым для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Элемент управления "Документ" всегда включается в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элемент управления "Документ" всегда включается в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|См. примечания.|Значение этого свойства должно быть меткой элемента управления "Документ". Как правило, используется заголовок документа.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"документ"|Локализованная строка, соответствующая типу элемента управления Document.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Элемент управления "Документ" обычно получает свои имена из имени файла, из которого загружается документ. Оно часто отображается в заголовке, содержащем окна или рамки.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться элементами управления "Документ". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Зависит от обстоятельств|Элемент управления "Документ" может занимать, превышающую область просмотра. Если содержимое может прокручиваться, этот элемент управления должен поддерживать шаблон элемента управления Scroll.|  
|<xref:System.Windows.Automation.Provider.ITextProvider>|Обязательно|Элемент управления "Документ" может занимать, превышающую область просмотра. Если содержимое может прокручиваться, этот элемент управления должен поддерживать шаблон элемента управления Scroll.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Никогда|Элемент управления "Документ" не поддерживает этот шаблон элемента управления, поскольку содержимое элемента управления часто занимает несколько страниц. Клиенты автоматизации пользовательского интерфейса должны использовать <xref:System.Windows.Automation.TextPattern> для получения текстовых сведений о документе.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Документ". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательный|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательно|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty>|Обязательно|Отсутствуют|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Зависит от обстоятельств|Если элемент управления поддерживает шаблон Selection, то он должен поддерживать данное событие.|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|Обязательно|Отсутствуют|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|Обязательно|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>|Никогда|Отсутствуют|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType.Document>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-overview.md)
