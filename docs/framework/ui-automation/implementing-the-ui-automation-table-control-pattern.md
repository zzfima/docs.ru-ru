---
title: "Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса | Microsoft Docs"
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
  - "Шаблона элемента управления таблицы автоматизации пользовательского интерфейса"
  - "шаблоны элементов управления, таблицы"
  - "TableControl - шаблон"
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 18
---
# Реализация шаблона элемента управления таблицы автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, которые хотят использовать управляемый [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] классы, определенные в <xref:System.Windows.Automation> пространства имен. Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в разделе [API автоматизации Windows: автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе рассматриваются рекомендации и правила для реализации <xref:System.Windows.Automation.Provider.ITableProvider>, включая сведения о свойствах, методы и события. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 <xref:System.Windows.Automation.TablePattern> шаблон элемента управления используется для поддержки элементов управления, которые действуют как контейнеры для коллекции дочерних элементов. Дочерние элементы данного элемента должны реализовать <xref:System.Windows.Automation.Provider.ITableItemProvider> и быть организованы в двумерную логическую систему координат, к которой можно обращаться по строкам и столбцам. Этот шаблон элемента управления является аналогом <xref:System.Windows.Automation.Provider.IgridProvider>, с той разницей, что любой элемент управления, реализующий <xref:System.Windows.Automation.Provider.ITableProvider> также должен предоставлять отношение заголовка столбца и строки для каждого дочернего элемента. Примеры элементов управления, реализующие данный шаблон элемента управления в разделе [управления шаблон сопоставления для клиентов автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Table обратите внимание на следующие правила и соглашения.  
  
-   Доступ к содержимому отдельных ячеек осуществляется через двумерную логическую систему координат или массив, предоставляемый требуемой параллельной реализацией интерфейса <xref:System.Windows.Automation.Provider.IGridProvider>.  
  
-   Заголовок столбца или строки может содержаться в объекте таблицы или быть отдельным объектом заголовка, связанным с объектом таблицы.  
  
-   Заголовки столбцов и строк могут включать и основной заголовок, и любые поддерживаемые заголовки.  
  
> [!NOTE]
>  Эта концепция становится понятной в [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] таблицы, в которой пользователь определил столбец «First name». Теперь этот столбец имеет два заголовка: заголовок "Имя", определенный пользователем, и алфавитно-цифровое обозначение этого столбца, назначенное приложением.  
  
-   В разделе [реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) для функциональных возможностях связанной сетки.  
  
 ![Таблица со сложными элементами верхнего колонтитула.](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.png "UIA_TablePattern_Complex_Column_Headers")  
Пример таблицы со сложными заголовками столбцов  
  
 ![Таблица с неоднозначным свойством roworcolumnmajor.](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.png "UIA_TablePattern_RowOrColumnMajorProperty")  
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
 [Общие сведения о шаблонах элементов управления автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [Шаблоны модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Реализация шаблона элемента управления TableItem автоматизированного пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)   
 [Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)   
 [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)