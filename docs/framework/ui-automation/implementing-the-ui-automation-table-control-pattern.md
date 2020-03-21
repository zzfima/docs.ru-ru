---
title: Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 0b3d000112060550734890ad3c4063a26c320b04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180117"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a>Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITableProvider>, включая сведения о свойствах, методах и событиях. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TablePattern> используется для поддержки элементов управления, которые действуют как контейнеры для коллекции дочерних элементов. Дочерние элементы данного элемента должны реализовывать <xref:System.Windows.Automation.Provider.ITableItemProvider> и быть организованы в двумерной логической системе координат, к которой можно обращаться по строкам и столбцам. Этот шаблон элемента управления является аналогом <xref:System.Windows.Automation.Provider.IGridProvider>, с той разницей, что любой элемент управления, реализующий <xref:System.Windows.Automation.Provider.ITableProvider>, также должен предоставлять отношение заголовка столбца и строки для каждого дочернего элемента. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Table обратите внимание на следующие правила и соглашения.  
  
- Доступ к содержимому отдельных ячеек осуществляется через двумерную логическую систему координат или массив, предоставляемый требуемой параллельной реализацией интерфейса <xref:System.Windows.Automation.Provider.IGridProvider>.  
  
- Заголовок столбца или строки может содержаться в объекте таблицы или быть отдельным объектом заголовка, связанным с объектом таблицы.  
  
- Заголовки столбцов и строк могут включать и основной заголовок, и любые поддерживаемые заголовки.  
  
> [!NOTE]
> Эта концепция становится очевидной в таблице Microsoft Excel, где пользователь определил столбец "Первое имя". Теперь этот столбец имеет два заголовка: заголовок "Имя", определенный пользователем, и алфавитно-цифровое обозначение этого столбца, назначенное приложением.  
  
- [Ознакомьтесь с реализацией шаблона управления сеткой автоматизации uI](implementing-the-ui-automation-grid-control-pattern.md) для связанных с ней функциональности сетки.  
  
 ![Таблица с двумя сложными элементами верхнего колонтитула.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")  
Пример таблицы со сложными заголовками столбцов  
  
 ![Таблица с неоднозначным свойством RowOrColumnMajor.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")  
Пример таблицы с неоднозначным свойством RowOrColumnMajor.  
  
<a name="Required_Members_for_ITableProvider"></a>
## <a name="required-members-for-itableprovider"></a>Обязательные члены для ITableProvider  
 Следующие свойства и методы обязательны для реализации интерфейса ITableProvider.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|Метод|None|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|Метод|None|  
  
 Этот шаблон элемента управления не имеет связанных событий.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Исключения  
 Этот шаблон элемента управления не имеет связанных исключений.  
  
## <a name="see-also"></a>См. также раздел

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса](implementing-the-ui-automation-tableitem-control-pattern.md)
- [Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса](implementing-the-ui-automation-grid-control-pattern.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
