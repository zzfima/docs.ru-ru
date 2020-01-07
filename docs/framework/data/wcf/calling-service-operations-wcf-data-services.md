---
title: Вызов операций служб (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1767f3a7-29d2-4834-a763-7d169693fa8b
ms.openlocfilehash: 1b8a00c7716a60daec4e4f6af6ae8e3a7a45e943
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346176"
---
# <a name="calling-service-operations-wcf-data-services"></a>Вызов операций служб (службы данных WCF)
Open Data Protocol (OData) определяет операции службы для службы данных. WCF Data Services позволяет определять такие операции в качестве методов в службе данных. Как и для других ресурсов службы данных, для обращения к этим операциям службы используются идентификаторы URI. Операция службы может возвращать коллекции типов сущностей, единственные экземпляры типа сущностей и примитивные типы, такие как integer и string. Операция службы также может также вернуть значение `null` (`Nothing` в Visual Basic). Клиентскую библиотеку WCF Data Services можно использовать для доступа к операциям службы, поддерживающим HTTP-запросы GET. Такого рода операции службы определяются как методы, к которым применен атрибут <xref:System.ServiceModel.Web.WebGetAttribute>. Дополнительные сведения см. в разделе [операции службы](service-operations-wcf-data-services.md).  
  
 Операции службы предоставляются в метаданных, возвращаемых службой данных, которая реализует OData. В метаданных операции службы представлены как элементы `FunctionImport`. При создании строго типизированного элемента <xref:System.Data.Services.Client.DataServiceContext> средства Add Service Reference и DataSvcUtil.exe его не учитывают. Вследствие этого нельзя найти метод в контексте, который может быть использован для прямого вызова операции службы. Однако вы по-прежнему можете использовать клиент WCF Data Services для вызова операций службы одним из следующих двух способов:  
  
- Вызов метода <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> на <xref:System.Data.Services.Client.DataServiceContext> с передачей URI операции службы вместе с любыми параметрами. Этот метод используется для вызова любой операции службы GET.  
  
- С помощью метода <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> применительно к <xref:System.Data.Services.Client.DataServiceContext> можно создать объект <xref:System.Data.Services.Client.DataServiceQuery%601>. При вызове метода <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> имя операции службы указывается в параметре `entitySetName`. Этот метод возвращает объект <xref:System.Data.Services.Client.DataServiceQuery%601>, который вызывает операцию службы при перечислении или вызове метода <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A>. Этот метод используется для вызова операций службы GET, которые возвращают коллекцию. Можно указать один параметр с помощью метода <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. Объект <xref:System.Data.Services.Client.DataServiceQuery%601>, возвращаемый этим методом, можно затем использовать как любой объект запроса. Дополнительные сведения см. [в разделе запросы к службе данных](querying-the-data-service-wcf-data-services.md).  
  
## <a name="considerations-for-calling-service-operations"></a>Рассмотрение вызова операций службы  
 Следующие рекомендации относятся к использованию клиента WCF Data Services для вызова операций службы.  
  
- При асинхронном обращении к службе данных необходимо использовать эквивалентные методы асинхронного <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A>/<xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> в <xref:System.Data.Services.Client.DataServiceContext> или <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>методы /<xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> в <xref:System.Data.Services.Client.DataServiceQuery%601>.  
  
- Клиентская библиотека WCF Data Services не может материализовать результаты операции службы, возвращающей коллекцию типов-примитивов.  
  
- Клиентская библиотека WCF Data Services не поддерживает вызов операций после службы. Операции службы, которые вызываются запросом HTTP POST, определяются с использованием <xref:System.ServiceModel.Web.WebInvokeAttribute> с параметром `Method="POST"`. Для вызова операции службы с использованием запроса HTTP POST необходимо использовать <xref:System.Net.HttpWebRequest>.  
  
- Нельзя использовать <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> для вызова операции службы GET, которая возвращает единственный результат, представляющий собой сущность или простой тип, или операции, которой требуется несколько входных параметров. Вместо этого необходимо вызвать метод <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>.  
  
- Рассмотрите возможность создания метода расширения на строго типизированном разделяемом классе <xref:System.Data.Services.Client.DataServiceContext>, который создается этими средствами и использует метод <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> или <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> для вызова операции службы. Это позволяет вызывать операции службы непосредственно из контекста. Дополнительные сведения см. в записи блога, посвященной [операциям службы и клиенту WCF Data Services](https://blogs.msdn.microsoft.com/astoriateam/2010/05/26/service-operations-and-the-wcf-data-services-client/).  
  
- При использовании <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> для вызова операции службы клиентская библиотека автоматически преобразует символы, передаваемые в <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>, с помощью процента кодирования зарезервированных символов, таких как амперсанд (&), и экранирование одинарных кавычек в строках. Однако при вызове одного из методов *EXECUTE* для вызова операции службы необходимо помнить, что это экранирование любых переданных пользователем строковых значений. Одиночные кавычки в URI-адресах экранируются как пары одиночных кавычек.  
  
## <a name="examples-of-calling-service-operations"></a>Примеры вызова операций службы  
 В этом разделе содержатся следующие примеры вызова операций службы с помощью клиентской библиотеки WCF Data Services.  
  
- [Вызов EXECUTE&lt;T&gt; для возврата коллекции сущностей](calling-service-operations-wcf-data-services.md#ExecuteIQueryable)  
  
- [Использование CreateQuery&lt;T&gt; для возврата коллекции сущностей](calling-service-operations-wcf-data-services.md#CreateQueryIQueryable)  
  
- [Вызов EXECUTE&lt;T&gt; для возврата одной сущности](calling-service-operations-wcf-data-services.md#ExecuteSingleEntity)  
  
- [Вызов EXECUTE&lt;T&gt; для возврата коллекции примитивных значений](calling-service-operations-wcf-data-services.md#ExecutePrimitiveCollection)  
  
- [Вызов EXECUTE&lt;T&gt; для возврата одного примитивного значения](calling-service-operations-wcf-data-services.md#ExecutePrimitiveValue)  
  
- [Вызов операции службы, не возвращающей данные](calling-service-operations-wcf-data-services.md#ExecuteVoid)  
  
- [Асинхронный вызов операции службы](calling-service-operations-wcf-data-services.md#ExecuteAsync)  
  
<a name="ExecuteIQueryable"></a>   
### <a name="calling-executet-to-return-a-collection-of-entities"></a>Вызов EXECUTE\<T > для возврата коллекции сущностей  
 В следующем примере вызывается операция службы с именем GetOrdersByCity, которая принимает строковый параметр `city` и возвращает <xref:System.Linq.IQueryable%601>.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationiqueryable)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationiqueryable)]  
  
 В этом примере операция службы возвращает коллекцию объектов `Order` со связанными объектами `Order_Detail`.  
  
<a name="CreateQueryIQueryable"></a>   
### <a name="using-createqueryt-to-return-a-collection-of-entities"></a>Использование CreateQuery\<T > для возврата коллекции сущностей  
 В следующем примере метод <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> используется для возврата объекта <xref:System.Data.Services.Client.DataServiceQuery%601>, который используется для вызова той же операции службы GetOrdersByCity.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationcreatequery)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationcreatequery)]  
  
 В этом примере метод <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> используется для добавления параметра к запросу, а метод <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> — для включения в результаты связанных объектов Order_Details.  
  
<a name="ExecuteSingleEntity"></a>   
### <a name="calling-executet-to-return-a-single-entity"></a>Вызов EXECUTE\<T > для возврата одной сущности  
 В следующем примере вызывается операция службы с именем GetNewestOrder, которая возвращает одну сущность Order.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleentity)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleentity)]  
  
 В этом примере метод <xref:System.Linq.Enumerable.FirstOrDefault%2A> используется для запроса только одной сущности Order при исполнении.  
  
<a name="ExecutePrimitiveCollection"></a>   
### <a name="calling-executet-to-return-a-collection-of-primitive-values"></a>Вызов EXECUTE\<T > для возврата коллекции примитивных значений  
 В следующем примере вызывается операция службы, которая возвращает коллекцию строковых значений.  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationEnumString](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationenumstring)]  
  
<a name="ExecutePrimitiveValue"></a>   
### <a name="calling-executet-to-return-a-single-primitive-value"></a>Вызов EXECUTE\<T > для возврата одного примитивного значения  
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
  
## <a name="see-also"></a>См. также:

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
