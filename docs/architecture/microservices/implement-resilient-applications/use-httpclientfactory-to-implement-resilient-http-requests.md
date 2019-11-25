---
title: Использование HttpClientFactory для реализации устойчивых HTTP-запросов
description: Узнайте, как использовать фабрику HttpClientFactory, доступную в .NET Core, начиная с версии 2.1, для создания экземпляров `HttpClient`, чтобы облегчить их применение в ваших приложениях.
ms.date: 08/08/2019
ms.openlocfilehash: 9eff4a01361b3dc6f7471bc012c945d048b9a276
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737743"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a>Использование HttpClientFactory для реализации устойчивых HTTP-запросов

`HttpClientFactory` — это проверенная фабрика, доступная начиная с .NET Core 2.1. С ее помощью можно создавать экземпляры <xref:System.Net.Http.HttpClient>, которые используются в приложениях.

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Проблемы с исходным классом HttpClient, доступным в .NET Core

Исходный и хорошо известный класс <xref:System.Net.Http.HttpClient> очень просто использовать, но иногда разработчики применяют его неправильно.

Первая проблема в том, что, хотя этот класс и является одноразовым, лучше не использовать его с инструкцией `using`, поскольку даже при ликвидации объекта `HttpClient` базовый сокет не освобождается сразу, что может привести к исчерпанию сокетов. Дополнительные сведения об этой проблеме см. в записи блога [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Неправильное использование HttpClient и нарушение стабильной работы программного обеспечения).

Таким образом, создается один экземпляр `HttpClient`, которые будет использоваться повторно на протяжении всего жизненного цикла приложения. Создание экземпляра класса `HttpClient` для каждого запроса будет сокращать количество доступных сокетов при больших нагрузках. В результате будут возникать ошибки `SocketException`. Возможные способы решения этой проблемы основаны на создании объекта `HttpClient` в виде класса-одиночки или статического класса, как описано в этой [статье Майкрософт об использовании HttpClient](../../../csharp/tutorials/console-webapiclient.md).

