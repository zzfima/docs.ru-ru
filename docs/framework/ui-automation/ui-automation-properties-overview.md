---
title: Общие сведения о свойствах автоматизированного пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 2f96f3c7261882af58cd10038d729c4e723d6fa0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447950"
---
# <a name="ui-automation-properties-overview"></a>Общие сведения о свойствах автоматизированного пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 Поставщики автоматизации пользовательского интерфейса предоставляют свойства в элементах [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] . Эти свойства позволяют клиентским приложениям модели автоматизации пользовательского интерфейса обнаруживать сведения о частях [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], особенно элементах управления, включая статические и динамические данные.  
  
 В этом разделе приводится расширенный обзор свойств [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] . Более конкретные сведения даются в следующих разделах:  
  
- [Свойства автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md)  
  
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>   
## <a name="property-identifiers"></a>Идентификаторы свойств  
 Каждое свойство определяется номером и именем. Имена свойств используются только для отладки и диагностики. Поставщики используют числовые идентификаторы для идентификации входящих запросов свойств. Однако клиентские приложения используют для идентификации свойств, которые им требуется получить, только ссылку <xref:System.Windows.Automation.AutomationProperty>, которая включает номер и имя.  
  
 Объекты<xref:System.Windows.Automation.AutomationProperty> , представляющие конкретные свойства, доступны как поля в различных классах. По соображениям безопасности поставщики автоматизации пользовательского интерфейса получают эти объекты из отдельного набора классов, содержащихся в Uiautomationtypes.dll.  
  
 В следующей таблице перечислены свойства классов, содержащих идентификаторы <xref:System.Windows.Automation.AutomationProperty>.  
  
|Виды свойств|Клиенты получают идентификаторы из|Поставщики получают идентификаторы из|  
|-------------------------|--------------------------|----------------------------|  
|Свойства, общие для всех элементов (см. следующие таблицы)|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|Положение закрепленного окна|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|Состояние элемента, который можно разворачивать и сворачивать|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|Свойства элемента в сетке|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|Свойства сетки|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|Текущее и поддерживаемое представление элемента, который имеет несколько представлений|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|Свойства элемента, который перемещается по диапазону значений, такого как ползунок|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|Свойства прокручиваемого окна|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|Состояние и контейнер элемента, который может быть выбран, например в списке|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|Свойства элемента управления, содержащего элементы выделения|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|Заголовки столбцов и строк элемента в таблице|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|Заголовки столбцов и строк, а также ориентация таблицы|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|Состояние элемента управления "Переключатель"|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|Возможности элемента, который поддерживает перемещение, поворот или изменение размера|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|Значение и возможности чтения/записи элемента, который имеет значение|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|Возможности и состояние окна|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>   
## <a name="properties-by-category"></a>Свойства по категориям  
 В следующих таблицах указаны свойства, идентификаторы которых находятся в <xref:System.Windows.Automation.AutomationElement> и <xref:System.Windows.Automation.AutomationElementIdentifiers>. Эти свойства являются общими для всех элементов управления. Почти все из них, скорее всего, будут статическими во время существования приложения поставщика; большинство динамических свойств связано с шаблонами элементов управления.  
  
 В столбце **Доступ к свойству** перечислены другие методы доступа для каждого свойства, в дополнение к <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> и <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Дополнительные сведения о получении свойств в клиентском приложении см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
> [!NOTE]
> Чтобы получить сведения о конкретном свойстве, используйте ссылку в столбце **Доступ к свойству** .  
  
### <a name="display-characteristics"></a>Отобразить характеристики  
  
|Идентификатор свойства|Доступ к свойству|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|н/д|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a>Элемент Type  
  
|Идентификатор свойства|Доступ к свойству|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a>Идентификация  
  
|Идентификатор свойства|Доступ к свойству|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a>Взаимодействие  
  
|Идентификатор свойства|Доступ к свойству|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a>Поддержка шаблонов  
  
|Идентификатор свойства|Доступ к свойству|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a>Прочее  
  
|Идентификатор свойства|Доступ к свойству|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>   
## <a name="localization"></a>Локализация  
 Поставщики[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должны представлять следующие свойства на языке операционной системы.  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>   
## <a name="properties-and-events"></a>Свойства и события  
 Тесная связь со свойствами в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — это концепция событий изменения свойств. Для динамических свойств клиентскому приложению требуется способ узнать об изменении значения свойства, чтобы оно могло обновить свой кэш данных или отреагировать на новые сведения другим способом.  
  
 Поставщики вызывают события, когда что-нибудь в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] изменяется. Например, если флажок устанавливается или снимается, реализация поставщика шаблона Toggle вызывает событие изменения свойства. Поставщики могут вызывать события выборочно, в зависимости от наличия клиентов, прослушивающих события или прослушивающих определенные события.  
  
 Не все изменения свойств порождают события; это полностью зависит от реализации поставщика автоматизации пользовательского интерфейса для элемента. Например, поставщики стандартных прокси для списков не вызывают событие, когда изменяется <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> . В этом случае приложение должно прослушивать <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.  
  
 Клиенты прослушивают события, подписавшись на их. Подписка на события означает создание методов делегата, могущих обрабатывать эти события, и затем передачу этих методов в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] вместе с конкретными событиями, которые будут обработаны в этих методах. В частности, для событий изменения свойств клиенты должны реализовать <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.  
  
## <a name="see-also"></a>См. также:

- [Кэширование в клиентах автоматизации пользовательского интерфейса](caching-in-ui-automation-clients.md)
- [Свойства автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)
- [Нахождение элемента модели автоматизации пользовательского интерфейса в зависимости от состояния свойства](find-a-ui-automation-element-based-on-a-property-condition.md)
- [Возврат свойств от поставщика автоматизации пользовательского интерфейса](return-properties-from-a-ui-automation-provider.md)
- [Вызов событий из поставщика автоматизации пользовательского интерфейса](raise-events-from-a-ui-automation-provider.md)
