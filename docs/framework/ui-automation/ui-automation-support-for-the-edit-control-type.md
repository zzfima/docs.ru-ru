---
title: Поддержка автоматизации пользовательского интерфейса для типа элемента управления "Поле вода"
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Edit
- Edit control type
- UI Automation, Edit control type
ms.assetid: 6db9d231-c0a0-4e17-910e-ac80357f774f
ms.openlocfilehash: 500dc450ad171ed50316c8e08d62258d745049cb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448457"
---
# <a name="ui-automation-support-for-the-edit-control-type"></a>Поддержка автоматизации пользовательского интерфейса для типа элемента управления "Поле вода"

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).

В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления Edit. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Эти условия включают определенные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.

С помощью элементов управления "Поле ввода" пользователи могут просматривать и изменять простую строку текста без широкой поддержки форматирования.

В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления Edit. Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "Поле ввода", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса

В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которое относится к элементам управления "Поле ввода" и описывает, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).

|Представление элемента управления|Представление содержимого|
|------------------|------------------|
|Правка|Правка|

Элементы управления, которые реализуют тип элемента управления Edit, всегда имеют нулевые полосы прокрутки в представлении элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , так как это однострочный элемент управления. В некоторых макетах одна строка текста может переноситься. Тип элемента управления Edit лучше всего подходит для хранения небольших объемов редактируемого или выбираемого текста.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса

В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Поле ввода". Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).

|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|значения|Примечания|
|------------------------------------------------------------------------------------|-----------|-----------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Элемент управления "Поле ввода должен иметь активную точку, которая предоставляет фокус ввода в часть редактирования элемента управления, когда пользователь щелкает ее мышью.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Имя элемента управления "Поле ввода" обычно создается из статического текста метки. Если статическая текстовая метка не предусмотрена, разработчик приложения должен предоставить значение для свойства `Name` . Значение свойства `Name` никогда не должно быть текстовым содержимым элемента управления "Поле ввода".|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|См. примечания.|Если статическая текстовая метка связана с элементом управления, то данное свойство должно предоставлять ссылку на этот элемент управления. Если элемент управления "Текст" является подкомпонентом другого элемента управления, он не будет иметь набор свойств `LabeledBy` .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Правка|Это значение является одинаковым для всех инфраструктур [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"поле ввода"|Локализованная строка, соответствующая типу элемента управления Edit.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Элемент управления "Поле ввода" всегда включается в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элемент управления "Поле ввода" всегда включается в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsPasswordProperty>|См. примечания.|Должно быть задано значение true во всех элементах управления "Поле ввода", содержащих пароли. Если элемент управления "Поле ввода" содержит пароль, то это свойство может использоваться средством чтения с экрана для определения, должны ли считываться нажатия клавиш по мере нажатия их пользователем.|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns-and-properties"></a>Необходимые шаблоны и свойства элементов управления модели автоматизации пользовательского интерфейса

В следующей таблице перечислены шаблоны элементов управления, которые должны поддерживаться всеми элементами управления "Поле ввода". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).

|Шаблон элемента управления/свойство шаблона элемента управления|Поддержка/значение|Примечания|
|-----------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.Provider.ITextProvider>|Зависит от обстоятельств|Элементы управления "Поле ввода" должны поддерживать шаблон элемента управления Text, поскольку клиентам всегда должна быть доступна подробная текстовая информация.|
|<xref:System.Windows.Automation.Provider.IValueProvider>|Зависит от обстоятельств|Все элементы управления "Поле ввода", которые принимают строку, должны предоставлять шаблон Value.|
|<xref:System.Windows.Automation.Provider.IValueProvider.IsReadOnly%2A>|См. примечания.|Это свойство должно быть установлено, чтобы указать, может ли элемент управления иметь значение, заданное программными средствами, его может изменять пользователь.|
|<xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>|См. примечания.|Это свойство будет возвращать текстовое содержимое элемента управления "Поле ввода". Если `IsPasswordProperty` имеет значение `true`, это свойство должно создавать `InvalidOperationException` по запросу.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Зависит от обстоятельств|Все элементы управления "Поле ввода", принимающие числовой диапазон, должны предоставлять шаблон элемента управления Range Value.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Minimum%2A>|См. примечания.|Это свойство должно быть наименьшим значением, которое может быть присвоено содержимому элемента управления "Поле ввода".|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Maximum%2A>|См. примечания.|Это свойство должно быть наибольшим значением, которое может быть присвоено содержимому элемента управления "Поле ввода".|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.SmallChange%2A>|См. примечания.|Это свойство должно указывать количество десятичных разрядов, которое может быть в значении. Если поле ввода принимает только целые значения, `SmallChangeProperty` должно иметь значение 1. Если поле ввода принимает значения в диапазоне от 1.0 до 2.0, то `SmallChangeProperty` должно иметь значение 0.1. Если поле ввода принимает значения в диапазоне от 1.00 до 2.00, то `SmallChangeProperty` должно иметь значение 0.001.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.LargeChange%2A>|`Null`|Это свойство не обязательно предоставлять в элементе управления "Поле ввода".|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Value%2A>|См. примечания.|Это свойство будет указывать числовое содержимое элемента управления "Поле ввода". Если клиент [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] задает более точное значение в диапазоне, указанном в свойствах `Minimum` и `Maximum` , то свойство Value будет автоматически округляться до ближайшего приемлемого значения.|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса

В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Поле ввода". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).

|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|
|---------------------------------------------------------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Обязательное значение|Отсутствуют|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|Обязательное значение|Отсутствуют|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|Обязательное значение|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное значение|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное значение|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное значение|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Обязательное значение|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>|Зависит от обстоятельств|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>|Никогда|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty>|Никогда|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty>|Никогда|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty>|Никогда|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty>|Никогда|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty>|Никогда|Отсутствуют|
|Событие изменения свойства<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty>|Зависит от обстоятельств|Если элемент управления поддерживает шаблон элемента управления Range Value, то он должен поддерживать данное событие.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное значение|Отсутствуют|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное значение|Отсутствуют|

## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType.Edit>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
