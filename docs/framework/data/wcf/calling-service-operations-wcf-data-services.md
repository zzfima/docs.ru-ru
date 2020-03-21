---
title: Вызов операций служб (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1767f3a7-29d2-4834-a763-7d169693fa8b
ms.openlocfilehash: 41aac38cec97ae1afdd3c3c051d04ff242e7729d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174359"
---
# <a name="calling-service-operations-wcf-data-services"></a>Вызов операций служб (службы данных WCF)
Протокол открытых данных (OData) определяет операции службы для службы данных. WCF Data Services позволяет определить такие операции как методы службы данных. Как и для других ресурсов службы данных, для обращения к этим операциям службы используются идентификаторы URI. Операция службы может возвращать коллекции типов сущностей, единственные экземпляры типа сущностей и примитивные типы, такие как integer и string. Операция службы также может также вернуть значение `null` (`Nothing` в Visual Basic). Клиентская библиотека WCF Data Services может использоваться для доступа к службам, которые поддерживают запросы HTTP GET. Такого рода операции службы определяются как методы, к которым применен атрибут <xref:System.ServiceModel.Web.WebGetAttribute>. Для получения дополнительной информации [см.](service-operations-wcf-data-services.md)  
  
 Операции службы подвергаются в метаданных, возвращенных службой данных, которая реализует OData. В метаданных операции службы представлены как элементы `FunctionImport`. При создании строго типизированного элемента <xref:System.Data.Services.Client.DataServiceContext> средства Add Service Reference и DataSvcUtil.exe его не учитывают. Вследствие этого нельзя найти метод в контексте, который может быть использован для прямого вызова операции службы. Тем не менее, вы все еще можете использовать клиента WCF Data Services для вызова операций службы одним из следующих двух способов:  
  
- Вызов метода <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> на <xref:System.Data.Services.Client.DataServiceContext> с передачей URI операции службы вместе с любыми параметрами. Этот метод используется для вызова любой операции службы GET.  
  
- С помощью метода <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> применительно к <xref:System.Data.Services.Client.DataServiceContext> можно создать объект <xref:System.Data.Services.Client.DataServiceQuery%601>. При вызове метода <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> имя операции службы указывается в параметре `entitySetName`. Этот метод возвращает объект <xref:System.Data.Services.Client.DataServiceQuery%601>, который вызывает операцию службы при перечислении или вызове метода <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A>. Этот метод используется для вызова операций службы GET, которые возвращают коллекцию. Можно указать один параметр с помощью метода <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. Объект <xref:System.Data.Services.Client.DataServiceQuery%601>, возвращаемый этим методом, можно затем использовать как любой объект запроса. Для получения дополнительной [Querying the Data Service](querying-the-data-service-wcf-data-services.md)информации см.  
  
## <a name="considerations-for-calling-service-operations"></a>Рассмотрение вызова операций службы  
 При использовании клиента WCF Data Services для вызова сервисных операций применяются следующие соображения.  
  
- При асинхронном доступе к службе передачи данных <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> необходимо <xref:System.Data.Services.Client.DataServiceContext> использовать <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> эквивалентные асинхронные методы или на. <xref:System.Data.Services.Client.DataServiceQuery%601>  
  
- Библиотека клиентов WCF Data Services не может материализовать результаты операции службы, которая возвращает коллекцию примитивных типов.  
  
- Клиентская библиотека WCF Data Services не поддерживает вызов службы POST. Операции службы, которые вызываются запросом HTTP POST, определяются с использованием <xref:System.ServiceModel.Web.WebInvokeAttribute> с параметром `Method="POST"`. Для вызова операции службы с использованием запроса HTTP POST необходимо использовать <xref:System.Net.HttpWebRequest>.  
  
- Нельзя использовать <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> для вызова операции службы GET, которая возвращает единственный результат, представляющий собой сущность или простой тип, или операции, которой требуется несколько входных параметров. Вместо этого необходимо вызвать метод <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>.  
  
- Рассмотрите возможность создания метода расширения на строго типизированном разделяемом классе <xref:System.Data.Services.Client.DataServiceContext>, который создается этими средствами и использует метод <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> или <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> для вызова операции службы. Это позволяет вызывать операции службы непосредственно из контекста. Для получения дополнительной информации, см. [Service Operations and the WCF Data Services Client](https://docs.microsoft.com/archive/blogs/astoriateam/service-operations-and-the-wcf-data-services-client)  
  
- При использовании <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> вызова службы библиотека клиента автоматически избегает символов, поставляемых <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> в группу, выполняя кодирование зарезервированных символов, таких как амперсанд (&) и избегая одноцитатиц в строках. Однако при вызове одного из методов *выполнения* для вызова службы необходимо помнить об этом, чтобы выполнить это избегание любых значений строк, поставляемых пользователем. Одиночные кавычки в URI-адресах экранируются как пары одиночных кавычек.  
  
## <a name="examples-of-calling-service-operations"></a>Примеры вызова операций службы  
 В этом разделе содержатся следующие примеры вызова операций службы с помощью клиентской библиотеки WCF Data Services:  
  
- [Вызов&lt;выполнения&gt; T, чтобы вернуть коллекцию сущностей](calling-service-operations-wcf-data-services.md#ExecuteIQueryable)  
  
- [Использование Create'query&lt;T&gt; для возвращения коллекции сущностей](calling-service-operations-wcf-data-services.md#CreateQueryIQueryable)  
  
- [Вызов&lt;выполнения&gt; T для возвращения одного объекта](calling-service-operations-wcf-data-services.md#ExecuteSingleEntity)  
  
- [Вызов&lt;выполнения&gt; T, чтобы вернуть коллекцию примитивных ценностей](calling-service-operations-wcf-data-services.md#ExecutePrimitiveCollection)  
  
- [Вызов&lt;выполнения&gt; T, чтобы вернуть одно примитивное значение](calling-service-operations-wcf-data-services.md#ExecutePrimitiveValue)  
  
- [Вызов операции службы, не возвращающей никаких данных](calling-service-operations-wcf-data-services.md#ExecuteVoid)  
  
- [Асинхронный вызов операции службы](calling-service-operations-wcf-data-services.md#ExecuteAsync)  
  
<a name="ExecuteIQueryable"></a>
### <a name="calling-executet-to-return-a-collection-of-entities"></a>Вызов\<выполнения T> вернуть коллекцию сущностей  
 В следующем примере вызывается операция службы с именем GetOrdersByCity, которая принимает строковый параметр `city` и возвращает <xref:System.Linq.IQueryable%601>.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationiqueryable)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationiqueryable)]  
  
 В этом примере операция службы возвращает коллекцию объектов `Order` со связанными объектами `Order_Detail`.  
  
<a name="CreateQueryIQueryable"></a>
### <a name="using-createqueryt-to-return-a-collection-of-entities"></a>Использование>\<Create'ry T для возвращения коллекции объектов  
 В следующем примере метод <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> используется для возврата объекта <xref:System.Data.Services.Client.DataServiceQuery%601>, который используется для вызова той же операции службы GetOrdersByCity.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationcreatequery)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationcreatequery)]  
  
 В этом примере метод <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> используется для добавления параметра к запросу, а метод <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> — для включения в результаты связанных объектов Order_Details.  
  
<a name="ExecuteSingleEntity"></a>
### <a name="calling-executet-to-return-a-single-entity"></a>Вызов\<выполнения T> вернуть одно целое  
 В следующем примере вызывается операция службы с именем GetNewestOrder, которая возвращает одну сущность Order.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleentity)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleentity)]  
  
 В этом примере метод <xref:System.Linq.Enumerable.FirstOrDefault%2A> используется для запроса только одной сущности Order при исполнении.  
  
