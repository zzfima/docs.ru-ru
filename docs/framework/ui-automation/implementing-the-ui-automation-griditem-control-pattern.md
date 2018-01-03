---
title: "Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: "15"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d234ea6f15706a47f6a758528dbe4eda0f3b778a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a>Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>, включая сведения о свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 <xref:System.Windows.Automation.GridItemPattern> Используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих шаблон элемента управления <xref:System.Windows.Automation.Provider.IGridProvider>. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации <xref:System.Windows.Automation.Provider.IGridProvider>, обратите внимание на следующие правила и соглашения:  
  
-   Координаты сетки отсчитываются от нуля, начиная с верхней левой ячейки с координатами (0, 0).  
  
-   Объединенные ячейки будут передавать свои <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> и <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> основании свойств их базовой ячейки привязки в соответствии с определением поставщика автоматизации пользовательского интерфейса. Как правило, это будет самая верхняя строка и крайний левый столбец.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider>Отсутствует активная обработка сетки, таких как объединение или разбиение ячеек.  
  
-   Элементы управления, реализующие <xref:System.Windows.Automation.Provider.IGridItemProvider> обычно может выполняться (то есть клиент автоматизации пользовательского интерфейса может переходить к соседним элементам управления) с помощью клавиатуры.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>Обязательные члены для IGridItemProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|Свойство|Нет|  
  
 Этот шаблон элемента управления не имеет связанных методов или событий.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Этот шаблон элемента управления не имеет связанных исключений.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Реализация шаблона элемента управления Grid модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
