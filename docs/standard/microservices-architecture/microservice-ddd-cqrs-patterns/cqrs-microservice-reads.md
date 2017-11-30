---
title: "Реализация операции чтения и запросы в микрослужбу CQRS"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация операции чтения и запросы в микрослужбу CQRS"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e017aaaa701d8033110be8d6244d3e1120fc4fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="7f4d1-104">Реализация операции чтения и запросы в микрослужбу CQRS</span><span class="sxs-lookup"><span data-stu-id="7f4d1-104">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="7f4d1-105">Для операций чтения и запросы упорядочивания микрослужбу из приложения ссылку eShopOnContainers реализует запросы независимо от модели DDD и область транзакций.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-105">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="7f4d1-106">Это было сделано потому, что требования для запросов и транзакций, значительно отличаются.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-106">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="7f4d1-107">Записывает выполнение операций, которые должны быть совместимыми с логикой домена.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-107">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="7f4d1-108">Запросы, с другой стороны, являются идемпотентными и могут быть выделены из правил домена.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-108">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="7f4d1-109">Этот подход является простым, как показано на рисунке 9-3.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-109">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="7f4d1-110">API-интерфейса реализуется контроллеров веб-API, с помощью любой инфраструктуры (например, micro ORM, например Dapper) и возврат динамического ViewModels в зависимости от потребностей приложения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-110">The API interface is implemented by the Web API controllers using any infrastructure (such as a micro ORM like Dapper) and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="7f4d1-111">**Рис. 9-3**.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-111">**Figure 9-3**.</span></span> <span data-ttu-id="7f4d1-112">Самый простой способ для запросов в микрослужбу CQRS</span><span class="sxs-lookup"><span data-stu-id="7f4d1-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="7f4d1-113">Это простейший возможный подход для запросов.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-113">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="7f4d1-114">Определения запросов запроса к базе данных и возвращают динамические ViewModel построен в режиме реального времени для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="7f4d1-115">Поскольку запросы должны быть идемпотентными, они не изменит данные независимо от того, сколько раз выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-115">Since the queries are idempotent, they will not change the data no matter how many times you run a query.</span></span> <span data-ttu-id="7f4d1-116">Таким образом необходимо ограничить шаблоном ддд, используемые на стороне транзакций, например статистические функции и другие шаблоны, и поэтому запросы отделены от области транзакций.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-116">Therefore, you do not need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="7f4d1-117">Вы просто запрашивают данные, необходимые для пользовательского интерфейса в базе данных и возвращают динамические ViewModel, не должен быть статически, определенных в любом месте (без классы ViewModels) за исключением в сами инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="7f4d1-118">Так как это простой подход, требуется код на стороне запросов (например, код, с помощью micro, ORM, например [Dapper](https://github.com/StackExchange/Dapper)) можно реализовать [в том же проекте веб-API](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="7f4d1-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="7f4d1-119">Это показано на рис. 9-4.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-119">Figure 9-4 shows this.</span></span> <span data-ttu-id="7f4d1-120">Определенные запросы в **Ordering.API** микрослужбу проекта в решение eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="7f4d1-121">**Рис. 9-4**.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-121">**Figure 9-4**.</span></span> <span data-ttu-id="7f4d1-122">Запросы в микрослужбу упорядочения элементов в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="7f4d1-122">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="7f4d1-123">С помощью ViewModels специально создана для клиентских приложений, независимо от ограничений модели домена</span><span class="sxs-lookup"><span data-stu-id="7f4d1-123">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="7f4d1-124">Поскольку запросы выполняются для получения данных, необходимых клиентских приложений, возвращаемый тип может быть специально создана для клиентов, на основе данных, возвращенных запросами.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-124">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="7f4d1-125">Эти модели или объекты передачи данных (DTO), называются ViewModels.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-125">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="7f4d1-126">Возвращаемые данные (ViewModel) может быть результатом объединения данных из нескольких сущностей или таблиц в базе данных или даже через несколько агрегатные функции, определенные в модели предметной области транзакций.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-126">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="7f4d1-127">Таким образом так как вы создаете запросы независимо от модели домена, статистические выражения границ и ограничения полностью игнорируются, и можно запрашивать любую таблицу и столбец, который может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-127">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you are free to query any table and column you might need.</span></span> <span data-ttu-id="7f4d1-128">Такой подход обеспечивает большую гибкость и производительность для разработчиков, создание или обновление запросов.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-128">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="7f4d1-129">ViewModels может быть статические типы, определенные в классах.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-129">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="7f4d1-130">Или они могут создаваться динамически на основании запросы, выполняемые (как реализована в микрослужбу порядка сортировки), который является очень гибкой для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-130">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="7f4d1-131">С помощью Dapper как micro ORM для выполнения запросов</span><span class="sxs-lookup"><span data-stu-id="7f4d1-131">Using Dapper as a micro ORM to perform queries</span></span> 

<span data-ttu-id="7f4d1-132">Можно использовать любой микро-ORM, Entity Framework Core или даже простой ADO.NET для выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-132">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="7f4d1-133">В примере приложения мы выбрали Dapper для упорядочивания микрослужбу в eShopOnContainers как хороший пример популярных micro ORM.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-133">In the sample application, we selected Dapper for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="7f4d1-134">Его можно запустить простой SQL-запросы с высокую производительность, так как это очень простой framework.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-134">It can run plain SQL queries with great performance, because it is a very light framework.</span></span> <span data-ttu-id="7f4d1-135">С помощью Dapper, можно написать SQL-запроса, можно открыть и соединения нескольких таблиц.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-135">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="7f4d1-136">Dapper проекта с открытым кодом (original созданные Сэм Сэффрон), который частью стандартных блоков, используемых в [переполнения стека](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="7f4d1-136">Dapper is an open source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="7f4d1-137">Чтобы использовать Dapper, вам следует установить его через [пакет Dapper NuGet](https://www.nuget.org/packages/Dapper), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-137">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure.</span></span>

![](./media/image5.png)

<span data-ttu-id="7f4d1-138">Также необходимо добавить с помощью инструкции, поэтому код имеет доступ к методам Dapper расширения.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-138">You will also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="7f4d1-139">При использовании Dapper в коде непосредственно используют класс SqlClient, доступны в пространстве имен System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-139">When you use Dapper in your code, you directly use the SqlClient class available in the System.Data.SqlClient namespace.</span></span> <span data-ttu-id="7f4d1-140">Через метод QueryAsync и другие методы расширения, которые расширяют класс SqlClient можно просто запустить запросы в простой и эффективный способ.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-140">Through the QueryAsync method and other extension methods which extend the SqlClient class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-and-static-viewmodels"></a><span data-ttu-id="7f4d1-141">Динамических и статических ViewModels</span><span class="sxs-lookup"><span data-stu-id="7f4d1-141">Dynamic and static ViewModels</span></span>

<span data-ttu-id="7f4d1-142">Как показано в следующем коде из упорядочивания микрослужбу большинство ViewModels, возвращенных запросами, реализуются как *динамическое*.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-142">As shown in the following code from the ordering microservice, most of the ViewModels returned by the queries are implemented as *dynamic*.</span></span> <span data-ttu-id="7f4d1-143">Это означает, что к подмножеству атрибутов должны быть возвращены зависит от самого запроса.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-143">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="7f4d1-144">При добавлении нового столбца на запрос или соединение, возвращенный ViewModel динамически добавляется этих данных.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-144">If you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span> <span data-ttu-id="7f4d1-145">Этот подход уменьшает необходимость изменения запросов в ответ на обновления для базовой модели данных, что этот подход более гибкими и нечувствительного к ошибкам будущих изменений.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-145">This approach reduces the need to modify queries in response to updates to the underlying data model, making this design approach more flexible and tolerant of future changes.</span></span>

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

<span data-ttu-id="7f4d1-146">Важно то, что с помощью динамический тип, возвращаемый набор данных будет динамически собирать как ViewModel.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-146">The important point is that by using a dynamic type, the returned collection of data will be dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="7f4d1-147">Для большинства запросов не нужно предварительно определять класс DTO или ViewModel, который упрощает написание кода, их проще и продуктивным.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-147">For most queries, you do not need to predefine a DTO or ViewModel class, which makes coding them straightforward and productive.</span></span> <span data-ttu-id="7f4d1-148">Тем не менее можно заранее определить ViewModels (например, стандартные DTO), если вы хотите иметь ViewModels с определением больше ограничений, как контракты.</span><span class="sxs-lookup"><span data-stu-id="7f4d1-148">However, you can predefine ViewModels (like predefined DTOs) if you want to have ViewModels with a more restricted definition as contracts.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="7f4d1-149">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="7f4d1-149">Additional resources</span></span>

-   <span data-ttu-id="7f4d1-150">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="7f4d1-150">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="7f4d1-151">**Джули Лерман. Точки данных — Dapper, Entity Framework и гибридные приложения (статья MSDN Mag.)**</span><span class="sxs-lookup"><span data-stu-id="7f4d1-151">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    <span data-ttu-id="7f4d1-152">*https://MSDN.Microsoft.com/en-US/Magazine/mt703432.aspx*</span><span class="sxs-lookup"><span data-stu-id="7f4d1-152">*https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7f4d1-153">[Предыдущие] (eshoponcontainers-cqrs ддд microservice.md) [Далее] (ddd ориентированного microservice.md)</span><span class="sxs-lookup"><span data-stu-id="7f4d1-153">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
