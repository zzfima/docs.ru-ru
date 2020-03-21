---
title: Рекомендации по LINQ (службы WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
ms.openlocfilehash: 6c0cd7dcebb46b5408079848862ef4da1bb7f0a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174671"
---
# <a name="linq-considerations-wcf-data-services"></a>Рекомендации по LINQ (службы WCF Data Services)
В этой теме содержится информация о том, каким образом составляются и выполняются запросы LIN's при использовании клиента WCF Data Services, а также ограничения использования LIN-сервиса данных, реализуемого в Протоколе открытых данных (OData). Для получения дополнительной информации о составлении и выполнения запросов в [Querying the Data Service](querying-the-data-service-wcf-data-services.md)отношении службы данных на основе OData см.  
  
## <a name="composing-linq-queries"></a>Составление LINQ-запросов  
 LINQ позволяет составлять запросы к коллекции объектов, которая реализует <xref:System.Collections.Generic.IEnumerable%601>. Как диалоговый ящик **Add Service Reference** в Visual Studio, так и инструмент DataSvcUtil.exe используются для создания <xref:System.Data.Services.Client.DataServiceContext>представления службы OData как класса контейнеров сущности, который наследует, а также объектов, представляющих объекты, возвращенные в каналы. Эти средства также создают свойства для класса контейнера сущностей для коллекций, представляемых службой в виде потоков. Каждое свойство класса, инкапсулирующего службу данных, возвращает объект <xref:System.Data.Services.Client.DataServiceQuery%601>. Поскольку класс <xref:System.Data.Services.Client.DataServiceQuery%601> реализует интерфейс <xref:System.Linq.IQueryable%601>, определяемый LINQ, можно составить LINQ-запрос для потоков, предоставляемых службой данных, которые преобразуются клиентской библиотекой в URI-запрос, отправляемый службе данных при выполнении.  
  
> [!IMPORTANT]
> Набор запросов, выразимых в синтаксисе LIN', шире, чем в синтаксисе URI, который используется службами данных OData. Исключение <xref:System.NotSupportedException> возникает, если запрос не может быть сопоставлен с URI в целевой службе данных. Для получения дополнительной информации в этой теме можно ознакомиться с [методами неподдерживаемых ЛИНЗ.](linq-considerations-wcf-data-services.md#unsupportedMethods)  
  
 В следующем примере показан запрос LINQ, который возвращает объекты `Orders` со стоимостью транспортировки более 30 долларов и упорядочивает результаты по дате отправки, начиная с самой последней.  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]
  
 Этот запрос LIN's переведен в следующий запрос URI, который выполняется в отношении службы [данных на](quickstart-wcf-data-services.md) основе Northwind:  
  
