---
title: "UI Automation Events Overview | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, providers"
  - "UI Automation, events"
  - "clients, UI Automation"
  - "events, UI Automation"
  - "providers, UI Automation"
  - "UI Automation, clients"
ms.assetid: 69eebd8b-39ed-40e7-93cc-4457c4caf746
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# UI Automation Events Overview
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Уведомление о событии [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] — это ключевая функция для вспомогательных технологий, таких как средства чтения с экрана и экранные лупы. Эти клиенты автоматизации пользовательского интерфейса отслеживают события, вызываемые поставщиками автоматизации пользовательского интерфейса, когда что\-то происходит в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], и используют эти сведения, чтобы уведомить конечных пользователей.  
  
 Повысить эффективность можно, позволяя приложениям поставщика вызывать события выборочно в зависимости от того, было ли все клиенты подписаны на эти события или прослушивают ли клиенты события.  
  
<a name="Types_of_Events"></a>   
## Типы событий  
 События [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] делятся на следующие категории.  
  
|Событие|Описание|  
|-------------|--------------|  
|Изменение свойства|Возникает, когда свойство элемента [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] или шаблона элемента управления изменяется. Например, если клиент должен отслеживать элемент управления "Флажок" приложения, он может зарегистрироваться для прослушивания события изменения свойства <xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A>. Когда флажок устанавливается или снимается, поставщик вызывает событие и клиент может выполнить необходимые действия.|  
|Действие элемента|Возникает при изменении результатов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] конечным пользователем или программой, например при нажатии кнопки или ее вызове с помощью <xref:System.Windows.Automation.InvokePattern>.|  
|Изменение структуры|Вызывается, если структура дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] изменяется. Структура изменяется, когда новые элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] становятся видимыми, скрытыми или удаляются с рабочего стола.|  
|Глобальное изменение рабочего стола|Вызывается, когда выполняются глобальные действия для клиента, например когда фокус переходит от одного элемента к другому или при закрытии окна.|  
  
 Некоторые события необязательно означают, что состояние пользовательского интерфейса изменилось. Например, если пользователь переходит к полю ввода текста и затем нажимает кнопку для обновления поля, возникает событие `TextChangedEvent`, даже если пользователь фактически не изменил текст. При обработке события клиентскому приложению может потребоваться проверить, действительно ли что\-либо изменилось, перед выполнением действия.  
  
 Следующие события могут возникать, даже если состояние пользовательского интерфейса не изменилось.  
  
-   `AutomationPropertyChangedEvent` \(в зависимости от измененного свойства\)  
  
-   `ElementSelectedEvent`  
  
-   `InvalidatedEvent`  
  
-   `TextChangedEvent`  
  
<a name="UI_Automation_Event_Identifiers"></a>   
## Идентификаторы событий автоматизации пользовательского интерфейса  
 События [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] идентифицируются объектами <xref:System.Windows.Automation.AutomationEvent>. Свойство <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> содержит значение, которое однозначно определяет тип события.  
  
 Возможные значения параметра <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> приведены в следующей таблице вместе с типом, используемым для аргументов событий. Обратите внимание, что идентификаторы, используемые клиентами и поставщиками, идентичны именованным полям из различных классов.  
  
|Идентификатор клиента|Идентификатор поставщика|Тип аргументов события|  
|---------------------------|------------------------------|----------------------------|  
|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|  
|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionPattern.InvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.InvokePattern.InvokedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.LayoutInvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPattern.TextChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPattern.TextSelectionChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipClosedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipOpenedEvent?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationPropertyChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.StructureChangedEventArgs>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent?displayProperty=fullName>|<xref:System.Windows.Automation.WindowClosedEventArgs>|  
  
<a name="UI_Automation_Event_Arguments"></a>   
## Аргументы событий автоматизации пользовательского интерфейса  
 Следующие классы инкапсулируют аргументы событий.  
  
|Класс|Описание|  
|-----------|--------------|  
|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|Содержит сведения об асинхронной загрузке содержимого, включая процент завершения загрузки.|  
|<xref:System.Windows.Automation.AutomationEventArgs>|Содержит сведения о простом событии, не требующем дополнительных данных.|  
|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|Содержит сведения об изменении фокуса ввода с одного элемента на другой. События этого типа вызываются системой [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], а не поставщиками.|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|Содержит сведения об изменении значения свойства элемента или шаблона элемента управления.|  
|<xref:System.Windows.Automation.StructureChangedEventArgs>|Содержит сведения об изменении дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|<xref:System.Windows.Automation.WindowClosedEventArgs>|Содержит сведения о закрытии окна.|  
  
 Все классы аргументов событий содержат элемент <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>. Этот идентификатор инкапсулируется в <xref:System.Windows.Automation.AutomationEvent>.  
  
 Объекты <xref:System.Windows.Automation.AutomationEvent>, используемые для идентификации событий, извлекаются поставщиками из полей в <xref:System.Windows.Automation.AutomationElementIdentifiers> и классов идентификатора шаблона элементов управления, таких как <xref:System.Windows.Automation.DockPatternIdentifiers>. Эквивалентные поля извлекаются клиентскими приложениями из полей в <xref:System.Windows.Automation.AutomationElement> и классов шаблонов элементов управления, таких как <xref:System.Windows.Automation.DockPattern>.  
  
 Список идентификаторов событий см. в разделе [UI Automation Events for Clients](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md).  
  
## См. также  
 [UI Automation Events for Clients](../../../docs/framework/ui-automation/ui-automation-events-for-clients.md)   
 [Server\-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)   
 [Subscribe to UI Automation Events](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)