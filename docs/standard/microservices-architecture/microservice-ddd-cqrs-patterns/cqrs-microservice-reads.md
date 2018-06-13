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
ms.locfileid: "33579110"
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a>Реализация операций чтения и запросов в микрослужбе CQRS

При выполнении операций чтения и запросов микрослужба заказов в примере приложения eShopOnContainers реализует запросы независимо от модели проблемно-ориентированного программирования (DDD) и области транзакций. Это было сделано, главным образом, потому, что требования к запросам и транзакциям значительно отличаются. Операции записи выполняют транзакции, которые должны соответствовать логике предметной области. Запросы, с другой стороны, являются идемпотентными, их можно отделить от правил предметной области.

Это простой подход, как показано на рисунке 9-3. API-интерфейс реализуется контроллерами веб-API с помощью любой инфраструктуры, например микро-ORM (средство объектно-реляционного отображения), такого как Dapper, и возвращения динамических ViewModel, в зависимости от потребностей приложения пользовательского интерфейса.

![](./media/image3.png)

**Рис. 9-3**. Самый простой метод запросов в микрослужбе CQRS

Это простейший метод запросов. Определения запроса обращаются к базе данных и возвращают динамическую ViewModel, которая создается в режиме реального времени для каждого запроса. Поскольку запросы идемпотентны, они не меняют данные, сколько бы раз вы ни выполняли запрос. Значит, вам не нужно ограничиваться шаблоном DDD, используемым на стороне транзакций, например статистическими выражениями и другими шаблонами. Поэтому запросы отделены от области транзакций. Вы просто запрашиваете у базы данных данные, необходимые для пользовательского интерфейса, и получаете динамические ViewModel, которые не должны быть статически определены нигде (для ViewModel нет классов), кроме самих инструкций SQL.

