---
title: Использование HttpClientFactory для реализации устойчивых HTTP-запросов
description: HttpClientFactory — это проверенная фабрика, доступная начиная с .NET Core 2.1. С ее помощью можно создавать экземпляры `HttpClient`, которые используются в приложениях.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 07/03/2018
ms.openlocfilehash: 6fd30a9358ca9c07b2a6e2ec591e4c5d7db54ccb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513217"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a>Использование HttpClientFactory для реализации устойчивых HTTP-запросов

`HttpClientFactory` — это проверенная фабрика, доступная начиная с .NET Core 2.1. С ее помощью можно создавать экземпляры `HttpClient`, которые используются в приложениях. 

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a>Проблемы с исходным классом HttpClient, доступным в .NET Core

Исходный и хорошо известный класс [HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) очень прост в использовании, но иногда разработчики применяют его неправильно. 

Первая проблема в том, что, хотя этот класс и является одноразовым, лучше не использовать его с инструкцией `using`, поскольку даже при ликвидации объекта `HttpClient` базовый сокет не освобождается сразу, что может привести к исчерпанию сокетов. Дополнительные сведения об этой проблеме см. в записи блога [Неправильное использование HttpClient и нарушение стабильной работы программного обеспечения](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).

Таким образом, создается один экземпляр `HttpClient`, которые будет использоваться повторно на протяжении всего жизненного цикла приложения. Создание экземпляра класса `HttpClient` для каждого запроса будет сокращать количество доступных сокетов при больших нагрузках. В результате будут возникать ошибки `SocketException`. Возможные способы решения этой проблемы основаны на создании объекта `HttpClient` в виде класса-одиночки или статического класса, как описано в этой [статье Майкрософт об использовании HttpClient](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/console-webapiclient). 

