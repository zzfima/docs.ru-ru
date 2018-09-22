---
title: События модели автоматизации пользовательского интерфейса для клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: f295bbf44d6272879e8ea8e74c435d206b7af913
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581159"
---
# <a name="ui-automation-events-for-clients"></a>События модели автоматизации пользовательского интерфейса для клиентов
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Здесь описывается, как [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] события используются клиентами автоматизации пользовательского интерфейса.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] позволяет клиентам подписываться на интересующие события. Это позволяет повысить производительность, устраняя необходимость постоянного опроса всех [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементов в системы, чтобы узнать, изменилась ли любые сведения, структуры или состояния.  
  
 Эффективность также повышается благодаря возможности прослушивания событий только в заданной области. Например, клиент может прослушивать события изменения фокуса во всех [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элементы в дереве или только один элемент и его потомков.  
  
> [!NOTE]
>  Не следует предполагать, что все возможные события вызываются с помощью [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] поставщика. Например, не все изменения свойств приводят к вызову, поставщики стандартных прокси для событий [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] элементов управления.  
  
 Для более широком [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] события, см. в разделе [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Клиентские приложения подписываются на события определенного типа, регистрируя обработчик событий с помощью одного из следующих методов.  
  
|Метод|Тип события|Тип аргументов события|Тип делегата|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Изменение фокуса|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Изменение свойства|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Изменение структуры|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Все другие события, идентифицированные <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> или <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Перед вызовом метода вы должны создать метод делегата для обработки события. При желании можно обрабатывать различные типы событий в одном методе и передавать этот метод в несколько вызовов одного из методов в таблице. Например, один <xref:System.Windows.Automation.AutomationEventHandler> можно настроить для обработки различных событий по-разному, в <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
>  Чтобы обработать события закрытия окна, приведите тип аргумента, который передается в обработчик событий в <xref:System.Windows.Automation.WindowClosedEventArgs>. Так как [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элемент для окна больше не является допустимым, нельзя использовать `sender` параметр для получения сведений; используйте <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> вместо этого.  
  
> [!CAUTION]
>  Если ваше приложение может получать события из собственного [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], не используйте в приложении [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] потока для подписки на события или отмены подписки. Это может привести к непредсказуемому поведению. Для получения дополнительной информации см. [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 При завершении работы или когда [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] событий больше не представляют интерес для приложения, клиенты автоматизации пользовательского интерфейса должны вызвать один из следующих методов.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Отменяет регистрацию обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Отменяет регистрацию обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Отменяет регистрацию обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Отменяет регистрацию всех зарегистрированных обработчиков событий.|  
  
 Пример кода, см. в разделе [подписаться на события модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>См. также  
 [Подписка на события модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [Общие сведения о событиях модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [Общие сведения о свойствах модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [Пример реализации](https://msdn.microsoft.com/library/4a91c0af-6bb5-4d38-a743-cf136f268fc9)
