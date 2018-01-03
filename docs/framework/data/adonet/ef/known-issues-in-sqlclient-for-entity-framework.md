---
title: "Известные проблемы SqlClient для Entity Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f9b3a6140271749b9e0f1518aea736609ad438db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a>Известные проблемы SqlClient для Entity Framework
В данном разделе описаны известные проблемы, связанные с поставщиком данных .NET Framework для SQL Server (SqlClient).  
  
## <a name="trailing-spaces-in-string-functions"></a>Конечные пробелы в строковых функциях  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] пропускает конечные пробелы в строковых значениях. Таким образом, передача конечных пробелов в строку может привести к непредсказуемым результатам и даже сбоям.  
  
 Если в строке имеются конечные пробелы, рекомендуется добавить в конец пробельный символ так, чтобы [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] не усекал строку. Если конечные пробелы не требуются, их следует усекать до их последующей передачи по конвейеру запросов.  
  
## <a name="right-function"></a>RIGHT, функция  
 Если в `null`, 0`RIGHT(nvarchar(max)` или `)`, 0`RIGHT(varchar(max)` в качестве первого аргумента передается значение, отличное от `)`, а в качестве второго аргумента передается значение, равное 0, то вместо строки `NULL` будет возвращено значение типа `empty`.  
  
## <a name="cross-and-outer-apply-operators"></a>Операторы CROSS APPLY и OUTER APPLY  
 Операторы CROSS и OUTER APPLY появились в версии [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)]. В некоторых случаях конвейер запросов может сформировать инструкцию Transact-SQL, содержащую операторы CROSS APPLY и OUTER APPLY. Так как некоторые внутренние поставщики, включая версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], которые предшествовали [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], не поддерживают данные операторы, эти запросы нельзя выполнить на данных поставщиках.  
  
 Далее показаны некоторые стандартные сценарии, которые могут привести к появлению операторов CROSS APPLY и OUTER APPLY в выходном запросе.  
  
-   Связанный вложенный запрос с разбиением на страницы.  
  
-   `AnyElement` над коррелированным вложенным запросом или коллекцией, сформированной навигацией.  
  
-   LINQ-запросы, использующие методы группирования, принимающие элемент selector.  
  
-   Запрос, в котором явно указан оператор CROSS APPLY или OUTER APPLY.  
  
-   Запрос, имеющий конструкцию DEREF над конструкцией REF.  
  
## <a name="skip-operator"></a>Оператор SKIP  
 Если вы используете [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)], использование предложения SKIP вместе с ORDER BY для неключевых столбцов может возвращать неверные результаты. Если неключевой столбец содержит повторяющиеся данные, то может быть пропущено больше указанного числа строк. Причина этого заключается в способе преобразования предложения SKIP для выполнения в [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]. Например, в следующем запросе более пяти строк может быть пропущено Если `E.NonKeyColumn` содержит повторяющиеся значения:  
  
```  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a>Нацеливание на правильную версию SQL Server  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Цели [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] запрос, основанный на версии SQL Server, которая указана в `ProviderManifestToken` атрибута элемента схемы в файле хранилища модели (с расширением SSDL). Данная версия может отличаться от фактической версии SQL Server, с которой в данный момент осуществлено соединение. Например, если используется SQL Server 2005, а для атрибута `ProviderManifestToken` установлено значение 2008, сформированный запрос [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] может не выполниться на сервере. Например, запрос, который использует новые типы даты и времени, представленные в SQL Server 2008, не будет выполняться в предыдущих версиях SQL Server. Если вы используете SQL Server 2005, а `ProviderManifestToken` атрибута установлено значение 2000, сформированный [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] запрос может быть менее оптимизирован, или может возникнуть исключение, сообщающее, что запрос не поддерживается. Дополнительные сведения см. в разделе «Операторы CROSS и OUTER APPLY», приведенном выше в данной теме.  
  
 Некоторые варианты поведения базы данных зависят от уровня совместимости, установленного на базе данных. Если для атрибута `ProviderManifestToken` установлено значение 2005 и используется SQL Server версии SQL Server, а для уровня совместимости базы данных установлено значение «80» (SQL Server 2000), сформированный запрос [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] будет нацелен на SQL Server 2005, но может не выполниться, как ожидается, вследствие установки уровня совместимости. Например, если имя столбца в списке ORDER BY совпадает с именем столбца в селекторе, то можно потерять данные об упорядочивании.  
  
## <a name="nested-queries-in-projection"></a>Вложенные запросы в проекции  
 Вложенные запросы в предложении проекции могут быть переведены в запросы декартовых произведений на сервере. На некоторых внутренних серверах, включая SLQ Server это может вызвать таблицы TempDB получить достаточно большим. Это может снизить производительность сервера.  
  
 Далее приведен пример вложенного запроса в предложении проекции:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a>Формируемые сервером значения идентификаторов GUID  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поддерживает формируемые сервером значения идентификаторов GUID, однако поставщик должен поддерживать возвращение формируемых сервером значений идентификаторов после вставки строк. Начиная с [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2005, может возвращать формируемый сервером тип идентификатора GUID в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] базы данных через [предложение OUTPUT](http://go.microsoft.com/fwlink/?LinkId=169400) .  
  
## <a name="see-also"></a>См. также  
 [SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)  
 [Рекомендации и известные проблемы в LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)