<a name="ExecutePrimitiveCollection"></a>
### <a name="calling-executet-to-return-a-collection-of-primitive-values"></a>Вызов\<выполнения T>, чтобы вернуть коллекцию примитивных ценностей  
 В следующем примере вызывается операция службы, которая возвращает коллекцию строковых значений.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationEnumString](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationenumstring)]  
  
<a name="ExecutePrimitiveValue"></a>
### <a name="calling-executet-to-return-a-single-primitive-value"></a>Вызов\<выполнения T>, чтобы вернуть одно примитивное значение  
 В следующем примере вызывается операция службы, которая возвращает одно строковое значение.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleint)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleint)]  
  
 В этом примере метод <xref:System.Linq.Enumerable.FirstOrDefault%2A> опять используется для запроса только одного целочисленного значения при исполнении.  
  
<a name="ExecuteVoid"></a>
### <a name="calling-a-service-operation-that-returns-no-data"></a>Вызов операции службы, не возвращающей никаких данных  
 В следующем примере вызывается операция службы, не возвращающая никаких данных.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationvoid)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationvoid)]  
  
 Поскольку данные не возвращаются, значение выполнения не присваивается. Единственное свидетельство того, что запрос выполнен, — отсутствие исключения <xref:System.Data.Services.Client.DataServiceQueryException> после выполнения.  
  
<a name="ExecuteAsync"></a>
### <a name="calling-a-service-operation-asynchronously"></a>Асинхронный вызов операции службы  
 В следующем примере операция службы вызывается асинхронно путем вызова метода <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> и метода <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncexecutioncomplete)]  
  
 Поскольку данные не возвращаются, значение, возвращенное после выполнения, не присваивается. Единственное свидетельство того, что запрос выполнен, — отсутствие исключения <xref:System.Data.Services.Client.DataServiceQueryException> после выполнения.  
  
 В следующем примере та же операция службы вызывается асинхронно с помощью метода <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationqueryasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationqueryasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncqueryexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncqueryexecutioncomplete)]  
  
## <a name="see-also"></a>См. также раздел

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
