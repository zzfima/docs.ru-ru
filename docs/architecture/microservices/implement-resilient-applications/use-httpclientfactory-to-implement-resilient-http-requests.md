---
title: Использование IHttpClientFactory для реализации устойчивых HTTP-запросов
description: Узнайте, как использовать интерфейс IHttpClientFactory, доступный в .NET Core, начиная с версии 2.1, для создания экземпляров `HttpClient`, чтобы облегчить их применение в ваших приложениях.
ms.date: 03/03/2020
ms.openlocfilehash: 088fb6c7e10ad656247ee4065da5c13d383b2cf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847223"
---
# <a name="use-ihttpclientfactory-to-implement-resilient-http-requests"></a>Использование IHttpClientFactory для реализации устойчивых HTTP-запросов

<xref:System.Net.Http.IHttpClientFactory> — это контракт, который реализуется `DefaultHttpClientFactory` и доступен, начиная с версии .NET Core 2.1. С его помощью можно создавать экземпляры <xref:System.Net.Http.HttpClient>, которые используются в приложениях.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Проблемы с исходным классом HttpClient, доступным в .NET Core

Исходный и хорошо известный класс <xref:System.Net.Http.HttpClient> очень просто использовать, но иногда разработчики применяют его неправильно.

Этот класс реализует `IDisposable`, однако объявлять и создавать его экземпляры в инструкции `using` не рекомендуется, поскольку при удалении объекта `HttpClient` не происходит немедленное освобождение базового сокета, в результате чего со временем может возникнуть проблема _нехватки сокетов_. Дополнительные сведения об этой проблеме см. в [записи блога](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/), посвященной неправильному использованию HttpClient и нарушению стабильной работы программного обеспечения.

Таким образом, создается один экземпляр `HttpClient`, которые будет использоваться повторно на протяжении всего жизненного цикла приложения. Создание экземпляра класса `HttpClient` для каждого запроса будет сокращать количество доступных сокетов при больших нагрузках. В результате будут возникать ошибки `SocketException`. Возможные способы решения этой проблемы основаны на создании объекта `HttpClient` в виде класса-одиночки или статического класса, как описано в этой [статье Майкрософт об использовании HttpClient](../../../csharp/tutorials/console-webapiclient.md). Это может быть хорошим решением для консольных приложений, которые выполняются непродолжительное время несколько раз в день, а также их аналогов.

