---
title: Выполнение запросов к службе данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 823e9444-27aa-4f1f-be8e-0486d67f54c0
ms.openlocfilehash: e37a1654bdc62937bbb27c293a110293c9928645
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975168"
---
# <a name="querying-the-data-service-wcf-data-services"></a>Выполнение запросов к службе данных (службы данных WCF)

Клиентская библиотека служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет выполнять запросы службы данных, используя знакомые шаблоны программирования .NET Framework, включая использование языка LINQ. Клиентская библиотека преобразует запрос, определенный на клиенте как экземпляр класса <xref:System.Data.Services.Client.DataServiceQuery%601>, в сообщение запроса HTTP GET. Библиотека получает ответное сообщение и преобразует его в экземпляры клиентских классов службы данных. Эти классы отслеживаются с помощью <xref:System.Data.Services.Client.DataServiceContext>, которому принадлежит объект <xref:System.Data.Services.Client.DataServiceQuery%601>.

## <a name="data-service-queries"></a>Запросы к службе данных

Универсальный класс <xref:System.Data.Services.Client.DataServiceQuery%601> представляет запрос, который возвращает коллекцию, включающую ноль или больше экземпляров типа сущности. Запрос к службе данных всегда относится к контексту существующей службы данных. Этот контекст поддерживает URI службы и сведения о метаданных, необходимые для создания и выполнения запроса.

При использовании диалогового окна **Добавление ссылки на службу** для добавления службы данных в клиентское приложение на основе .NET Framework создается класс контейнера сущностей, наследуемый от класса <xref:System.Data.Services.Client.DataServiceContext>. Этот класс включает свойства, возвращаемые типизированными экземплярами <xref:System.Data.Services.Client.DataServiceQuery%601>. Для каждого набора сущностей, предоставляемого службой данных, имеется одно свойство. Эти свойства облегчают создание экземпляра типизированного объекта <xref:System.Data.Services.Client.DataServiceQuery%601>.

Запрос выполняется в следующих сценариях.

