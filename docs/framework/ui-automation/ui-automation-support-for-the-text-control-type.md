---
title: Поддержка автоматизированного пользовательского интерфейса для текстовых элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- Text control type
- UI Automation, Text control type
- control types, Text
ms.assetid: ab0d0ada-8a71-4547-9c03-aadf675938f2
ms.openlocfilehash: 857606bd0b759bd1283b5abcb3f70914a48014a7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785847"
---
# <a name="ui-automation-support-for-the-text-control-type"></a>Поддержка автоматизированного пользовательского интерфейса для текстовых элементов управления
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления Text. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 Элементы управления "Текст" являются основными элементами пользовательского интерфейса, представляющими фрагменты текста на экране.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления Text. Требования к [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "текст", будь то [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 или Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления "Текст", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление контента|  
|------------------|------------------|  
|Текст|Text (если содержимое)|  
  
 Элемент управления "Текст" может использоваться один в качестве метки или статического текста в форме. Он также может содержаться в структуре следующих типов элементов управления:  
  
- ListItem  
  
- TreeItem  
  
- DataItem  
  
 Элементы управления "Текст" могут отсутствовать в представлении содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , поскольку текст часто отображается с помощью `NameProperty` другого элемента управления. Например текст, который используется в качестве метки элемента управления "Поле со списком", предоставляется с помощью значения `NameProperty` элемента управления. Поскольку элемент управления "Поле со списком" находится в представлении содержимого дерева модели автоматизации пользовательского интерфейса, здесь необязательно должен присутствовать элемент управления "Текст". Элементы управления "Текст" никогда не имеют дочерних элементов в представлении содержимого.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Текст". Дополнительные сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] свойствах см. в разделе [Свойства модели автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|{2&gt;Value&lt;2}|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Поддерживается при наличии ограничивающего прямоугольника. Если не все точки внутри ограничивающего прямоугольника являются интерактивными и выполняется специализированная проверка на наличие данных, выполните переопределение и предоставьте интерактивную точку.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Элемент управления "Панель текста" всегда является текстом, который он отображает.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Элементы управления "Текст" не имеют меток со статическим текстом.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Текст|Это значение одинаково для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"текст"|Локализованная строка, соответствующая типу элемента управления Text.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Зависит от обстоятельств|Элемент управления "Текст" будет содержимым, если он содержит сведения, которые не представлены в NameProperty другого элемента управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Да|Элемент управления "Текст" всегда должен быть элементом управления.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться элементами управления "Текст". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Никогда.|Текст никогда не поддерживает ValuePattern. Если текст редактируемый, то он является типом элемента управления Edit.|  
|<xref:System.Windows.Automation.Provider.ITextProvider>|Зависит от обстоятельств|Для улучшения специальных возможностей элемент управления "Текст" может поддерживать шаблон элемента управления Text, хотя это не обязательно. Шаблон элемента управления Text целесообразно использовать, если текст имеет множество стилей и атрибутов (например, цвет, полужирным шрифт и курсив). Зависит от инфраструктуры.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Зависит от обстоятельств|Если текстовый элемент содержится в элементе управления "Таблица", это должно поддерживаться.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Зависит от обстоятельств|Если текстовый элемент содержится в элементе управления "Таблица", это должно поддерживаться.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Текст". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|Обязательное|Нет|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>|Никогда.|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное|Нет|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Automation.ControlType.Text>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
