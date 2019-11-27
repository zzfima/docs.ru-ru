---
title: Реализация шаблона элемента управления ExpandCollapse модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, ExpandCollapse control pattern
- ExpandCollapse control pattern
- control patterns, ExpandCollapse
ms.assetid: 1dbabb8c-0d68-47c1-a35e-1c01cb01af26
ms.openlocfilehash: 073ff0727fc6aab1189f73a254aa95da60820cc3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447146"
---
# <a name="implementing-the-ui-automation-expandcollapse-control-pattern"></a>Реализация шаблона элемента управления ExpandCollapse модели автоматизации пользовательского интерфейса

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).

В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, включая сведения о свойствах, методах и событиях. Ссылки на дополнительные материалы перечислены в конце раздела.

Шаблон элемента управления <xref:System.Windows.Automation.ExpandCollapsePattern> используется для поддержки элементов управления, которые визуально разворачиваются для отображения дополнительного содержимого и сворачиваются для скрытия содержимого. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).

<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации

При реализации шаблона элемента управления ExpandCollapse обратите внимание на следующие правила и соглашения.

- Агрегатные элементы управления, построенные с помощью дочерних объектов, предоставляющих функциональность развертывания и свертывания, должны поддерживать шаблон элемента управления <xref:System.Windows.Automation.ExpandCollapsePattern> , а их дочерние элементы — нет. Например, элемент управления «Поле со списком строится с помощью комбинации элементов управления «Список», «Кнопка» и «Поле ввода», но только родительский элемент управления «Поле со списком» должен поддерживать <xref:System.Windows.Automation.ExpandCollapsePattern>.

  > [!NOTE]
  > Исключением является элемент управления «Меню», который является совокупностью отдельных объектов MenuItem. Объекты MenuItem могут поддерживать шаблон элемента управления <xref:System.Windows.Automation.ExpandCollapsePattern> , но родительский элемент управления «Меню» — нет. Аналогичное исключение применяется к элементам управления «Дерево» и «Элемент дерева».

- Когда <xref:System.Windows.Automation.ExpandCollapseState> элемента управления имеет значение <xref:System.Windows.Automation.ExpandCollapseState.LeafNode>, в это время для него неактивны все функциональные возможности <xref:System.Windows.Automation.ExpandCollapsePattern> и с помощью этого шаблона элемента управления можно получить только сведения <xref:System.Windows.Automation.ExpandCollapseState>. Если впоследствии добавляются какие-либо дочерние объекты, <xref:System.Windows.Automation.ExpandCollapseState> изменяется и функциональность <xref:System.Windows.Automation.ExpandCollapsePattern> активируется.

- <xref:System.Windows.Automation.ExpandCollapseState> относится только к видимости непосредственных дочерних объектов; этот параметр не относится к видимости всех дочерних объектов.

- Функциональность развертывания и свертывания определяется элементом управления. Ниже представлены примеры такого поведения.

  - Личное меню Office может быть тремя состояниями MenuItem (<xref:System.Windows.Automation.ExpandCollapseState.Expanded>, <xref:System.Windows.Automation.ExpandCollapseState.Collapsed> и <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>), где элемент управления задает принимаемое состояние, когда вызывается метод <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> или <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> .

  - Вызов метода <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> в TreeItem может отображать все потомки или только непосредственные дочерние элементы.

  - Если вызов <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> или <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> в элементе управления поддерживает состояние его потомков, должно отправляться событие изменения видимости, а не событие изменения состояния. Если родительский элемент управления не поддерживает состояние своих потомков при сворачивании, то этот элемент управления может уничтожить всех потомков, которые больше не отображаются, и вызвать событие уничтожения; или же он может изменить <xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A> для каждого потомка и вызвать событие изменения видимости.

- Для обеспечения возможности навигации желательно, чтобы объект был в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (с указанием соответствующего состояния видимости) независимо от <xref:System.Windows.Automation.ExpandCollapseState>его родительских объектов. Если потомки создаются по запросу, они могут появляться только в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] после первого отображения или только когда они видимы.

<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-iexpandcollapseprovider"></a>Обязательные члены для IExpandCollapseProvider

Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.

|Обязательные члены|Тип элемента|Примечания|
|----------------------|-----------------|-----------|
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A>|Свойство|Нет|
|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A>|Метод|Нет|
|<xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>|Метод|Нет|
|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|Событие|Этот элемент управления не имеет связанных событий; используйте этот универсальный делегат.|

<a name="Exceptions"></a>

## <a name="exceptions"></a>Исключения

Поставщики должны вызывать следующие исключения.

|Тип исключения|Условие|
|--------------------|---------------|
|<xref:System.InvalidOperationException>|Вызывается <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> или <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> , когда <xref:System.Windows.Automation.ExpandCollapseState> = <xref:System.Windows.Automation.ExpandCollapseState.LeafNode>.|

## <a name="see-also"></a>См. также:

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Навигация между элементами модели автоматизации пользовательского интерфейса с помощью TreeWalker](navigate-among-ui-automation-elements-with-treewalker.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