```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 Для получения более подробной информации о LINЗ [см.](../../../csharp/programming-guide/concepts/linq/index.md) [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)  
  
 LINQ позволяет составлять запросы как с помощью декларативного синтаксиса запросов на основе определенного языка (как показано в предыдущем примере), так и в виде набора методов запроса, известных как стандартные операторы запроса. Запрос, эквивалентный запросу из предыдущего примера, может быть составлен только с помощью синтаксиса на основе методов, как показано в следующем примере.  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpressionspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpressionspecific)]
  
 Клиент WCF Data Services может перевести оба вида составных запросов в URI запроса, и можно расширить запрос LIN, приложив методы запроса к выражению запроса. При составлении LINQ-запросов путем добавления синтаксиса запросов в выражение запроса или в объект <xref:System.Data.Services.Client.DataServiceQuery%601> операторы добавляются в URI-запрос в порядке вызова методов. Это эквивалентно вызову метода <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> для добавления параметров запроса в URI-запрос.  
  
## <a name="executing-linq-queries"></a>Выполнение LINQ-запросов  
 Некоторые методы LINQ-запроса, такие как <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> или <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, приводят к выполнению запроса при добавлении в запрос. Запрос также выполняется, если результаты неявно перечисляются, например в цикле `foreach` или когда запрос приписывается к коллекции `List`. Для получения дополнительной [Querying the Data Service](querying-the-data-service-wcf-data-services.md)информации см.  
  
 Клиент выполняет LINQ-запрос в два этапа. По возможности сначала вычисляются LINQ-выражения в запросе на стороне клиента, а затем создается URI-запрос, который будет отправлен службе данных для проведения вычислений по отношению к данным в службе. Для получения дополнительной информации смотрите раздел [«Клиент против выполнения сервера»](querying-the-data-service-wcf-data-services.md#executingQueries) в [службе обработки данных.](querying-the-data-service-wcf-data-services.md)  
  
 Если запрос LIN'а не может быть переведен в URI запроса, отвечая требованиям OData, при попытке выполнения возникает исключение. Для получения дополнительной [Querying the Data Service](querying-the-data-service-wcf-data-services.md)информации см.  
  
## <a name="linq-query-examples"></a>Примеры LINQ-запросов  
 Примеры следующих разделов демонстрируют виды запросов LIN, которые могут быть выполнены в отношении службы OData.  
  
<a name="filtering"></a>
### <a name="filtering"></a>Фильтрация  
 Образцы LINQ-запросов в этом подразделе сортируют данные в потоке, возвращаемом службой.  
  
 Следующие примеры эквиваленты запросам, которые фильтруют возвращаемые `Orders` сущности так, чтобы были возвращены только заказы со стоимостью более 30 долларов.  
  
- Использование синтаксиса LINQ-запросов  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwhereclausespecific)]
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwhereclausespecific)]
  
- Использование методов LINQ-запросов  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwheremethodspecific)]
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwheremethodspecific)]
  
- Параметр строки URI-запроса `$filter`:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitquerywheremethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitquerywheremethodspecific)]
  
 Все вышеприведенные примеры преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.  
  
<a name="sorting"></a>
### <a name="sorting"></a>Сортировка  
 Далее приведены примеры эквивалентных запросов, которые сортируют возвращаемые данные как по названию компании, так и по почтовому индексу в порядке убывания.  
  
- Использование синтаксиса LINQ-запросов  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbyclausespecific)]
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbyclausespecific)]
  
- Использование методов LINQ-запросов  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbymethodspecific)]
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbymethodspecific)]
  
- Параметр строки URI-запроса `$orderby`):  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryorderbymethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryorderbymethodspecific)]
  
 Все вышеприведенные примеры преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.  
  
<a name="projection"></a>
### <a name="projection"></a>Проекция  
 Далее приведены примеры эквивалентных запросов, которые проецируют возвращаемые данные в более узкий тип `CustomerAddress`.  
  
- Использование синтаксиса LINQ-запросов  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectclausespecific)]
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectclausespecific)]
  
- Использование методов LINQ-запросов  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectmethodspecific)]
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectmethodspecific)]

> [!NOTE]
> Параметр запроса `$select` нельзя добавить в URI-запрос с помощью метода <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. Рекомендуется использовать метод <xref:System.Linq.Enumerable.Select%2A> на основе LINQ для создания параметра запроса `$select` в URI-запросе.  
  
 Оба приведенных выше примера преобразуются в URI-запрос: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.  
  
<a name="paging"></a>
### <a name="client-paging"></a>Клиент разбиения по страницам  
 Далее приведены примеры эквивалентных запросов, запрашивающих страницу сущностей отсортированных заказов, которая включает 25 заказов и не включает первые 50 заказов.  
  
- Применение методов запроса к LINQ-запросу:  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqskiptakemethodspecific)]
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqskiptakemethodspecific)]
  
- Параметры строки URI-запроса `$skip` и `$top`):  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryskiptakemethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryskiptakemethodspecific)]
  
 Оба приведенных выше примера преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.  
  
<a name="expand"></a>
### <a name="expand"></a>Разверните  
 При запросе службы данных OData можно запросить, чтобы объекты, относящиеся к объекту, на которого нацелен запрос, были включены в возвращенную ленту. Метод <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> вызывается для <xref:System.Data.Services.Client.DataServiceQuery%601> для набора сущностей, заданного LINQ-запросом, при этом имя связанного набора сущностей предоставляется в виде параметра `path`. Для получения дополнительной информации [см.](loading-deferred-content-wcf-data-services.md)  
  
 В следующих примерах показаны эквивалентные способы использования метода <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> в запросе.  
  
- Синтаксис LINQ-запроса:  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandspecific)]  
  
- С помощью методов LINQ-запроса:  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandmethodspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandmethodspecific)]

 Оба приведенных выше примера преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.  
  
<a name="unsupportedMethods"></a>
## <a name="unsupported-linq-methods"></a>Неподдерживаемые LINQ-методы  
 Следующая таблица содержит классы методов LIN' не поддерживаются и не могут быть включены в запрос, выполняемый против службы OData:  
  
|Тип операции|Неподдерживаемый метод|  
|--------------------|------------------------|  
|Операторы набора|Все операторы набора не поддерживаются в запросе <xref:System.Data.Services.Client.DataServiceQuery%601>, включая следующие запросы:<br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|Операторы упорядочивания|Следующие операторы упорядочивания, которым требуется метод <xref:System.Collections.Generic.IComparer%601>, не поддерживаются в запросе <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|Операторы проецирования и фильтрации|Следующие операторы проецирования и фильтрации, принимающие аргументы положения, не поддерживаются в запросе <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|Операторы группирования|Все операторы группирования не поддерживаются в запросе <xref:System.Data.Services.Client.DataServiceQuery%601>, включая следующие запросы:<br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> Операции группирования следует выполнять на стороне клиента.|  
|Статистические операторы|Все статистические операторы не поддерживаются в запросе <xref:System.Data.Services.Client.DataServiceQuery%601>, включая следующие запросы:<br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> Статистические операции должны выполняться на стороне клиента либо инкапсулироваться операцией службы.|  
|Операторы разбиения на страницы|Следующие операторы разбиения на страницы не поддерживаются в запросе <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A><br/><br/>**Примечание:**  Операторы paging, выполняемые на пустой последовательности, возвращают нулю.|  
|Другие операторы|Следующие операторы также не <xref:System.Data.Services.Client.DataServiceQuery%601>поддерживаются против:<br /><br /> - <xref:System.Linq.Enumerable.Empty%2A><br />- <xref:System.Linq.Enumerable.Range%2A><br />- <xref:System.Linq.Enumerable.Repeat%2A><br />- <xref:System.Linq.Enumerable.ToDictionary%2A><br />- <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>
## <a name="supported-expression-functions"></a>Поддерживаемые функции выражений  
 Следующие методы и свойства общего времени выполнения (CLR) поддерживаются, поскольку они могут быть переведены в экспресс запрос для включения в запрос URI в службу OData:  
  
|Элемент <xref:System.String>|Поддерживаемая функция OData|  
|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.String.Concat%28System.String%2CSystem.String%29>|`string concat(string p0, string p1)`|  
|<xref:System.String.Contains%28System.String%29>|`bool substringof(string p0, string p1)`|  
|<xref:System.String.EndsWith%28System.String%29>|`bool endswith(string p0, string p1)`|  
|<xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>|`int indexof(string p0, string p1)`|  
|<xref:System.String.Length>|`int length(string p0)`|  
|<xref:System.String.Replace%28System.String%2CSystem.String%29>|`string replace(string p0, string find, string replace)`|  
|<xref:System.String.Substring%28System.Int32%29>|`string substring(string p0, int pos)`|  
|<xref:System.String.Substring%28System.Int32%2CSystem.Int32%29>|`string substring(string p0, int pos, int length)`|  
|<xref:System.String.ToLower>|`string tolower(string p0)`|  
|<xref:System.String.ToUpper>|`string toupper(string p0)`|  
|<xref:System.String.Trim>|`string trim(string p0)`|  
  
|<xref:System.DateTime>Член<sup>1</sup>|Поддерживаемая функция OData|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <sup>1</sup> Поддерживаются также эквивалентные <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType> свойства <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> даты и времени и метода в Visual Basic.  
  
|Элемент <xref:System.Math>|Поддерживаемая функция OData|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|Элемент <xref:System.Linq.Expressions.Expression>|Поддерживаемая функция OData|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 Клиент может также вычислить дополнительные функции среды CLR на стороне клиента. Исключение <xref:System.NotSupportedException> возникает для любого выражения, которое не может быть вычислено на стороне клиента и преобразовано в действительный URI-запрос для вычисления на сервере.  
  
## <a name="see-also"></a>См. также раздел

- [Выполнение запросов к службе данных](querying-the-data-service-wcf-data-services.md)
- [Проекции запросов](query-projections-wcf-data-services.md)
- [Материализация объектов](object-materialization-wcf-data-services.md)
- [OData: условные обозначения URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/)
