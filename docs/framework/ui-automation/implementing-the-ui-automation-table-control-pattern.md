---
title: Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: dc1ddfaa13b83d06b1d3211e9d21bd82bfeabc3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61646050"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a>Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITableProvider>, включая сведения о свойствах, методах и событиях. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TablePattern> используется для поддержки элементов управления, которые действуют как контейнеры для коллекции дочерних элементов. Дочерние элементы данного элемента должны реализовывать <xref:System.Windows.Automation.Provider.ITableItemProvider> и быть организованы в двумерной логической системе координат, к которой можно обращаться по строкам и столбцам. Этот шаблон элемента управления является аналогом <xref:System.Windows.Automation.Provider.IGridProvider>, с той разницей, что любой элемент управления, реализующий <xref:System.Windows.Automation.Provider.ITableProvider>, также должен предоставлять отношение заголовка столбца и строки для каждого дочернего элемента. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Table обратите внимание на следующие правила и соглашения.  
  
- Доступ к содержимому отдельных ячеек осуществляется через двумерную логическую систему координат или массив, предоставляемый требуемой параллельной реализацией интерфейса <xref:System.Windows.Automation.Provider.IGridProvider>.  
  
- Заголовок столбца или строки может содержаться в объекте таблицы или быть отдельным объектом заголовка, связанным с объектом таблицы.  
  
- Заголовки столбцов и строк могут включать и основной заголовок, и любые поддерживаемые заголовки.  
  
> [!NOTE]
>  Эта концепция становится понятной в электронной таблице [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)], в которой пользователь определил столбец "Имя". Теперь этот столбец имеет два заголовка: заголовок "Имя", определенный пользователем, и алфавитно-цифровое обозначение этого столбца, назначенное приложением.  
  
- См. в разделе [реализации шаблона элемента управления таблицы автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) о связанной функциональности сетки.  
  
 ![Таблица со сложными элементами верхнего колонтитула. ](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")  
Пример таблицы со сложными заголовками столбцов  
  
 ![Таблица с неоднозначным свойством RowOrColumnMajor. ](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")  
Пример таблицы с неоднозначным свойством RowOrColumnMajor.  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a>Обязательные члены для ITableProvider  
 Следующие свойства и методы обязательны для реализации интерфейса ITableProvider.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|Метод|Нет|  
  
 Этот шаблон элемента управления не имеет связанных событий.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Этот шаблон элемента управления не имеет связанных исключений.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Реализация шаблона элемента управления TableItem модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)
- [Реализация шаблона элемента управления Grid модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
