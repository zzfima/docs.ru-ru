---
title: События модели автоматизации пользовательского интерфейса для клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
ms.openlocfilehash: 6d4525aeea458e1ec810efa659f373a2b5f21f57
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741306"
---
# <a name="ui-automation-events-for-clients"></a>События модели автоматизации пользовательского интерфейса для клиентов
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе описывается, как события [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] используются клиентами автоматизации пользовательского интерфейса.  
  
 В модели [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] клиенты могут подписываться на интересующие события. Это позволяет повысить производительность, устраняя необходимость постоянного опроса всех элементов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] в системе на предмет изменения каких-либо сведений, структуры или состояния.  
  
 Эффективность также повышается благодаря возможности прослушивания событий только в заданной области. Например, клиент может прослушивать события изменения фокуса во всех элементах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] в дереве или только в одном элементе и его потомках.  
  
> [!NOTE]
> Не следует думать, что все возможные события вызываются поставщиком [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]. Например, не все изменения свойств приводят к возникновению событий стандартными поставщиками прокси для [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] и элементов управления Win32.  
  
 Более широкое представление [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] событий см. в разделе [Общие сведения о событиях модели автоматизации пользовательского интерфейса](ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Клиентские приложения подписываются на события определенного типа, регистрируя обработчик событий с помощью одного из следующих методов.  
  
|Метод|Тип события|Тип аргументов события|Тип делегата|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Изменение фокуса|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Изменение свойства|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Изменение структуры|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Все прочие события, идентифицированные <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> или <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Перед вызовом метода вы должны создать метод делегата для обработки события. При желании можно обрабатывать различные типы событий в одном методе и передавать этот метод в несколько вызовов одного из методов в таблице. Например, один <xref:System.Windows.Automation.AutomationEventHandler> можно настроить для обработки различных событий по-разному, в зависимости от <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
> Чтобы обработать события закрытия окна, приведите тип аргумента, передаваемого в обработчик событий, к типу <xref:System.Windows.Automation.WindowClosedEventArgs>. Поскольку элемент [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для окна больше не является допустимым, нельзя использовать параметр `sender` для получения сведений; используйте вместо него метод <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A>.  
  
> [!CAUTION]
> Если ваше приложение может получать события из собственного [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], не используйте поток [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] вашего приложения для подписки на события или отмены подписки. Это может привести к непредсказуемому поведению. Для получения дополнительной информации см. [UI Automation Threading Issues](ui-automation-threading-issues.md).  
  
 При завершении работы или когда события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] больше не представляют интерес для приложения, клиенты автоматизации пользовательского интерфейса должны вызвать один из следующих методов.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Отменяет регистрацию обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Отменяет регистрацию обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Отменяет регистрацию обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Отменяет регистрацию всех зарегистрированных обработчиков событий.|  
  
 Пример кода см. [в разделе Подписка на события модели автоматизации пользовательского интерфейса](subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>См. также:

- [Подписка на события модели автоматизации пользовательского интерфейса](subscribe-to-ui-automation-events.md)
- [Общие сведения о событиях модели автоматизации пользовательского интерфейса](ui-automation-events-overview.md)
- [Общие сведения о свойствах модели автоматизации пользовательского интерфейса](ui-automation-properties-overview.md)
- [Пример Траккфокус](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FocusTracker)
