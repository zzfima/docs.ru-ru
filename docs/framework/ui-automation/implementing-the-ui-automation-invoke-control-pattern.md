---
title: Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса Invoke
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Invoke control pattern
- control patterns, Invoke
- Invoke control pattern
ms.assetid: e5b1e239-49f8-468e-bfec-1fba02ec9ac4
ms.openlocfilehash: 30ae83aa4b73f36afce1251387598ef9b61816d8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435158"
---
# <a name="implementing-the-ui-automation-invoke-control-pattern"></a>Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса Invoke

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).

В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IInvokeProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.

Шаблон элемента управления <xref:System.Windows.Automation.InvokePattern> используется для поддержки элементов управления, которые не сохраняют состояние при активации, а инициируют или выполняют одно однозначное действие. Элементы управления, сохраняющие свое состояние, такие как флажки и переключатели, вместо этого должны реализовывать <xref:System.Windows.Automation.Provider.IToggleProvider> и <xref:System.Windows.Automation.Provider.ISelectionItemProvider> соответственно. Примеры элементов управления, реализующих шаблон элемента управления Invoke, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).

<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации

При реализации шаблона элемента управления Invoke обратите внимание на следующие правила и соглашения.

- Элементы управления реализуют <xref:System.Windows.Automation.Provider.IInvokeProvider> , если то же самое поведение не доступно через другого поставщика шаблона элемента управления. Например, если метод <xref:System.Windows.Automation.InvokePattern.Invoke%2A> в элементе управления выполняет те же действия, что и метод <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> или <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> этот элемент управления не должен реализовывать <xref:System.Windows.Automation.Provider.IInvokeProvider>.

- Обычно для вызова элемента управления нужно щелкнуть, дважды щелкнуть, нажать клавишу ВВОД, нажать стандартное сочетание клавиш или нажать некоторое другую другое сочетание клавиш.

- <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> вызывается в элементе управления, который был активирован (в ответ на выполнение элементом управления связанного действия). Если это возможно, событие должно вызываться после завершения действия элементом управления и его возврата без блокировки. Событие Invoked должно вызываться перед обслуживанием запроса Invoke в следующих случаях:

  - невозможно или нецелесообразно ожидать завершения действия;

  - действие требует взаимодействия с пользователем;

  - действие занимает много времени и приведет к блокировке вызывающего клиента на значительное время.

- Если вызов элемента управления имеет существенные побочные эффекты, эти эффекты должны предоставляться через свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> . Например, несмотря на то что метод <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> не связан с выделением, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> может привести к выделению другого элемента управления.

- Эффекты наведения указателя обычно не представляют собой событие Invoked. Однако элементы управления, выполняющие действие (в отличие от вызывающих визуальный эффект) на основе состояния наведения, должны поддерживать шаблон элемента управления <xref:System.Windows.Automation.InvokePattern> .

> [!NOTE]
> Эта реализация считается проблемой специальных возможностей, если элемент управления может быть вызван только в результате побочного эффекта, связанного с мышью.

- Вызов элемента управления отличается от выбора элемента. Тем не менее в зависимости от элемента управления его вызов может привести к выбору элемента в качестве побочного эффекта. Например, при вызове элемента списка документов Microsoft Word в папке «Мои документы» выбирается элемент и открывается документ.

- Элемент может исчезнуть из дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] сразу после вызова. В результате запрос информации из элемента, предоставленного обратным вызовом события, может завершиться неудачно. В качестве обходного решения рекомендуется выполнять предварительное кэширование информации.

- Элементы управления могут реализовывать множество шаблонов элементов управления. Например, элемент управления цвет заливки на панели инструментов Microsoft Excel реализует как <xref:System.Windows.Automation.InvokePattern>, так и шаблоны элементов управления <xref:System.Windows.Automation.ExpandCollapsePattern>. <xref:System.Windows.Automation.ExpandCollapsePattern> предоставляет меню, а <xref:System.Windows.Automation.InvokePattern> заполняет активный выделенный фрагмент выбранным цветом.

<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-iinvokeprovider"></a>Обязательные члены для IInvokeProvider

Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IInvokeProvider>.

|Обязательные члены|Тип члена|Примечания|
|----------------------|-----------------|-----------|
|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>|метод|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> является асинхронным вызовом и должен возвращаться немедленно без блокировки.<br /><br /> Это особенно важно для элементов управления, которые при вызове прямо или косвенно запускают модальное диалоговое окно. Любой клиент автоматизации пользовательского интерфейса, инициировавший это событие, будет оставаться заблокированным до закрытия модального диалогового окна.|

<a name="Exceptions"></a>

## <a name="exceptions"></a>Исключения

Поставщики должны вызывать следующие исключения.

|Тип исключения|Условие|
|--------------------|---------------|
|<xref:System.Windows.Automation.ElementNotEnabledException>|Если элемент управления не включен.|

## <a name="see-also"></a>См. также

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса](invoke-a-control-using-ui-automation.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
