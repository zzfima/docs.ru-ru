---
title: "События модели автоматизации пользовательского интерфейса для клиентов | Microsoft Docs"
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
  - "События для клиентов автоматизации пользовательского интерфейса"
  - "события, клиенты автоматизации пользовательского интерфейса"
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
caps.latest.revision: 32
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 32
---
# События модели автоматизации пользовательского интерфейса для клиентов
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, которые хотят использовать управляемый [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] классы, определенные в <xref:System.Windows.Automation> пространства имен. Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в разделе [API автоматизации Windows: автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Описывается, как [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] события используются клиенты автоматизации пользовательского интерфейса.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]позволяет клиентам для подписки на события. Это позволяет повысить производительность, устраняя необходимость постоянного опроса всех [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы в системе на предмет изменения любые сведения, структуры или состояния.  
  
 Эффективность также повышается благодаря возможности прослушивания событий только в заданной области. Например, клиент может прослушивать события изменения фокуса для всех [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элементы в дереве или только для одного элемента и его потомков.  
  
> [!NOTE]
>  Не следует предполагать, что все возможные события вызываются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] поставщика. Например, не все изменения свойств приводят к вызову стандартными прокси-поставщиками для событий [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] элементов управления.  
  
 Дополнительные сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] события, см. [обзор событий автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Подписка на события  
 Клиентские приложения подписываются на события определенного типа, регистрируя обработчик событий с помощью одного из следующих методов.  
  
|Метод|Тип события|Тип аргументов события|Тип делегата|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Изменение фокуса|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Изменение свойства|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Изменение структуры|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Все прочие события, идентифицируемый <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> или <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Перед вызовом метода вы должны создать метод делегата для обработки события. При желании можно обрабатывать различные типы событий в одном методе и передавать этот метод в несколько вызовов одного из методов в таблице. Например, один <xref:System.Windows.Automation.AutomationEventHandler> можно настроить для обработки различных событий по-разному в <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
>  Чтобы обработать события закрытия окна, привести тип аргумента, который передается в обработчик событий, как <xref:System.Windows.Automation.WindowClosedEventArgs>. Поскольку [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] элемент для окна больше не действительна, нельзя использовать `sender` параметр для получения сведений; используйте <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> вместо.  
  
> [!CAUTION]
>  Если ваше приложение может получать события от собственного [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], следует использовать в приложении [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] потока для подписки на события или чтобы отказаться от подписки. Это может привести к непредсказуемому поведению. Дополнительные сведения см. в разделе [проблем потоков автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 При завершении работы или когда [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] события больше не представляют интерес для приложения, клиенты автоматизации пользовательского интерфейса следует вызвать один из следующих методов.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Отмена регистрации обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Отмена регистрации обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Отмена регистрации обработчика событий, который был зарегистрирован с помощью <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Отменяет регистрацию всех зарегистрированных обработчиков событий.|  
  
 Пример кода см. в разделе [подписаться на события модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>См. также  
 [Подписка на события модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)   
 [Обзор событий автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-events-overview.md)   
 [Общие сведения о свойствах модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)   
 [Пример реализации](http://msdn.microsoft.com/ru-ru/4a91c0af-6bb5-4d38-a743-cf136f268fc9)