Это простой подход, поэтому код на стороне запросов (например, код, использующий микро-ORM, вроде [Dapper](https://github.com/StackExchange/Dapper)) можно реализовать [в том же проекте веб-API](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs). Это показано на рис. 9-4. Запросы определяются в проекте микрослужбы **Ordering.API** в решении eShopOnContainers.

![](./media/image4.png)

**Рис. 9-4**. Запросы в микрослужбе заказов в eShopOnContainers

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Использование ViewModel, специально созданных для клиентских приложений, независимо от ограничений модели предметной области

Поскольку запросы выполняются для получения данных, необходимых клиентским приложениям, можно создать тип возвращаемого значения специально для клиентов на основе данных, возвращаемых запросами. Эти модели, или объекты передачи данных (DTO), называются ViewModel.

Возвращаемые данные (ViewModel) могут быть результатом объединения данных из нескольких сущностей или таблиц в базе данных или даже нескольких статистических выражений, определенных в модели предметной области для области транзакций. В этом случае, поскольку вы создаете запросы независимо от модели предметной области, границы и ограничения статистических выражений полностью игнорируются, и вы можете обратиться к любой нужной таблице или столбцу. Такой подход обеспечивает большую гибкость и производительность для разработчиков, создающих или обновляющих запросы.

Модели ViewModel могут быть статичными и определенными в классах. Или они могут создаваться динамически на основании запросов (как реализовано в микрослужбе заказов), что очень удобно для разработчиков.

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a>Использование Dapper в качестве микро-ORM для выполнения запросов

Для запросов вы можете использовать любой микро-ORM, Entity Framework Core или даже просто ADO.NET. В примере приложения eShopOnContainers Dapper выбран для микрослужбы заказов как хороший пример популярного микро-ORM. Он может выполнять обычные SQL-запросы с высокой производительностью, так как это очень легкая платформа. С помощью Dapper вы можете написать SQL-запрос, который обратится к нескольким таблицам и соединит их.

Dapper — это проект с открытым кодом (изначально созданный Сэмом Сэффроном), который является частью стандартных блоков, используемых в [Stack Overflow](https://stackoverflow.com/). Чтобы использовать Dapper, просто установите его с помощью [пакета Dapper NuGet](https://www.nuget.org/packages/Dapper), как показано на рисунке:

![](./media/image4.1.png)

Затем добавьте оператор using, чтобы у кода был доступ к методам расширения Dapper.

При добавлении Dapper в код вы напрямую используете класс <xref:System.Data.SqlClient.SqlConnection>, доступный в пространстве имен <xref:System.Data.SqlClient>. Метод QueryAsync и другие методы расширения, которые расширяют класс <xref:System.Data.SqlClient.SqlConnection>, — это прямой и эффективный способ выполнения запросов.

## <a name="dynamic-versus-static-viewmodels"></a>Динамические и статические модели ViewModel

Когда модели ViewModel возвращаются с сервера в клиентские приложения, их можно представить себе в виде объектов передачи данных, которые могут отличаться для внутренних сущностей предметной области в вашей модели сущностей, поскольку модели ViewModel хранят данные так, как это необходимо клиентскому приложению. Поэтому во многих случаях вы можете объединять данные из нескольких сущностей предметной области и составлять модели ViewModel в точном соответствии с требованиями клиентского приложения.

Эти ViewModel или объекты передачи данных можно явно определить (как классы держателей данных), как класс [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs), показанный во фрагменте кода далее, или можно просто вернуть динамические ViewModel или динамические объекты передачи данных на основе атрибутов, возвращенных вашими запросами, как тип `dynamic`.

### <a name="viewmodel-as-dynamic-type"></a>ViewModel как динамический тип

Как показано в следующем коде, ViewModel можно получить напрямую с помощью запросов, вернув динамический тип, который внутренне основан на атрибутах, возвращенных запросом. Это означает, что подмножество атрибутов, которое будет возвращено, основано на самом запросе. Поэтому, если вы добавляете в запрос или соединение новый столбец, данные динамически добавляются к возвращаемой ViewModel.

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

Важно отметить, что при использовании динамического типа возвращенная коллекция данных динамически собирается в виде ViewModel.

*Преимущества:* при этом подходе можно реже менять статические классы ViewModel при обновлении SQL-предложения запроса, что очень удобно при написании кода. Это простой метод, позволяющий быстро приспособиться в случае изменений в будущем.

*Недостатки:* в долгосрочной перспективе динамические типы могут негативно отразиться на ясности и повлиять на совместимость службы с клиентскими приложениями. Кроме того, ПО промежуточного слоя, например Swagger, не может предоставить тот же уровень документации для типов возвращаемого значения, если вы используете динамические типы.

### <a name="viewmodel-as-predefined-dto-classes"></a>ViewModel как предопределенные классы объектов передачи данных

*Преимущества:* предопределенные статические классы ViewModel, например "контракты" на основе явных классов объектов передачи данных, лучше подходят для общедоступных API, а также для долгосрочных микрослужб, даже если они используются только в том же самом приложении.

Если вы хотите указать типы ответов для Swagger, необходимо использовать явные классы объектов передачи данных в качестве типа возвращаемого значения. Таким образом, с помощью предопределенных классов объектов передачи данных вы сможете получить больше сведений из Swagger. Так вы сможете улучшить документацию по API и совместимость при использовании API.

*Недостатки:* как уже упоминалось, при обновлении кода будет сложнее обновить классы объектов передачи данных.

*Совет, основанный на нашем опыте:* в запросах, реализованных микрослужбой заказов в eShopOnContainers, мы начали разработку, используя динамические ViewModel, поскольку это очень удобно на ранних этапах разработки. Но после стабилизации разработки мы выполнили рефакторинг API и использовали статические, или предопределенные, объекты передачи данных для ViewModel, поскольку микрослужбам удобнее знать явные типы объектов передачи данных и использовать их как "контракты".

В следующем примере показано, как запрос возвращает данные с помощью явного класса объекта передачи данных ViewModel: класса OrderSummary.

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

#### <a name="describing-response-types-of-web-apis"></a>Описания типов ответов веб-API

Разработчиков, использующих веб-API и микрослужбы, в первую очередь волнуют возвращаемые данные, а именно — типы ответов и коды ошибок (если они не стандартны). Все это указывается в XML-комментарии и заметках к данным.

Без правильной документации в пользовательском интерфейсе Swagger потребителю не хватает знаний о том, какой тип значений возвращается или что могут вернуть HTTP-коды. Проблему можно решить, если добавить <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, чтобы Swagger создал больше информации о модели возврата и возвращенных значениях API, как в примере кода:

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

Однако атрибут `ProducesResponseType` не может использовать динамический тип. Он требует явный тип, как объект передачи данных ViewModel `OrderSummary`, показанный в следующем примере:

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

Это еще одна причина, по которой явные типы возвращаемого значения лучше динамических в долгосрочной перспективе.
При использовании атрибута `ProducesResponseType` вы также можете указать ожидаемый результат в отношении возможных ошибок и кодов HTTP, например 200, 400 и т. д.

На следующем рисунке показано, как пользовательский интерфейс Swagger отображает сведения ResponseType.

![](./media/image5.png)

**Рис. 9-5**. Пользовательский интерфейс Swagger, отображающий типы ответов и возможные коды состояния HTTP в веб-API

На рисунке выше показан пример значений на базе типов ViewModel и возможные коды состояния HTTP, которые могут быть возвращены.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)

-   **Julie Lerman (Джули Лерман). Доступ к данным — Dapper, Entity Framework и гибридные приложения (статья в журнале MSDN)**

    *https://msdn.microsoft.com/magazine/mt703432.aspx*

-   **Страницы справки по веб-API ASP.NET Core с использованием Swagger**

    *https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio*

>[!div class="step-by-step"]
[Назад] (eshoponcontainers-cqrs-ddd-microservice.md) [Далее] (ddd-oriented-microservice.md)
