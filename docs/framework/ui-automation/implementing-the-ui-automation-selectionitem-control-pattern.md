---
title: Реализация шаблона элемента управления SelectionItem автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- Selection Item control pattern
- UI Automation, Selection Item control pattern
- control patterns, Selection Item
ms.assetid: 76b0949a-5b23-4cfc-84cc-154f713e2e12
ms.openlocfilehash: 53a5a739918e61d53b3102c2c85d4ef2b8425173
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447109"
---
# <a name="implementing-the-ui-automation-selectionitem-control-pattern"></a>Реализация шаблона элемента управления SelectionItem автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, включая сведения о свойствах, методах и событиях. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.SelectionItemPattern> используется для поддержки элементов управления, которые действуют как отдельные выбираемые дочерние элементы контейнерных элементов управления, реализующих <xref:System.Windows.Automation.Provider.ISelectionProvider>. Примеры элементов управления, реализующих шаблон элемента управления SelectionItem, см. в разделе [Управление сопоставлением шаблонов для клиентов автоматизации пользовательского интерфейса](control-pattern-mapping-for-ui-automation-clients.md) .  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления SelectionItem обратите внимание на следующие правила и соглашения.  
  
- Элементы управления, поддерживающие единичный выбор, которые управляют дочерними элементами, реализующими <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, такие как ползунок **Разрешение экрана** в диалоговом окне **Свойства экрана** , должны реализовывать <xref:System.Windows.Automation.Provider.ISelectionProvider> , а их дочерние элементы должны реализовывать <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> и <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-iselectionitemprovider"></a>Обязательные члены для ISelectionItemProvider  
 Следующие свойства, методы и события обязательны для реализации <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
|Обязательные члены|Тип элемента|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Событие|Вызывается, когда выбор в контейнере существенно изменился и требуется отправить больше событий <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> и <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> , чем позволяет константа <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> .|  
  
- Если результатом метода <xref:System.Windows.Automation.SelectionItemPattern.Select%2A>, <xref:System.Windows.Automation.SelectionItemPattern.AddToSelection%2A>или <xref:System.Windows.Automation.SelectionItemPattern.RemoveFromSelection%2A> является один выбранный элемент, должно вызываться событие <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> ; в противном случае отправьте <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>/ <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> соответствующим образом.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Когда предпринимается попытка выполнить одно из следующих действий:<br /><br /> -   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> в контейнере с поддержкой единственного выбора, где <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> = `true` , и элемент уже выбран;<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> в контейнере с поддержкой множественного выбора, где <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> = `true` , и выбран только один элемент;<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.AddToSelection%2A> в контейнере с поддержкой единственного выбора, где <xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty> = `false` , и другой элемент уже выбран.|  
  
## <a name="see-also"></a>См. также:

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Реализация шаблона элемента управления Selection модели автоматизации пользовательского интерфейса](implementing-the-ui-automation-selection-control-pattern.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
- [Пример поставщика фрагментов](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771502(v=vs.90))