Кроме того, разработчики сталкиваются с проблемами при использовании общего экземпляра `HttpClient` в длительно выполняющихся процессах. Если экземпляр HttpClient создается в единичном виде или как статический объект, он не может обрабатывать изменения DNS, как описывается в этой [проблеме](https://github.com/dotnet/corefx/issues/11224) в репозитории GitHub dotnet/corefx.

Тем не менее эта проблема связана не с самим объектом `HttpClient`, а с [конструктором по умолчанию для HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient.-ctor?view=netcore-3.1#System_Net_Http_HttpClient__ctor), поскольку он создает новый конкретный экземпляр <xref:System.Net.Http.HttpMessageHandler>, который является источником описываемых выше проблем, связанных с *нехваткой сокетов* и изменениями DNS.

Чтобы решить указанные выше проблемы и обеспечить возможность управления экземплярами `HttpClient`, в .NET Core 2.1 был представлен интерфейс <xref:System.Net.Http.IHttpClientFactory>, который можно использовать для настройки и создания экземпляров `HttpClient` в приложении путем внедрения зависимостей. Также этот интерфейс предоставляет расширения для ПО промежуточного слоя на основе Polly, что позволяет использовать преимущества делегирования обработчиков в HttpClient.

[Polly](http://www.thepollyproject.org/) — это библиотека для обеспечения обработки временных сбоев, которая позволяет разработчикам повысить устойчивость своих приложений, используя некоторые стандартные политики более эффективным и потокобезопасным способом.

## <a name="benefits-of-using-ihttpclientfactory"></a>Преимущества использования IHttpClientFactory

В текущей реализации <xref:System.Net.Http.IHttpClientFactory> также реализуется <xref:System.Net.Http.IHttpMessageHandlerFactory> и предлагаются следующие преимущества.

- Центральное расположение для именования и настройки логических объектов `HttpClient`. Например, вы можете настроить клиент (агент службы), который предварительно настроен для доступа к определенной микрослужбе.
- Кодификация концепции исходящего ПО промежуточного слоя путем делегирования обработчиков в `HttpClient` и реализация ПО промежуточного слоя на основе Polly для использования политик устойчивости Polly.
- В `HttpClient` уже существует концепция делегирования обработчиков, которые можно связать друг с другом для исходящих HTTP-запросов. Вы можете регистрировать клиенты HTTP в фабрике, а также использовать обработчик Polly, чтобы использовать политики Polly для повторных попыток, размыкателя цепи и т. д.
- Управление временем существования <xref:System.Net.Http.HttpMessageHandler>, чтобы избежать упомянутых проблем, которые могут возникнуть при управлении временем существования `HttpClient` самостоятельно.

> [!TIP]
> Экземпляры `HttpClient`, внедряемые в виде зависимостей, можно безопасно удалять, поскольку связанный с ними обработчик `HttpMessageHandler` управляется фабрикой. В сущности, внедренные экземпляры `HttpClient` с точки зрения внедрения зависимостей имеют *ограниченную область действия*.

> [!NOTE]
> Реализация `IHttpClientFactory` (`DefaultHttpClientFactory`) тесно привязывается к реализации внедрения зависимостей в пакете NuGet `Microsoft.Extensions.DependencyInjection`. См. сведения об использовании других контейнеров внедрения зависимостей в этом [обсуждении GitHub](https://github.com/dotnet/extensions/issues/1345).

## <a name="multiple-ways-to-use-ihttpclientfactory"></a>Способы применения IHttpClientFactory

Есть несколько способов использования `IHttpClientFactory` в вашем приложении:

- Основное использование
- Использование именованных клиентов
- Использование типизированных клиентов
- Использование созданных клиентов

Для краткости в этом руководстве показан наиболее структурированный способ использования `IHttpClientFactory`, а именно — с помощью типизированных клиентов (шаблон агента службы). Все параметры описаны и перечислены в [этой статье](/aspnet/core/fundamentals/http-requests#consumption-patterns), посвященной использованию `IHttpClientFactory`.

## <a name="how-to-use-typed-clients-with-ihttpclientfactory"></a>Как использовать типизированные клиенты с IHttpClientFactory

Так что же такое типизированный клиент? Это просто объект `HttpClient`, предварительно настроенный для конкретной цели. Эта конфигурация может включать заданные значения, например базовый сервер, заголовки HTTP или величины времени ожидания.

На следующей схеме показано, как использовать типизированные клиенты с `IHttpClientFactory`.

![На схеме показано, как использовать типизированные клиенты с IHttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Рис. 8-4**. Использование `IHttpClientFactory` с классами типизированных клиентов.

На изображении выше `ClientService` (используется контроллером или в коде клиента) использует объект `HttpClient`, созданный зарегистрированной фабрикой `IHttpClientFactory`. Эта фабрика назначает `HttpMessageHandler` из пула объекту `HttpClient`. `HttpClient` можно настроить с помощью политик Polly при регистрации фабрики `IHttpClientFactory` в контейнере внедрения зависимостей, используя метод расширения <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*>.

Чтобы настроить такую структуру, добавьте <xref:System.Net.Http.IHttpClientFactory> в приложение, установив пакет NuGet `Microsoft.Extensions.Http`, который содержит метод расширения <xref:Microsoft.Extensions.DependencyInjection.HttpClientFactoryServiceCollectionExtensions.AddHttpClient*> для <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>. Этот метод расширения регистрирует внутренний класс `DefaultHttpClientFactory`, который будет использоваться как класс-одиночка для интерфейса `IHttpClientFactory`. Он определяет временную конфигурацию для <xref:Microsoft.Extensions.Http.HttpMessageHandlerBuilder>. Этот обработчик сообщений (объект <xref:System.Net.Http.HttpMessageHandler>), взятый из пула, используется классом `HttpClient`, который возвращается фабрикой.

В приведенном далее коде показано, как `AddHttpClient()` может использоваться для регистрации типизированных клиентов (агентов службы), которым нужно использовать `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

Как показано в предыдущем примере кода, регистрация клиентских служб позволяет `DefaultClientFactory` создать объект `HttpClient` для каждой службы.

В регистрацию можно также добавить настройки конкретного экземпляра, например, настроить базовый адрес и добавить некоторые политики устойчивости, как показано в следующем коде:

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

В следующем коде для примера показана одна из приведенных выше политик.

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

Дополнительные сведения об использовании Polly можно найти в [следующей статье](implement-http-call-retries-exponential-backoff-polly.md).

### <a name="httpclient-lifetimes"></a>Время существования HttpClient

Каждый раз, когда вы получаете объект `HttpClient` из `IHttpClientFactory`, возвращается новый экземпляр. Но чтобы уменьшить потребление ресурсов, каждый объект `HttpClient` использует из пула экземпляр `HttpMessageHandler`, который также применяется фабрикой `IHttpClientFactory`, если время существования `HttpMessageHandler` еще не истекло.

Создание пулов обработчиков желательно, поскольку каждый обработчик обычно управляет собственными базовыми HTTP-подключениями. Создание лишних обработчиков может привести к задержке подключения. Некоторые обработчики поддерживают подключения открытыми в течение неопределенного периода, что может помешать обработчику отреагировать на изменения DNS.

Время существования объектов `HttpMessageHandler`это период, в течение которого экземпляр `HttpMessageHandler` в пуле может использоваться повторно. Значение по умолчанию — две минуты, но его можно переопределить для отдельных типизированных клиентов. Чтобы переопределить это значение, вызовите `SetHandlerLifetime()` в экземпляре <xref:Microsoft.Extensions.DependencyInjection.IHttpClientBuilder>, который возвращается при создании клиента, как показано в следующем примере кода:

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

Для каждого типизированного клиента можно указать свое значение времени существования настроенного обработчика. Установите значение `InfiniteTimeSpan`, чтобы отключить срок действия обработчика.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Реализация классов типизированных клиентов, использующих внедренный и настроенный HttpClient

Вы уже должны были определить классы типизированных клиентов, например классы в примере кода, такие как BasketService, CatalogService, OrderingService и т. д. Типизированный клиент — это класс, который принимает объект `HttpClient` (внедренный через конструктор) и использует его для вызова удаленной службы HTTP. Пример:

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take,
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl,
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

Типизированный клиент (в нашем примере это `CatalogService`) активируется путем внедрения зависимостей, то есть он может принять любую зарегистрированную службу в свой конструктор в дополнение к `HttpClient`.

По сути, типизированный клиент — это временный объект, то есть экземпляр создается каждый раз по необходимости и при этом он будет получать новый экземпляр `HttpClient`. Тем не менее объекты `HttpMessageHandler` в пуле используются повторно множеством экземпляров `HttpClient`.

### <a name="use-your-typed-client-classes"></a>Использование классов типизированных клиентов

Наконец, когда вы реализуете классы типов, а также зарегистрируете и настроите их в `AddHttpClient()`, их можно будет использовать везде, где можно внедрить службы с помощью внедрения зависимостей. Например, в любом коде страницы Razor или любом контроллере веб-приложения MVC, как в следующем коде из eShopOnContainers.

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) =>
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied,
                                               int? TypesFilterApplied,
                                               int? page,
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0,
                                                            itemsPage,
                                                            BrandFilterApplied,
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

Пока пример кода просто выполняет обычные HTTP-запросы. Самое интересное начнется в следующих разделах, где вы будете просто добавлять политики и делегирующие обработчики в зарегистрированные типизированные клиенты. Все HTTP-запросы, которые должны выполняться объектом `HttpClient`, будут учитывать политики отказоустойчивости, например политики повтора c экспоненциальной задержкой, размыкатели цепи или другие настраиваемые делегирующие обработчики, чтобы реализовать дополнительные функции безопасности, такие как маркеры проверки подлинности и другие настраиваемые возможности.

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Использование HttpClientFactory в .NET Core**  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- **Исходный код HttpClientFactory в репозитории GitHub `dotnet/extensions`**  
  <https://github.com/dotnet/extensions/tree/master/src/HttpClientFactory>

- **Polly (библиотека для обеспечения отказоустойчивости .NET и обработки временных сбоев)**  
  <http://www.thepollyproject.org/>
  
- **Использование IHttpClientFactory без внедрения зависимостей (проблема GitHub)**  
  <https://github.com/dotnet/extensions/issues/1345>

>[!div class="step-by-step"]
>[Назад](implement-resilient-entity-framework-core-sql-connections.md)
>[Вперед](implement-http-call-retries-exponential-backoff-polly.md)