Но есть еще одна проблема с `HttpClient`, которая может возникнуть, когда вы используете его как класс-одиночку или статический объект. В этом случае класс-одиночка или статический класс `HttpClient` не учитывает изменения в DNS, как описано в этой [проблеме в репозитории GitHub по .NET Core](https://github.com/dotnet/corefx/issues/11224). 

Чтобы решить эти проблемы и упростить управление экземплярами `HttpClient`, .NET Core 2.1 предлагает новую фабрику `HttpClientFactory`, которую также можно использовать для реализации устойчивых HTTP-вызовов путем интеграции с Polly.   

## <a name="what-is-httpclientfactory"></a>Что такое HttpClientFactory

Задачи `HttpClientFactory`:

- Центральное расположение для именования и настройки логических объектов HttpClient. Например, вы можете настроить клиент (агент службы), который предварительно настроен для доступа к определенной микрослужбе.
- Кодификация концепции исходящего ПО промежуточного слоя путем делегирования обработчиков в `HttpClient` и реализация ПО промежуточного слоя на основе Polly для использования политик устойчивости Polly.
- В `HttpClient` уже существует концепция делегирования обработчиков, которые можно связать друг с другом для исходящих HTTP-запросов. Вы можете регистрировать объекты HttpClient в фабрике, а также использовать обработчик Polly, чтобы использовать политики Polly для повторных попыток, размыкателя цепи и т. д.
- Управление временем существования HttpClientMessageHandler, чтобы избежать упомянутых проблем, которые могут возникнуть при управлении временем существования `HttpClient` самостоятельно. 

## <a name="multiple-ways-to-use-httpclientfactory"></a>Способы применения HttpClientFactory

Есть несколько способов использования `HttpClientFactory` в вашем приложении:

- Использование `HttpClientFactory` напрямую
- Использование именованных клиентов
- Использование типизированных клиентов
- Использование созданных клиентов

Для краткости в этом руководстве показан наиболее структурированный способ использования `HttpClientFactory`, а именно — с помощью типизированных клиентов (шаблон агента службы), но все параметры описаны и в данный момент перечислены в этой [статье об использовании HttpClientFactory](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?#consumption-patterns).  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a>Как использовать типизированные клиенты с HttpClientFactory

На следующей схеме показано, как использовать типизированные клиенты с HttpClientFactory.

![Схема с контроллером MVC, использующим внедренную службу ClientService, которая использует HttpClient, настроенный с помощью HttpClientFactory и политик Polly](./media/image3.5.png)

**Рис. 10-4**. Использование `HttpClientFactory` с классами типизированных клиентов.

Сначала настройте `HttpClientFactory` в приложении. Добавьте ссылку на пакет `Microsoft.Extensions.Http`, который включает метод расширения `AddHttpClient()` для `IServiceCollection`. Этот метод расширения регистрирует класс `DefaultHttpClientFactory`, который будет использоваться как класс-одиночка для интерфейса `IHttpClientFactory`. Он определяет временную конфигурацию для `HttpMessageHandlerBuilder`. Этот обработчик сообщений (объект `HttpMessageHandler`), взятый из пула, используется классом `HttpClient`, который возвращается фабрикой.

В приведенном далее коде показано, как `AddHttpClient()` может использоваться для регистрации типизированных клиентов (агентов службы), которым нужно использовать `HttpClient`.

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

Если вы просто добавите классы типизированного клиента с AddHttpClient() при использовании объекта `HttpClient`, который будет внедрен в ваш класс через конструктор, этот объект `HttpClient` будет использовать все указанные конфигурации и политики. В следующих разделах вы увидите эти политики, например политику повтора или размыкателя цепи Polly.

### <a name="httpclient-lifetimes"></a>Время существования HttpClient

Каждый раз, когда вы получаете объект `HttpClient` из IHttpClientFactory, возвращается новый экземпляр `HttpClient`. У вас будет HttpMessageHandler ** для каждого именованного или типизированного клиента. I`HttpClientFactory` будет объединять в пул все экземпляры HttpMessageHandler, созданные фабрикой, чтобы уменьшить потребление ресурсов. Экземпляр HttpMessageHandler можно использовать повторно из пула при создании нового экземпляра `HttpClient`, если его время существования еще не истекло.

Создание пулов обработчиков желательно, поскольку каждый обработчик обычно управляет собственными базовыми HTTP-подключениями. Создание лишних обработчиков может привести к задержке подключения. Некоторые обработчики поддерживают подключения открытыми в течение неопределенного периода, что может помешать обработчику отреагировать на изменения DNS.

Время существования объектов HttpMessageHandler — это период, когда экземпляр HttpMessageHandler в пуле может использоваться повторно. Значение по умолчанию — две минуты, но его можно переопределить для отдельных именованных или типизированных клиентов. Чтобы переопределить это значение, вызовите SetHandlerLifetime() в IHttpClientBuilder, который возвращается при создании клиента, как показано в следующем коде.

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

Для каждого типизированного или именованного клиента можно указать свое значение времени существования настроенного обработчика. Установите значение InfiniteTimeSpan, чтобы отключить срок действия обработчика.

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a>Реализация классов типизированных клиентов, использующих внедренный и настроенный HttpClient

Вы должны были уже определить классы типизированных клиентов, например классы в примере кода, такие как BasketService, CatalogService, OrderingService и т. д. Типизированный клиент — это класс, который принимает объект `HttpClient` (внедренный через конструктор) и использует его для вызова удаленной службы HTTP. Пример:

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

Типизированный клиент (в примере это CatalogService) активируется посредством внедрения зависимостей, то есть он может принять любую зарегистрированную службу в свой конструктор в дополнение к HttpClient.

Типизированный клиент, по сути, — это временный объект, то есть новый экземпляр создается каждый раз, когда он нужен, и он будет получать новый экземпляр `HttpClient` при каждом создании. Тем не менее объекты HttpMessageHandler в пуле используются повторно множеством HTTP-запросов.

### <a name="use-your-typed-client-classes"></a>Использование классов типизированных клиентов

Наконец, когда вы реализуете классы типов и зарегистрируете их в AddHttpClient(), их можно будет использовать везде, где можно внедрить службы с помощью внедрения зависимостей, например в любом коде страницы Razor или любом контроллере веб-приложения MVC, как, например, в следующем коде из eShopOnContainers.

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

Пока показанный код просто выполняет обычные HTTP-запросы. Самое интересное начнется в следующих разделах, где вы будете просто добавлять политики и делегирующие обработчики в зарегистрированные типизированные клиенты, и все HTTP-запросы, которые должны выполняться объектом `HttpClient`, будут учитывать политики отказоустойчивости, например политики повтора c экспоненциальной задержкой, размыкатели цепи или другие настраиваемые делегирующие обработчики, чтобы реализовать дополнительные функции безопасности, такие как маркеры проверки подлинности и другие настраиваемые возможности. 


## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Использование HttpClientFactory в .NET Core 2.1**
    [*https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)


-   **Репозиторий GitHub HttpClientFactory**

    [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)



>[!div class="step-by-step"]
[Назад] (explore-custom-http-call-retries-exponential-backoff.md) [Далее] (implement-http-call-retries-exponential-backoff-polly.md)