- Если результаты перечислены неявно, например:

  - Если свойство <xref:System.Data.Services.Client.DataServiceContext>, которое представляет набор сущностей, перечисляется, например во время цикла `foreach` (C#) или `For Each` (Visual Basic).

  - Если запрос назначен коллекции `List`.

- Если метод <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A> или <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> вызывается явно.

- При вызове оператора выполнения запроса LINQ, такого как <xref:System.Linq.Enumerable.First%2A> или <xref:System.Linq.Enumerable.Single%2A>.

Следующий запрос, если он выполняется, возвращает все сущности `Customers` в службе данных Northwind:

[!code-csharp[Astoria Northwind Client#GetAllCustomersSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomersspecific)]
[!code-vb[Astoria Northwind Client#GetAllCustomersSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomersspecific)]

Дополнительные сведения см. [в разделе инструкции. выполнение запросов службы данных](how-to-execute-data-service-queries-wcf-data-services.md).

Клиент [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживает запросы для объектов с поздним связыванием, например при использовании *динамического* типа в C#. Тем не менее в силу влияния на производительность для службы данных необходимо всегда составлять строго типизированные запросы. Тип <xref:System.Tuple> и динамические объекты не поддерживаются клиентом.

## <a name="linq-queries"></a>Запросы LINQ

Поскольку класс <xref:System.Data.Services.Client.DataServiceQuery%601> реализует интерфейс <xref:System.Linq.IQueryable%601>, определенный LINQ, клиентская библиотека [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] может преобразовать запросы LINQ к данным набора сущностей в URI, представляющий выражение запроса, вычисляемое для ресурса службы данных. В следующем примере показан запрос LINQ, эквивалентный предыдущему объекту <xref:System.Data.Services.Client.DataServiceQuery%601>, который возвращает объект `Orders` со стоимостью транспортировки более 30 долларов и упорядочивает результаты по стоимости транспортировки.

[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]

Этот запрос LINQ преобразуется в следующий универсальный код ресурса (URI) запроса, который выполняется для службы данных [краткого руководства](quickstart-wcf-data-services.md) на основе Northwind:

```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30
```

> [!NOTE]
> Набор запросов, которые можно выразить в синтаксисе LINQ, шире, чем набор запросов, поддерживаемых в URI-синтаксисе на основе технологии REST, который используется в службах данных. Исключение <xref:System.NotSupportedException> возникает, если запрос не может быть сопоставлен с URI в целевой службе данных.

Дополнительные сведения см. в статье [рекомендации по LINQ](linq-considerations-wcf-data-services.md).

## <a name="adding-query-options"></a>Добавление параметров запроса

Запросы службы данных поддерживают все параметры запроса, которые предоставляют службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Метод <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> вызывается для присоединения параметров запроса к экземпляру <xref:System.Data.Services.Client.DataServiceQuery%601>. <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> возвращает новый экземпляр <xref:System.Data.Services.Client.DataServiceQuery%601>, эквивалентный исходному запросу, но с новым набором параметров запроса. Следующий запрос, если он выполняется, возвращает объект `Orders`, отфильтрованный по значению `Freight` и упорядоченный по `OrderID` по убыванию.

[!code-csharp[Astoria Northwind Client#AddQueryOptionsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionsspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionsspecific)]

Параметр запроса `$orderby` можно использовать как для упорядочения, так и для фильтрации запроса, основанного на одном свойстве, как в следующем примере, в котором фильтруются и упорядочиваются возвращаемые объекты `Orders`, основанные на значении свойства `Freight`:

[!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#orderwithfilter)]
[!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#orderwithfilter)]

Можно последовательно вызывать метод <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>, чтобы сконструировать сложные выражения запроса. Дополнительные сведения см. [в разделе инструкции. Добавление параметров запроса в запрос службы данных](how-to-add-query-options-to-a-data-service-query-wcf-data-services.md).

Параметры запроса предоставляют другой способ выражения синтаксических компонентов запроса LINQ. Дополнительные сведения см. в статье [рекомендации по LINQ](linq-considerations-wcf-data-services.md).

> [!NOTE]
> Параметр запроса `$select` нельзя добавить в URI-запрос с помощью метода <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. Рекомендуется использовать метод <xref:System.Linq.Enumerable.Select%2A> на основе LINQ для создания параметра запроса `$select` в URI-запросе.

<a name="executingQueries"></a>

## <a name="client-versus-server-execution"></a>Клиент и запуск сервера

Клиент выполняет запрос в два этапа. По возможности сначала вычисляются выражения в запросе на стороне клиента, а затем создается URI-запрос, который будет отправлен службе данных для проведения вычислений по отношению к данным в службе. Рассмотрим следующий запрос LINQ:

[!code-csharp[Astoria Northwind Client#LinqQueryClientEvalSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryclientevalspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryClientEvalSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryclientevalspecific)]

В этом примере выражение `(basePrice – (basePrice * discount))` вычисляется на стороне клиента. По этой причине фактический URI-запрос `http://localhost:12345/northwind.svc/Products()?$filter=(UnitPrice gt 90.00M) and substringof('bike',ProductName)`, отправляемый службе данных, содержит уже вычисленное десятичное значение `90` в предложении фильтра. Другие части выражения фильтрации, включая выражение подстроки, вычисляются службой данных. Выражения, вычисляемые на клиенте, следуют семантике среды CLR, а выражения, отправляемые в службу данных, полагаются на реализацию службы данных протокола OData. Также следует помнить о сценариях, в которых это отдельное вычисление может привести к непредвиденным результатам, например если клиент и служба выполняют временные вычисления в разных часовых поясах.

## <a name="query-responses"></a>Ответы на запросы

При выполнении запроса <xref:System.Data.Services.Client.DataServiceQuery%601> он возвращает объект <xref:System.Collections.Generic.IEnumerable%601> запрошенного типа сущности. Этот результат запроса может быть приведен к объекту <xref:System.Data.Services.Client.QueryOperationResponse%601>, как в следующем примере:

[!code-csharp[Astoria Northwind Client#GetResponseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getresponsespecific)]
[!code-vb[Astoria Northwind Client#GetResponseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getresponsespecific)]

Экземпляры типа сущности, которые представляют сущности в службе данных, создаются на клиенте процессом, называемым материализацией объектов. Дополнительные сведения см. в разделе [материализация объектов](object-materialization-wcf-data-services.md). Объект <xref:System.Data.Services.Client.QueryOperationResponse%601> реализует объект <xref:System.Collections.Generic.IEnumerable%601> для предоставления доступа к результатам запроса.

Объект <xref:System.Data.Services.Client.QueryOperationResponse%601> имеет также следующие члены, позволяющие производить доступ к дополнительным сведениям о результате запроса.

- <xref:System.Data.Services.Client.OperationResponse.Error%2A> — возвращает ошибку, инициируемую операцией, если ошибка возникает.

- <xref:System.Data.Services.Client.OperationResponse.Headers%2A> — содержит коллекцию заголовков ответов HTTP, связанных с ответом на запрос.

- <xref:System.Data.Services.Client.QueryOperationResponse.Query%2A> — возвращает исходный объект <xref:System.Data.Services.Client.DataServiceQuery%601>, создавший ответ <xref:System.Data.Services.Client.QueryOperationResponse%601>.

- <xref:System.Data.Services.Client.OperationResponse.StatusCode%2A> — возвращает код ответа HTTP для ответа на запрос.

- <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> — возвращает общее число сущностей в наборе сущностей, если метод <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A> вызван на клиенте <xref:System.Data.Services.Client.DataServiceQuery%601>.

- <xref:System.Data.Services.Client.QueryOperationResponse.GetContinuation%2A> — возвращает объект <xref:System.Data.Services.Client.DataServiceQueryContinuation>, который содержит URI следующей страницы результатов.

По умолчанию [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] возвращает только те данные, которые явно выбраны с помощью URI запроса. Это дает возможность явно загрузить дополнительные данные из службы данных, если это необходимо. Запрос отправляется в службу данных при каждой явной загрузке данных из службы данных. Данные, которые можно явно загрузить, включают связанные сущности, разбитые на страницы данные ответа и потоки двоичных данных.

> [!NOTE]
> Поскольку служба данных может возвратить разбитый на страницы ответ, рекомендуется, чтобы приложение использовало шаблон программирования для обработки разбитого на страницы ответа службы данных. Дополнительные сведения см. в разделе [Загрузка отложенного содержимого](loading-deferred-content-wcf-data-services.md).

Объем возвращаемых запросом данных может быть также уменьшен указанием, что в ответе возвращаются только определенные свойства сущности. Дополнительные сведения см. в разделе [проекции запросов](query-projections-wcf-data-services.md).

## <a name="getting-a-count-of-the-total-number-of-entities-in-the-set"></a>Получение подсчета общего числа сущностей в наборе

В некоторых сценариях полезно знать общее число сущностей в наборе сущностей, а не только число, возвращаемое запросом. Вызовите метод <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A> по отношению к объекту <xref:System.Data.Services.Client.DataServiceQuery%601> для запроса, чтобы этот общий итог подсчета сущностей в наборе возвращался с результатом запроса. В этом случае свойство <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> возвращаемого объекта <xref:System.Data.Services.Client.QueryOperationResponse%601> возвращает общее количество сущностей в наборе.

Можно также получить только общее число сущностей в наборе либо как значение типа <xref:System.Int32>, либо как значение типа <xref:System.Int64>, вызвав метод <xref:System.Linq.Enumerable.Count%2A> или <xref:System.Linq.Enumerable.LongCount%2A> соответственно. Если вызываются эти методы, объект <xref:System.Data.Services.Client.QueryOperationResponse%601> не возвращается, при этом возвращается только значение подсчета. Дополнительные сведения см. в разделе [инструкции. Определение количества сущностей, возвращаемых запросом](number-of-entities-returned-by-a-query-wcf.md).

## <a name="in-this-section"></a>Содержание

- [Проекции запросов](query-projections-wcf-data-services.md)

- [Материализация объектов](object-materialization-wcf-data-services.md)

- [Рекомендации по LINQ](linq-considerations-wcf-data-services.md)

- [Практическое руководство. Выполнение запросов к службе данных](how-to-execute-data-service-queries-wcf-data-services.md)

- [Практическое руководство. Добавление параметров запроса к запросу службы данных](how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)

- [Практическое руководство. Определение количества сущностей, возвращаемых запросом](number-of-entities-returned-by-a-query-wcf.md)

- [Практическое руководство. Указание учетных данных клиента для запроса службы данных](specify-client-creds-for-a-data-service-request-wcf.md)

- [Практическое руководство. Установка заголовков в клиентском запросе](how-to-set-headers-in-the-client-request-wcf-data-services.md)

- [Практическое руководство. Проекция результатов запроса](how-to-project-query-results-wcf-data-services.md)

## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
