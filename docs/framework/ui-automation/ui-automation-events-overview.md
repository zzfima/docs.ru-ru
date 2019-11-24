---
title: Обзор событий автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- UI Automation, events
- clients, UI Automation
- events, UI Automation
- providers, UI Automation
- UI Automation, clients
ms.assetid: 69eebd8b-39ed-40e7-93cc-4457c4caf746
ms.openlocfilehash: 5f9362814eb671a6d7a111cadb96be6d06f5cb3d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441490"
---
# <a name="ui-automation-events-overview"></a>Обзор событий автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 Уведомление о событии[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] — это ключевая функция для вспомогательных технологий, таких как средства чтения с экрана и экранные лупы. Эти клиенты автоматизации пользовательского интерфейса отслеживают события, вызываемые поставщиками автоматизации пользовательского интерфейса, когда что-то происходит в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , и используют эти сведения, чтобы уведомить конечных пользователей.  
  
 Повысить эффективность можно, позволяя приложениям поставщика вызывать события выборочно в зависимости от того, было ли все клиенты подписаны на эти события или прослушивают ли клиенты события.  
  
<a name="Types_of_Events"></a>   
## <a name="types-of-events"></a>Типы событий  
 События[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] делятся на следующие категории.  
  
|событие|Описание|  
|-----------|-----------------|  
|Изменение свойства|Возникает, когда свойство элемента [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] или шаблона элемента управления изменяется. Например, если клиент должен отслеживать элемент управления "Флажок" приложения, он может зарегистрироваться для прослушивания события изменения свойства <xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> . Когда флажок устанавливается или снимается, поставщик вызывает событие и клиент может выполнить необходимые действия.|  
|Действие элемента|Возникает при изменении результатов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] конечным пользователем или программой, например при нажатии кнопки или ее вызове с помощью <xref:System.Windows.Automation.InvokePattern>.|  
|Изменение структуры|Вызывается, если структура дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] изменяется. Структура изменяется, когда новые элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] становятся видимыми, скрытыми или удаляются с рабочего стола.|  
|Глобальное изменение рабочего стола|Вызывается, когда выполняются глобальные действия для клиента, например когда фокус переходит от одного элемента к другому или при закрытии окна.|  
  
 Некоторые события необязательно означают, что состояние пользовательского интерфейса изменилось. Например, если пользователь переходит к полю ввода текста и затем нажимает кнопку для обновления поля, возникает событие `TextChangedEvent` , даже если пользователь фактически не изменил текст. При обработке события клиентскому приложению может потребоваться проверить, действительно ли что-либо изменилось, перед выполнением действия.  
  
 Следующие события могут возникать, даже если состояние пользовательского интерфейса не изменилось.  
  
- `AutomationPropertyChangedEvent` (в зависимости от измененного свойства)  
  
- `ElementSelectedEvent`  
  
- `InvalidatedEvent`  
  
- `TextChangedEvent`  
  
<a name="UI_Automation_Event_Identifiers"></a>   
## <a name="ui-automation-event-identifiers"></a>Идентификаторы событий автоматизации пользовательского интерфейса  
 События[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] идентифицируются объектами <xref:System.Windows.Automation.AutomationEvent> . Свойство <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> содержит значение, которое однозначно определяет тип события.  
  
 Возможные значения параметра <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> приведены в следующей таблице вместе с типом, используемым для аргументов событий. Обратите внимание, что идентификаторы, используемые клиентами и поставщиками, идентичны именованным полям из различных классов.  
  
|Идентификатор клиента|Идентификатор поставщика|Тип аргументов события|  
|-----------------------|-------------------------|--------------------------|  
|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|  
|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionPattern.InvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.InvokePattern.InvokedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.LayoutInvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPattern.TextChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPattern.TextSelectionChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationPropertyChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.StructureChangedEventArgs>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.WindowClosedEventArgs>|  
  
<a name="UI_Automation_Event_Arguments"></a>   
## <a name="ui-automation-event-arguments"></a>Аргументы событий автоматизации пользовательского интерфейса  
 Следующие классы инкапсулируют аргументы событий.  
  
|Class|Описание|  
|-----------|-----------------|  
|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|Содержит сведения об асинхронной загрузке содержимого, включая процент завершения загрузки.|  
|<xref:System.Windows.Automation.AutomationEventArgs>|Содержит сведения о простом событии, не требующем дополнительных данных.|  
|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|Содержит сведения об изменении фокуса ввода с одного элемента на другой. События этого типа вызываются системой [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , а не поставщиками.|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|Содержит сведения об изменении значения свойства элемента или шаблона элемента управления.|  
|<xref:System.Windows.Automation.StructureChangedEventArgs>|Содержит сведения об изменении дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.WindowClosedEventArgs>|Содержит сведения о закрытии окна.|  
  
 Все классы аргументов событий содержат элемент <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A> . Этот идентификатор инкапсулируется в <xref:System.Windows.Automation.AutomationEvent>.  
  
 Объекты <xref:System.Windows.Automation.AutomationEvent> , используемые для идентификации событий, извлекаются поставщиками из полей в <xref:System.Windows.Automation.AutomationElementIdentifiers> и классов идентификатора шаблона элементов управления, таких как <xref:System.Windows.Automation.DockPatternIdentifiers>. Эквивалентные поля извлекаются клиентскими приложениями из полей в <xref:System.Windows.Automation.AutomationElement> и классов шаблонов элементов управления, таких как <xref:System.Windows.Automation.DockPattern>.  
  
 Список идентификаторов событий см. в разделе [UI Automation Events for Clients](ui-automation-events-for-clients.md).  
  
## <a name="see-also"></a>См. также

- [События модели автоматизации пользовательского интерфейса для клиентов](ui-automation-events-for-clients.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)
- [Подписка на события модели автоматизации пользовательского интерфейса](subscribe-to-ui-automation-events.md)
