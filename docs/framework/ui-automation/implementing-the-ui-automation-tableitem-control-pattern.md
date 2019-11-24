---
title: Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 4374666ba5e03720413614c63b00ba987f81f58f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447079"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a>Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITableItemProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TableItemPattern> используется для поддержки дочерних элементов управления контейнеров, реализующих <xref:System.Windows.Automation.Provider.ITableProvider>. Доступ к функциям отдельной ячейки обеспечивается обязательной параллельной реализацией <xref:System.Windows.Automation.Provider.IGridItemProvider>. Этот шаблон элемента управления является аналогом <xref:System.Windows.Automation.Provider.IGridItemProvider> с той разницей, что любой элемент управления, реализующий <xref:System.Windows.Automation.Provider.ITableItemProvider>, должен программными средствами предоставлять отношение между отдельной ячейкой и сведениями ее строки и столбца. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
  
- For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a>Обязательные члены для ITableItemProvider  
  
|Обязательный член|Тип члена|Примечания|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|Метод|Отсутствуют|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|Метод|Отсутствуют|  
  
 Этот шаблон элемента управления не имеет связанных свойств или событий.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Этот шаблон элемента управления не имеет связанных исключений.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Реализация шаблона элемента управления Table модели автоматизации пользовательского интерфейса](implementing-the-ui-automation-table-control-pattern.md)
- [Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса](implementing-the-ui-automation-griditem-control-pattern.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
