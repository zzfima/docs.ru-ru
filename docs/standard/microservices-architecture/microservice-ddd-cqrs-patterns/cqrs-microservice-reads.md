---
title: Реализация операций чтения и запросов в микрослужбе CQRS
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация операций чтения и запросов в микрослужбе CQRS
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/02/2017
ms.openlocfilehash: 8eca01acc2308097d1684be8bdb0f07edd86832f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="39e65-103">Реализация операций чтения и запросов в микрослужбе CQRS</span><span class="sxs-lookup"><span data-stu-id="39e65-103">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="39e65-104">При выполнении операций чтения и запросов микрослужба заказов в примере приложения eShopOnContainers реализует запросы независимо от модели проблемно-ориентированного программирования (DDD) и области транзакций.</span><span class="sxs-lookup"><span data-stu-id="39e65-104">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="39e65-105">Это было сделано, главным образом, потому, что требования к запросам и транзакциям значительно отличаются.</span><span class="sxs-lookup"><span data-stu-id="39e65-105">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="39e65-106">Операции записи выполняют транзакции, которые должны соответствовать логике предметной области.</span><span class="sxs-lookup"><span data-stu-id="39e65-106">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="39e65-107">Запросы, с другой стороны, являются идемпотентными, их можно отделить от правил предметной области.</span><span class="sxs-lookup"><span data-stu-id="39e65-107">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="39e65-108">Это простой подход, как показано на рисунке 9-3.</span><span class="sxs-lookup"><span data-stu-id="39e65-108">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="39e65-109">API-интерфейс реализуется контроллерами веб-API с помощью любой инфраструктуры, например микро-ORM (средство объектно-реляционного отображения), такого как Dapper, и возвращения динамических ViewModel, в зависимости от потребностей приложения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="39e65-109">The API interface is implemented by the Web API controllers using any infrastructure, such as a micro Object Relational Mapper (ORM) like Dapper, and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="39e65-110">**Рис. 9-3**.</span><span class="sxs-lookup"><span data-stu-id="39e65-110">**Figure 9-3**.</span></span> <span data-ttu-id="39e65-111">Самый простой метод запросов в микрослужбе CQRS</span><span class="sxs-lookup"><span data-stu-id="39e65-111">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="39e65-112">Это простейший метод запросов.</span><span class="sxs-lookup"><span data-stu-id="39e65-112">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="39e65-113">Определения запроса обращаются к базе данных и возвращают динамическую ViewModel, которая создается в режиме реального времени для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="39e65-113">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="39e65-114">Поскольку запросы идемпотентны, они не меняют данные, сколько бы раз вы ни выполняли запрос.</span><span class="sxs-lookup"><span data-stu-id="39e65-114">Since the queries are idempotent, they won't change the data no matter how many times you run a query.</span></span> <span data-ttu-id="39e65-115">Значит, вам не нужно ограничиваться шаблоном DDD, используемым на стороне транзакций, например статистическими выражениями и другими шаблонами. Поэтому запросы отделены от области транзакций.</span><span class="sxs-lookup"><span data-stu-id="39e65-115">Therefore, you don't need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="39e65-116">Вы просто запрашиваете у базы данных данные, необходимые для пользовательского интерфейса, и получаете динамические ViewModel, которые не должны быть статически определены нигде (для ViewModel нет классов), кроме самих инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="39e65-116">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="39e65-117">Это простой подход, поэтому код на стороне запросов (например, код, использующий микро-ORM, вроде [Dapper](https://github.com/StackExchange/Dapper)) можно реализовать [в том же проекте веб-API](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="39e65-117">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="39e65-118">Это показано на рис. 9-4.</span><span class="sxs-lookup"><span data-stu-id="39e65-118">Figure 9-4 shows this.</span></span> <span data-ttu-id="39e65-119">Запросы определяются в проекте микрослужбы **Ordering.API** в решении eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="39e65-119">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="39e65-120">**Рис. 9-4**.</span><span class="sxs-lookup"><span data-stu-id="39e65-120">**Figure 9-4**.</span></span> <span data-ttu-id="39e65-121">Запросы в микрослужбе заказов в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="39e65-121">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="39e65-122">Использование ViewModel, специально созданных для клиентских приложений, независимо от ограничений модели предметной области</span><span class="sxs-lookup"><span data-stu-id="39e65-122">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="39e65-123">Поскольку запросы выполняются для получения данных, необходимых клиентским приложениям, можно создать тип возвращаемого значения специально для клиентов на основе данных, возвращаемых запросами.</span><span class="sxs-lookup"><span data-stu-id="39e65-123">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="39e65-124">Эти модели, или объекты передачи данных (DTO), называются ViewModel.</span><span class="sxs-lookup"><span data-stu-id="39e65-124">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="39e65-125">Возвращаемые данные (ViewModel) могут быть результатом объединения данных из нескольких сущностей или таблиц в базе данных или даже нескольких статистических выражений, определенных в модели предметной области для области транзакций.</span><span class="sxs-lookup"><span data-stu-id="39e65-125">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="39e65-126">В этом случае, поскольку вы создаете запросы независимо от модели предметной области, границы и ограничения статистических выражений полностью игнорируются, и вы можете обратиться к любой нужной таблице или столбцу.</span><span class="sxs-lookup"><span data-stu-id="39e65-126">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you're free to query any table and column you might need.</span></span> <span data-ttu-id="39e65-127">Такой подход обеспечивает большую гибкость и производительность для разработчиков, создающих или обновляющих запросы.</span><span class="sxs-lookup"><span data-stu-id="39e65-127">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="39e65-128">Модели ViewModel могут быть статичными и определенными в классах.</span><span class="sxs-lookup"><span data-stu-id="39e65-128">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="39e65-129">Или они могут создаваться динамически на основании запросов (как реализовано в микрослужбе заказов), что очень удобно для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="39e65-129">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="39e65-130">Использование Dapper в качестве микро-ORM для выполнения запросов</span><span class="sxs-lookup"><span data-stu-id="39e65-130">Using Dapper as a micro ORM to perform queries</span></span>

<span data-ttu-id="39e65-131">Для запросов вы можете использовать любой микро-ORM, Entity Framework Core или даже просто ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="39e65-131">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="39e65-132">В примере приложения eShopOnContainers Dapper выбран для микрослужбы заказов как хороший пример популярного микро-ORM.</span><span class="sxs-lookup"><span data-stu-id="39e65-132">In the sample application, Dapper was selected for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="39e65-133">Он может выполнять обычные SQL-запросы с высокой производительностью, так как это очень легкая платформа.</span><span class="sxs-lookup"><span data-stu-id="39e65-133">It can run plain SQL queries with great performance, because it's a very light framework.</span></span> <span data-ttu-id="39e65-134">С помощью Dapper вы можете написать SQL-запрос, который обратится к нескольким таблицам и соединит их.</span><span class="sxs-lookup"><span data-stu-id="39e65-134">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="39e65-135">Dapper — это проект с открытым кодом (изначально созданный Сэмом Сэффроном), который является частью стандартных блоков, используемых в [Stack Overflow](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="39e65-135">Dapper is an open-source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="39e65-136">Чтобы использовать Dapper, просто установите его с помощью [пакета Dapper NuGet](https://www.nuget.org/packages/Dapper), как показано на рисунке:</span><span class="sxs-lookup"><span data-stu-id="39e65-136">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure:</span></span>

![](./media/image4.1.png)

<span data-ttu-id="39e65-137">Затем добавьте оператор using, чтобы у кода был доступ к методам расширения Dapper.</span><span class="sxs-lookup"><span data-stu-id="39e65-137">You also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="39e65-138">При добавлении Dapper в код вы напрямую используете класс <xref:System.Data.SqlClient.SqlConnection>, доступный в пространстве имен <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="39e65-138">When you use Dapper in your code, you directly use the <xref:System.Data.SqlClient.SqlConnection> class available in the <xref:System.Data.SqlClient> namespace.</span></span> <span data-ttu-id="39e65-139">Метод QueryAsync и другие методы расширения, которые расширяют класс <xref:System.Data.SqlClient.SqlConnection>, — это прямой и эффективный способ выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="39e65-139">Through the QueryAsync method and other extension methods that extend the <xref:System.Data.SqlClient.SqlConnection> class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-versus-static-viewmodels"></a><span data-ttu-id="39e65-140">Динамические и статические модели ViewModel</span><span class="sxs-lookup"><span data-stu-id="39e65-140">Dynamic versus static ViewModels</span></span>

<span data-ttu-id="39e65-141">Когда модели ViewModel возвращаются с сервера в клиентские приложения, их можно представить себе в виде объектов передачи данных, которые могут отличаться для внутренних сущностей предметной области в вашей модели сущностей, поскольку модели ViewModel хранят данные так, как это необходимо клиентскому приложению.</span><span class="sxs-lookup"><span data-stu-id="39e65-141">When returning ViewModels from the server-side to client apps, you can think about those ViewModels as DTOs that can be different to the internal domain entities of your entity model because the ViewModels hold the data the way the client app needs.</span></span> <span data-ttu-id="39e65-142">Поэтому во многих случаях вы можете объединять данные из нескольких сущностей предметной области и составлять модели ViewModel в точном соответствии с требованиями клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="39e65-142">Therefore, in many cases, you can aggregate data coming from multiple domain entities and compose the ViewModels precisely according to how the client app needs that data.</span></span>

<span data-ttu-id="39e65-143">Эти ViewModel или объекты передачи данных можно явно определить (как классы держателей данных), как класс [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs), показанный во фрагменте кода далее, или можно просто вернуть динамические ViewModel или динамические объекты передачи данных на основе атрибутов, возвращенных вашими запросами, как тип `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="39e65-143">Those ViewModels or DTOs can be defined explicitly (as data holder classes) like the [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs) class shown in a later code snippet, or you could just return dynamic ViewModels or dynamic DTOs simply based on the attributes returned by your queries, as a `dynamic` type.</span></span>

### <a name="viewmodel-as-dynamic-type"></a><span data-ttu-id="39e65-144">ViewModel как динамический тип</span><span class="sxs-lookup"><span data-stu-id="39e65-144">ViewModel as dynamic type</span></span>

<span data-ttu-id="39e65-145">Как показано в следующем коде, ViewModel можно получить напрямую с помощью запросов, вернув динамический тип, который внутренне основан на атрибутах, возвращенных запросом.</span><span class="sxs-lookup"><span data-stu-id="39e65-145">As shown in the following code, a ViewModel can be directly returned by the queries by returning a dynamic type that internally is based on the attributes returned by a query.</span></span> <span data-ttu-id="39e65-146">Это означает, что подмножество атрибутов, которое будет возвращено, основано на самом запросе.</span><span class="sxs-lookup"><span data-stu-id="39e65-146">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="39e65-147">Поэтому, если вы добавляете в запрос или соединение новый столбец, данные динамически добавляются к возвращаемой ViewModel.</span><span class="sxs-lookup"><span data-stu-id="39e65-147">Therefore, if you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
@"SELECT o.[Id] as ordernumber,
o.[OrderDate] as [date],os.[Name] as [status],
SUM(oi.units*oi.unitprice) as total
FROM [ordering].[Orders] o
LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
    }
}
```

<span data-ttu-id="39e65-148">Важно отметить, что при использовании динамического типа возвращенная коллекция данных динамически собирается в виде ViewModel.</span><span class="sxs-lookup"><span data-stu-id="39e65-148">The important point is that by using a dynamic type, the returned collection of data is dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="39e65-149">*Преимущества:* при этом подходе можно реже менять статические классы ViewModel при обновлении SQL-предложения запроса, что очень удобно при написании кода. Это простой метод, позволяющий быстро приспособиться в случае изменений в будущем.</span><span class="sxs-lookup"><span data-stu-id="39e65-149">*Pros:* This approach reduces the need to modify static ViewModel classes whenever you update the SQL sentence of a query, making this design approach pretty agile when coding, straightforward, and quick to evolve in regard to future changes.</span></span>

<span data-ttu-id="39e65-150">*Недостатки:* в долгосрочной перспективе динамические типы могут негативно отразиться на ясности и повлиять на совместимость службы с клиентскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="39e65-150">*Cons:* In the long term, dynamic types can impact negatively the clarity and impact the compatibility of a service with client apps.</span></span> <span data-ttu-id="39e65-151">Кроме того, ПО промежуточного слоя, например Swagger, не может предоставить тот же уровень документации для типов возвращаемого значения, если вы используете динамические типы.</span><span class="sxs-lookup"><span data-stu-id="39e65-151">In addition, middleware software like Swagger cannot provide the same level of documentation on returned types if using dynamic types.</span></span>

### <a name="viewmodel-as-predefined-dto-classes"></a><span data-ttu-id="39e65-152">ViewModel как предопределенные классы объектов передачи данных</span><span class="sxs-lookup"><span data-stu-id="39e65-152">ViewModel as predefined DTO classes</span></span>

<span data-ttu-id="39e65-153">*Преимущества:* предопределенные статические классы ViewModel, например "контракты" на основе явных классов объектов передачи данных, лучше подходят для общедоступных API, а также для долгосрочных микрослужб, даже если они используются только в том же самом приложении.</span><span class="sxs-lookup"><span data-stu-id="39e65-153">*Pros:* Having static predefined ViewModel classes, like "contracts" based on explicit DTO classes, is definitely better for public APIs but also for long term microservices, even if they are only used by the same application.</span></span>

<span data-ttu-id="39e65-154">Если вы хотите указать типы ответов для Swagger, необходимо использовать явные классы объектов передачи данных в качестве типа возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="39e65-154">If you want to specify response types for swagger, you need to use explicit DTO classes as the return type.</span></span> <span data-ttu-id="39e65-155">Таким образом, с помощью предопределенных классов объектов передачи данных вы сможете получить больше сведений из Swagger.</span><span class="sxs-lookup"><span data-stu-id="39e65-155">Therefore, predefined DTO classes allow you to offer richer information from Swagger.</span></span> <span data-ttu-id="39e65-156">Так вы сможете улучшить документацию по API и совместимость при использовании API.</span><span class="sxs-lookup"><span data-stu-id="39e65-156">That improves the API documentation and compatibility when consuming an API.</span></span>

<span data-ttu-id="39e65-157">*Недостатки:* как уже упоминалось, при обновлении кода будет сложнее обновить классы объектов передачи данных.</span><span class="sxs-lookup"><span data-stu-id="39e65-157">*Cons:* As mentioned earlier, when updating the code, it takes some more steps to update the DTO classes.</span></span>

<span data-ttu-id="39e65-158">*Совет, основанный на нашем опыте:* в запросах, реализованных микрослужбой заказов в eShopOnContainers, мы начали разработку, используя динамические ViewModel, поскольку это очень удобно на ранних этапах разработки.</span><span class="sxs-lookup"><span data-stu-id="39e65-158">*Tip based on our experience:* In the queries implemented at the Ordering microservice in eShopOnContainers, we started developing by using dynamic ViewModels as it was very straightforward and agile on the early development stages.</span></span> <span data-ttu-id="39e65-159">Но после стабилизации разработки мы выполнили рефакторинг API и использовали статические, или предопределенные, объекты передачи данных для ViewModel, поскольку микрослужбам удобнее знать явные типы объектов передачи данных и использовать их как "контракты".</span><span class="sxs-lookup"><span data-stu-id="39e65-159">But, once the development was stabilized, we chose to refactor the APIs and use static or pre-defined DTOs for the ViewModels, because it is clearer for the microservice’s consumers to know explicit DTO types, used as "contracts".</span></span>

<span data-ttu-id="39e65-160">В следующем примере показано, как запрос возвращает данные с помощью явного класса объекта передачи данных ViewModel: класса OrderSummary.</span><span class="sxs-lookup"><span data-stu-id="39e65-160">In the following example, you can see how the query is returning data by using an explicit ViewModel DTO class: the OrderSummary class.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            var result = await connection.QueryAsync<dynamic>(
                  @"SELECT o.[Id] as ordernumber, 
                  o.[OrderDate] as [date],os.[Name] as [status], 
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid 
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    } 
}
```

#### <a name="describing-response-types-of-web-apis"></a><span data-ttu-id="39e65-161">Описания типов ответов веб-API</span><span class="sxs-lookup"><span data-stu-id="39e65-161">Describing response types of Web APIs</span></span>

<span data-ttu-id="39e65-162">Разработчиков, использующих веб-API и микрослужбы, в первую очередь волнуют возвращаемые данные, а именно — типы ответов и коды ошибок (если они не стандартны).</span><span class="sxs-lookup"><span data-stu-id="39e65-162">Developers consuming web APIs and microservices are most concerned with what is returned — specifically response types and error codes (if not standard).</span></span> <span data-ttu-id="39e65-163">Все это указывается в XML-комментарии и заметках к данным.</span><span class="sxs-lookup"><span data-stu-id="39e65-163">These are handled in the XML comments and data annotations.</span></span>

<span data-ttu-id="39e65-164">Без правильной документации в пользовательском интерфейсе Swagger потребителю не хватает знаний о том, какой тип значений возвращается или что могут вернуть HTTP-коды.</span><span class="sxs-lookup"><span data-stu-id="39e65-164">Without proper documentation in the Swagger UI, the consumer lacks knowledge of what types are being returned or what HTTP codes can be returned.</span></span> <span data-ttu-id="39e65-165">Проблему можно решить, если добавить <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, чтобы Swagger создал больше информации о модели возврата и возвращенных значениях API, как в примере кода:</span><span class="sxs-lookup"><span data-stu-id="39e65-165">That problem is fixed by adding the <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, so Swagger can generate richer information about the API return model and values, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
       //Additional code...
       [Route("")]
       [HttpGet]
       [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
                             (int)HttpStatusCode.OK)]
       public async Task<IActionResult> GetOrders()
       {
           var orderTask = _orderQueries.GetOrdersAsync();
           var orders = await orderTask;
           return Ok(orders);
        }
    }
}
```

<span data-ttu-id="39e65-166">Однако атрибут `ProducesResponseType` не может использовать динамический тип. Он требует явный тип, как объект передачи данных ViewModel `OrderSummary`, показанный в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="39e65-166">However, the `ProducesResponseType` attribute cannot use dynamic as a type but requires to use explicit types, like the `OrderSummary` ViewModel DTO, shown in the following example:</span></span>

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

<span data-ttu-id="39e65-167">Это еще одна причина, по которой явные типы возвращаемого значения лучше динамических в долгосрочной перспективе.</span><span class="sxs-lookup"><span data-stu-id="39e65-167">This is another reason why explicit returned types are better than dynamic types, in the long term.</span></span>
<span data-ttu-id="39e65-168">При использовании атрибута `ProducesResponseType` вы также можете указать ожидаемый результат в отношении возможных ошибок и кодов HTTP, например 200, 400 и т. д.</span><span class="sxs-lookup"><span data-stu-id="39e65-168">When using the `ProducesResponseType` attribute, you can also specify what is the expected outcome in regards possible HTTP errors/codes, like 200,400, etc.</span></span>

<span data-ttu-id="39e65-169">На следующем рисунке показано, как пользовательский интерфейс Swagger отображает сведения ResponseType.</span><span class="sxs-lookup"><span data-stu-id="39e65-169">In the following image, you can see how Swagger UI shows the ResponseType information.</span></span>

![](./media/image5.png)

<span data-ttu-id="39e65-170">**Рис. 9-5**.</span><span class="sxs-lookup"><span data-stu-id="39e65-170">**Figure 9-5**.</span></span> <span data-ttu-id="39e65-171">Пользовательский интерфейс Swagger, отображающий типы ответов и возможные коды состояния HTTP в веб-API</span><span class="sxs-lookup"><span data-stu-id="39e65-171">Swagger UI showing response types and possible HTTP status codes from a Web API</span></span>

<span data-ttu-id="39e65-172">На рисунке выше показан пример значений на базе типов ViewModel и возможные коды состояния HTTP, которые могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="39e65-172">You can see in the image above some example values based on the ViewModel types plus the possible HTTP status codes that can be returned.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39e65-173">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="39e65-173">Additional resources</span></span>

-   <span data-ttu-id="39e65-174">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="39e65-174">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="39e65-175">**Julie Lerman (Джули Лерман). Доступ к данным — Dapper, Entity Framework и гибридные приложения (статья в журнале MSDN)**</span><span class="sxs-lookup"><span data-stu-id="39e65-175">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    *https://msdn.microsoft.com/magazine/mt703432.aspx*

-   <span data-ttu-id="39e65-176">**Страницы справки по веб-API ASP.NET Core с использованием Swagger**</span><span class="sxs-lookup"><span data-stu-id="39e65-176">**ASP.NET Core Web API Help Pages using Swagger**</span></span>

    *https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio*

>[!div class="step-by-step"]
<span data-ttu-id="39e65-177">[Назад] (eshoponcontainers-cqrs-ddd-microservice.md) [Далее] (ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="39e65-177">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
