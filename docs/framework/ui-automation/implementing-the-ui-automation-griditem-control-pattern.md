---
title: Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: d561587e6bb98ba857b27ba89b4c1a45ba964ffd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180189"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a>Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>, включая сведения о свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.GridItemPattern> используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.IGridProvider>. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации <xref:System.Windows.Automation.Provider.IGridProvider> обратите внимание на следующие правила и соглашения.  
  
- Координаты сетки отсчитываются от нуля, начиная с верхней левой ячейки с координатами (0, 0).  
  
- Объединенные ячейки будут передавать свои свойства <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> и <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> на основе свойств их базовой ячейки привязки в соответствии с определением в поставщике автоматизации пользовательского интерфейса. Как правило, это будет самая верхняя строка и крайний левый столбец.  
  
- <xref:System.Windows.Automation.Provider.IGridItemProvider> не предусматривает активные манипуляции с сеткой, такие как объединение или разбиение ячеек.  
  
- Элементы управления, реализующие <xref:System.Windows.Automation.Provider.IGridItemProvider>, обычно могут быть пройдены (то есть клиент автоматизации пользовательского интерфейса может переходить в соседние элементы управления) с помощью клавиатуры.  
  
<a name="Required_Members_for_IGridItemProvider"></a>
## <a name="required-members-for-igriditemprovider"></a>Обязательные члены для IGridItemProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|Свойство|None|  
  
 Этот шаблон элемента управления не имеет связанных методов или событий.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Исключения  
 Этот шаблон элемента управления не имеет связанных исключений.  
  
## <a name="see-also"></a>См. также раздел

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса](implementing-the-ui-automation-grid-control-pattern.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