Но есть еще одна проблема с `HttpClient`, которая может возникнуть, когда вы используете его как класс-одиночку или статический объект. В этом случае класс-одиночка или статический класс `HttpClient` не учитывает изменения в DNS. Эта проблема описывается [в репозитории GitHub dotnet/corefx](https://github.com/dotnet/corefx/issues/11224).

Чтобы решить эти проблемы и упростить управление экземплярами `HttpClient`, в .NET Core 2.1 появилась новая фабрика `HttpClientFactory`, которую также можно использовать для реализации устойчивых HTTP-вызовов путем интеграции с Polly.

[Polly](http://www.thepollyproject.org/) — это библиотека для обеспечения обработки временных сбоев, которая позволяет разработчикам повысить устойчивость своих приложений, используя некоторые стандартные политики более эффективным и потокобезопасным способом.

## <a name="what-is-httpclientfactory"></a>Что такое HttpClientFactory

Задачи `HttpClientFactory`:

- Центральное расположение для именования и настройки логических объектов `HttpClient`. Например, вы можете настроить клиент (агент службы), который предварительно настроен для доступа к определенной микрослужбе.
- Кодификация концепции исходящего ПО промежуточного слоя путем делегирования обработчиков в `HttpClient` и реализация ПО промежуточного слоя на основе Polly для использования политик устойчивости Polly.
- В `HttpClient` уже существует концепция делегирования обработчиков, которые можно связать друг с другом для исходящих HTTP-запросов. Вы можете регистрировать клиенты HTTP в фабрике, а также использовать обработчик Polly, чтобы использовать политики Polly для повторных попыток, размыкателя цепи и т. д.
- Управление временем существования `HttpClientMessageHandlers`, чтобы избежать упомянутых проблем, которые могут возникнуть при управлении временем существования `HttpClient` самостоятельно.

> [!NOTE]
> `HttpClientFactory` тесно привязывается к реализации внедрения зависимостей (DI) в пакете NuGet `Microsoft.Extensions.DependencyInjection`. См. сведения об использовании других контейнеров внедрения зависимостей в этом [обсуждении GitHub](https://github.com/aspnet/Extensions/issues/1345).

## <a name="multiple-ways-to-use-httpclientfactory"></a>Способы применения HttpClientFactory

Есть несколько способов использования `HttpClientFactory` в вашем приложении:

- Использование `HttpClientFactory` напрямую
- Использование именованных клиентов
- Использование типизированных клиентов
- Использование созданных клиентов

Для краткости в этом руководстве показан наиболее структурированный способ использования `HttpClientFactory`, а именно — с помощью типизированных клиентов (шаблон агента службы). Все параметры описаны и перечислены в [этой статье об использовании HttpClientFactory](/aspnet/core/fundamentals/http-requests#consumption-patterns).

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a>Как использовать типизированные клиенты с HttpClientFactory

Так что же такое типизированный клиент? Это просто класс `HttpClient`, настроенный после внедрения с помощью `DefaultHttpClientFactory`.

На следующей схеме показано, как использовать типизированные клиенты с `HttpClientFactory`.

![На схеме показано, как использовать типизированные клиенты с HttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

**Рис. 8-4**. Использование HttpClientFactory с классами типизированных клиентов.

На изображении выше ClientService (применяется контроллером или в коде клиента) использует объект `HttpClient`, созданный зарегистрированной фабрикой `IHttpClientFactory`. Эта фабрика назначает `HttpClient` `HttpMessageHandler` из пула, которым она управляет. `HttpClient` можно настроить с помощью политик Polly при регистрации фабрики `IHttpClientFactory` в контейнере внедрения зависимостей, используя метод расширения `AddHttpClient`.

Чтобы настроить такую структуру, добавьте `HttpClientFactory` в приложение, установив пакет NuGet `Microsoft.Extensions.Http`, который содержит метод расширения `AddHttpClient()` для `IServiceCollection`. Этот метод расширения регистрирует класс `DefaultHttpClientFactory`, который будет использоваться как класс-одиночка для интерфейса `IHttpClientFactory`. Он определяет временную конфигурацию для `HttpMessageHandlerBuilder`. Этот обработчик сообщений (объект `HttpMessageHandler`), взятый из пула, используется классом `HttpClient`, который возвращается фабрикой.

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

Время существования объектов `HttpMessageHandler`это период, в течение которого экземпляр `HttpMessageHandler` в пуле может использоваться повторно. Значение по умолчанию — две минуты, но его можно переопределить для отдельных типизированных клиентов. Чтобы переопределить это значение, вызовите `SetHandlerLifetime()` в экземпляре `IHttpClientBuilder`, который возвращается при создании клиента, как показано в следующем примере кода:

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

Для каждого типизированного клиента можно указать свое значение времени существования настроенного обработчика. Установите значение `InfiniteTimeSpan`, чтобы отключить срок действия обработчика.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Реализация классов типизированных клиентов, использующих внедренный и настроенный HttpClient

Вы уже должны были уже определить классы типизированных клиентов, например классы в примере кода, такие как BasketService, CatalogService, OrderingService и т. д. Типизированный клиент — это класс, который принимает объект `HttpClient` (внедренный через конструктор) и использует его для вызова удаленной службы HTTP. Например:

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

Типизированный клиент (в нашем примере это CatalogService) активируется путем внедрения зависимостей, то есть он может принять любую зарегистрированную службу в свой конструктор в дополнение к HttpClient.

По сути, типизированный клиент — это временный объект, то есть экземпляр создается каждый раз по необходимости и при этом он будет получать новый экземпляр `HttpClient`. Тем не менее объекты HttpMessageHandler в пуле используются повторно множеством HTTP-запросов.

### <a name="use-your-typed-client-classes"></a>Использование классов типизированных клиентов

Наконец, когда вы реализуете классы типов и зарегистрируете их в `AddHttpClient()`, их можно будет использовать везде, где можно внедрить службы с помощью внедрения зависимостей. Например, в любом коде страницы Razor или любом контроллере веб-приложения MVC, как в следующем коде из eShopOnContainers.

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

- **Исходный код HttpClientFactory в репозитории GitHub `aspnet/Extensions`**  
  <https://github.com/aspnet/Extensions/tree/master/src/HttpClientFactory>

- **Polly (библиотека для обеспечения отказоустойчивости .NET и обработки временных сбоев)**  
  <http://www.thepollyproject.org/>
  
- **Использование HttpClientFactory без внедрения зависимостей (проблема GitHub)**  
  <https://github.com/aspnet/Extensions/issues/1345>

>[!div class="step-by-step"]
>[Назад](explore-custom-http-call-retries-exponential-backoff.md)
>[Вперед](implement-http-call-retries-exponential-backoff-polly.md)
