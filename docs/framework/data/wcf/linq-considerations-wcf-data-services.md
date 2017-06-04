---
title: "Рекомендации по LINQ (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы данных WCF, LINQ"
  - "выполнение запросов к службе данных [службы данных WCF]"
  - "Службы данных WCF, запрос"
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Рекомендации по LINQ (службы WCF Data Services)
Данный раздел содержит сведения о способе подготовки и выполнения запросов LINQ при использовании клиента [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], а также об ограничениях использования LINQ для запросов к службе данных, реализующей [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Создание и выполнение запросов к [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-службы данных на основе разделе [запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
## <a name="composing-linq-queries"></a>Составление LINQ-запросов  
 LINQ позволяет составлять запросы к коллекции объектов, который реализует <xref:System.Collections.Generic.IEnumerable%601>. Оба **Add Service Reference** диалогового окна в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] и средство DataSvcUtil.exe используются для формирования представление [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] службы как класс контейнера сущностей, который наследует от <xref:System.Data.Services.Client.DataServiceContext>, а также объекты, представляющие сущности, возвращаемые в потоках. Эти средства также создают свойства для класса контейнера сущностей для коллекций, представляемых службой в виде потоков. Каждое из этих свойств класса, инкапсулирующего службу данных возвращает <xref:System.Data.Services.Client.DataServiceQuery%601>. Поскольку <xref:System.Data.Services.Client.DataServiceQuery%601> реализует <xref:System.Linq.IQueryable%601> интерфейс, определяемый LINQ, можно составить LINQ-запрос для потоков, предоставляемых службой данных, которые преобразуются клиентской библиотекой в URI, который отправляется в службу данных при выполнении запроса.  
  
> [!IMPORTANT]
>  Набор запросов, которые можно выразить в синтаксисе LINQ, шире, чем набор запросов, поддерживаемых в URI-синтаксисе на основе технологии [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], используемой в службах данных. Объект <xref:System.NotSupportedException> возникает, когда запрос не может быть сопоставлен с URI в целевой службе данных. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][неподдерживаемые методы LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md#unsupportedMethods) в этом разделе.  
  
 В следующем примере показан запрос LINQ, который возвращает объекты `Orders` со стоимостью транспортировки более&30; долларов и упорядочивает результаты по дате отправки, начиная с самой последней.  
  
  [Astoria NorthwindClient #AddQueryOptionsLinqSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#AddQueryOptionsLinqSpecific)]  
  
 Этот запрос LINQ преобразуется в следующий запрос URI, который выполняется для основанной на Northwind [быстрого запуска](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) службы данных:  
  
```  
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 Дополнительные сведения о LINQ см. в разделе [LINQ (Language-Integrated Query)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).  
  
 LINQ позволяет составлять запросы как с помощью декларативного синтаксиса запросов на основе определенного языка (как показано в предыдущем примере), так и в виде набора методов запроса, известных как стандартные операторы запроса. Запрос, эквивалентный запросу из предыдущего примера, может быть составлен только с помощью синтаксиса на основе методов, как показано в следующем примере.  
  
  [Astoria NorthwindClient #AddQueryOptionsLinqExpressionSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#AddQueryOptionsLinqExpressionSpecific)]  
  
 Клиент [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] может преобразовать оба вида запросов в URI-запрос, а пользователь может расширить LINQ-запрос путем добавления методов в выражение запроса. При составлении запросов LINQ путем добавления синтаксиса выражения запроса или <xref:System.Data.Services.Client.DataServiceQuery%601>, операции будут добавлены в запрос URI в том порядке, в котором вызываются методы. Это эквивалентно вызову <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> метод для добавления каждого параметра запроса в URI запроса.  
  
## <a name="executing-linq-queries"></a>Выполнение LINQ-запросов  
 Некоторые методы LINQ-запроса, таких как <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> или <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, при добавлении в запрос вызывает выполнение запроса. Запрос также выполняется, если результаты неявно перечисляются, например в цикле `foreach` или когда запрос приписывается к коллекции `List`. Дополнительные сведения см. в разделе [запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Клиент выполняет LINQ-запрос в два этапа. По возможности сначала вычисляются LINQ-выражения в запросе на стороне клиента, а затем создается URI-запрос, который будет отправлен службе данных для проведения вычислений по отношению к данным в службе. Дополнительные сведения см. в разделе [клиент и запуск сервера](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md#executingQueries) в [запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Если LINQ-запрос нельзя преобразовать в URI-запрос, совместимый с [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], при попытке выполнения возникнет исключение. Дополнительные сведения см. в разделе [запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
## <a name="linq-query-examples"></a>Примеры LINQ-запросов  
 Примеры в следующих разделах демонстрируют LINQ-запросы, которые могут быть выполнены для службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
<a name="filtering"></a>   
### <a name="filtering"></a>Фильтрация  
 Образцы LINQ-запросов в этом подразделе сортируют данные в потоке, возвращаемом службой.  
  
 Следующие примеры эквиваленты запросам, которые фильтруют возвращаемые `Orders` сущности так, чтобы были возвращены только заказы со стоимостью более&30; долларов.  
  
-   Использование синтаксиса LINQ-запросов  
  
      [Astoria NorthwindClient #LinqWhereClauseSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqWhereClauseSpecific)]  
  
-   Использование методов LINQ-запросов  
  
      [Astoria NorthwindClient #LinqWhereMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqWhereMethodSpecific)]  
  
-   Параметр строки URI-запроса `$filter`:  
  
      [Astoria NorthwindClient #ExplicitQueryWhereMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#ExplicitQueryWhereMethodSpecific)]  
  
 Все вышеприведенные примеры преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.  
  
<a name="sorting"></a>   
### <a name="sorting"></a>Сортировка  
 Далее приведены примеры эквивалентных запросов, которые сортируют возвращаемые данные как по названию компании, так и по почтовому индексу в порядке убывания.  
  
-   Использование синтаксиса LINQ-запросов  
  
      [Astoria NorthwindClient #LinqOrderByClauseSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqOrderByClauseSpecific)]  
  
-   Использование методов LINQ-запросов  
  
      [Astoria NorthwindClient #LinqOrderByMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqOrderByMethodSpecific)]  
  
-   Параметр строки URI-запроса `$orderby`):  
  
      [Astoria NorthwindClient #ExplicitQueryOrderByMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#ExplicitQueryOrderByMethodSpecific)]  
  
 Все вышеприведенные примеры преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.  
  
<a name="projection"></a>   
### <a name="projection"></a>Проекция  
 Далее приведены примеры эквивалентных запросов, которые проецируют возвращаемые данные в более узкий тип `CustomerAddress`.  
  
-   Использование синтаксиса LINQ-запросов  
  
      [Astoria NorthwindClient #LinqSelectClauseSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqSelectClauseSpecific)]  
  
-   Использование методов LINQ-запросов  
  
      [Astoria NorthwindClient #LinqSelectMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqSelectMethodSpecific)]  
  
> [!NOTE]
>  `$select` Параметр запроса не может добавить в URI запроса с помощью <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> метод. Мы рекомендуем использовать LINQ <xref:System.Linq.Enumerable.Select%2A> способ создания `$select` параметр в запросе URI запроса.\</TSource, TResult>  
  
 Оба приведенных выше примера преобразуются в URI-запрос: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.  
  
<a name="paging"></a>   
### <a name="client-paging"></a>Клиент разбиения по страницам  
 Далее приведены примеры эквивалентных запросов, запрашивающих страницу сущностей отсортированных заказов, которая включает 25 заказов и не включает первые 50 заказов.  
  
-   Применение методов запроса к LINQ-запросу:  
  
      [Astoria NorthwindClient #LinqSkipTakeMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqSkipTakeMethodSpecific)]  
  
-   Параметры строки URI-запроса `$skip` и `$top`):  
  
      [Astoria NorthwindClient #ExplicitQuerySkipTakeMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#ExplicitQuerySkipTakeMethodSpecific)]  
  
 Оба приведенных выше примера преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.  
  
<a name="expand"></a>   
### <a name="expand"></a>Развернуть  
 При отправке запроса службе данных [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] можно указать, что сущности, связанные с целевой сущностью, должны быть включены в возвращаемый поток. <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> вызывается метод <xref:System.Data.Services.Client.DataServiceQuery%601> для набора сущностей, LINQ-запросом, вместе со связанной сущностью имя набора предоставляется как `path` параметр. Дополнительные сведения см. в разделе [загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 В следующих примерах эквивалентные способы использования <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> метод в запросе:  
  
-   Синтаксис LINQ-запроса:  
  
      [Astoria NorthwindClient #LinqQueryExpandSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqQueryExpandSpecific)]  
  
-   С помощью методов LINQ-запроса:  
  
      [Astoria NorthwindClient #LinqQueryExpandMethodSpecific](../../../../amples/snippets/xml/VS_Snippets_Misc/astoria northwind service/astoria.vsmdi NorthwindClient#LinqQueryExpandMethodSpecific)]  
  
 Оба приведенных выше примера преобразуются в URI-запрос: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.  
  
<a name="unsupportedMethods"></a>   
## <a name="unsupported-linq-methods"></a>Неподдерживаемые LINQ-методы  
 В следующей таблице приведены классы LINQ-методов, которые не поддерживаются и не могут быть включены в запрос, выполняемый для службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
|Тип операции|Неподдерживаемые методы|  
|--------------------|------------------------|  
|Операторы набора|Все операторы набора не поддерживаются в <xref:System.Data.Services.Client.DataServiceQuery%601>, включая следующие:<br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>\</TFirst, TSecond, TResult>|  
|Операторы упорядочивания|Следующие операторы упорядочивания, которым требуется <xref:System.Collections.Generic.IComparer%601> не поддерживаются в <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29> </TSource, TKey> </TSource, TKey><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29> \</TSource, TKey> \</TSource, TKey><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29> </TSource, TKey> </TSource, TKey><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29> \</TSource, TKey> \</TSource, TKey>|  
|Операторы проецирования и фильтрации|Следующие проекции и фильтрации операторы, которые принимают позиционные аргументы не поддерживаются в <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29> </TOuter, TInner, TResult> </TInner, TKey> </TOuter, TKey> </TOuter, TInner, TKey, TResult><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29> </TSource, Int32, TResult> </TSource, TResult><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29> </TSource, TResult><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29> </TSource, TResult><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29> \</TSource, TCollection, TResult> \</TSource, TCollection, TResult><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29> </TSource, TCollection, TResult> </TSource, TCollection, TResult><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29> \</TSource, Int32, Boolean>|  
|Операторы группирования|Все операторы группирования не поддерживаются в <xref:System.Data.Services.Client.DataServiceQuery%601>, включая следующие:<br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A>\</TSource, TKey><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A>\</TOuter, TInner, TKey, TResult><br /><br /> Операции группирования следует выполнять на стороне клиента.|  
|Статистические операторы|Все статистические операторы не поддерживаются в <xref:System.Data.Services.Client.DataServiceQuery%601>, включая следующие:<br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> Статистические операции должны выполняться на стороне клиента либо инкапсулироваться операцией службы.|  
|Операторы разбиения на страницы|Следующие операторы разбиения на страницы не поддерживаются в <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A> **Примечание:** операторы разбиения на страницы, выполняемые для пустой последовательности возвращает значение null.|  
|Другие операторы|Следующие операторы не поддерживаются для <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> 1.  <xref:System.Linq.Enumerable.Empty%2A><br />2.  <xref:System.Linq.Enumerable.Range%2A><br />3.  <xref:System.Linq.Enumerable.Repeat%2A><br />4.  <xref:System.Linq.Enumerable.ToDictionary%2A></TSource, TKey><br />5.  <xref:System.Linq.Enumerable.ToLookup%2A>\</TSource, TKey>|  
  
<a name="supportedExpressions"></a>   
## <a name="supported-expression-functions"></a>Поддерживаемые функции выражений  
 Следующие методы среды CLR и свойства поддерживаются, поскольку они могут быть преобразованы в выражение запроса и включены в URI-запрос, отправляемый службе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
|<xref:System.String> член|Поддерживаемая функция [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]|  
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
  
|<xref:System.DateTime> член<sup>1</sup>|Поддерживаемая функция [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <sup>1</sup>эквивалентные свойства даты и времени из <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=fullName>, а также <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> также поддерживаются в Visual Basic.  
  
|<xref:System.Math> член|Поддерживаемая функция [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<xref:> System.Linq.Expressions.Expression?qualifyHint=False&autoUpgrade=True член|Поддерживаемая функция [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 Клиент может также вычислить дополнительные функции среды CLR на стороне клиента. Объект <xref:System.NotSupportedException> возникает для любого выражения, не может быть вычислено на стороне клиента и нельзя преобразовать в допустимый URI запроса для вычисления на сервере.  
  
## <a name="see-also"></a>См. также  
 [Выполнение запросов к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)   
 [Проекции запросов](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)   
 [Материализация объектов](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)   
 [OData: Соглашения URI](http://go.microsoft.com/fwlink/?LinkID=185564)