---
title: Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса "Выделение"
ms.date: 03/30/2017
helpviewer_keywords:
- Selection control pattern
- UI Automation, Selection control pattern
- control patterns, Selection
ms.assetid: 449c3068-a5d6-4f66-84c6-1bcc7dd4d209
ms.openlocfilehash: f12ab6cc776daa4d6cca65d682cd299a0733a3a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935767"
---
# <a name="implementing-the-ui-automation-selection-control-pattern"></a>Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса "Выделение"
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ISelectionProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.SelectionPattern> используется для поддержки элементов управления, которые действуют как контейнеры для коллекции выбираемых дочерних элементов. Дочерние элементы данного элемента должны реализовывать <xref:System.Windows.Automation.Provider.ISelectionItemProvider>. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Selection обратите внимание на следующие правила и соглашения.  
  
- Элементы управления, реализующие <xref:System.Windows.Automation.Provider.ISelectionProvider> , разрешают выбирать один или несколько дочерних элементов. Например, список, представление списка и представление в виде дерева поддерживают множественный выбор, в то время как поле со списком, ползунки и группа переключателей поддерживают единичный выбор.  
  
- Элементы управления, имеющие минимальный, максимальный и непрерывный диапазон, такие как элемент управления "Ползунок" для элемента **Объем** , должны реализовывать <xref:System.Windows.Automation.Provider.IRangeValueProvider> вместо <xref:System.Windows.Automation.Provider.ISelectionProvider>.  
  
- Элементы управления, поддерживающие единичный выбор, которые управляют дочерними элементами, реализующими <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, такие как ползунок **Разрешение экрана** в диалоговом окне **Свойства экрана** или элемент управления "Выбор" для элемента **Палитра цветов** из [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (см. ниже), должны реализовывать <xref:System.Windows.Automation.Provider.ISelectionProvider>; их дочерние элементы должны реализовывать <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> и <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
 ![Палитра цветов с выделенным желтым цветом.](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Пример сопоставления строки настройки цвета  
  
- Меню не поддерживают <xref:System.Windows.Automation.SelectionPattern>. Если вы работаете с элементами меню, включающими как график, так и текст (например, элементы **области просмотра** в меню **вид** в Microsoft Outlook) и должны передать состояние, следует реализовать <xref:System.Windows.Automation.Provider.IToggleProvider>.  
  
<a name="Required_Members_for_ISelectionProvider"></a>   
## <a name="required-members-for-iselectionprovider"></a>Обязательные члены для ISelectionProvider  
 Следующие свойства, методы и события обязательны для реализации интерфейса <xref:System.Windows.Automation.Provider.ISelectionProvider> .  
  
|Обязательные члены|Тип|Примечания|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Свойство.|Должно поддерживать события изменения свойства с помощью <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> и <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Свойство.|Должно поддерживать события изменения свойства с помощью <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> и <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Метод|Отсутствуют|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|событие|Возникает, когда выделение в контейнере существенно изменилось и требуется отправить больше событий добавления и удаления, чем позволяет константа <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> .|  
  
 Свойства <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> и <xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A> могут быть динамическими. Например, начальное состояние элемента управления может не иметь элементов, выбранных по умолчанию, указывая, что <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> имеет значение `false`. Однако после выбора элемента элемент управления всегда должен иметь хотя бы один выбранный элемент. В редких случаях элемент управления также может разрешать выбор нескольких элементов при инициализации, но впоследствии разрешает выбор только одного элемента.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|Если элемент управления не включен.|  
|<xref:System.InvalidOperationException>|Если элемент управления скрыт.|  
  
## <a name="see-also"></a>См. также

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Реализация шаблона элемента управления SelectionItem модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-selectionitem-control-pattern.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
