---
title: Реализация шлюзов API с помощью Ocelot
description: Узнайте, как реализовывать шлюзы API с помощью Ocelot и как использовать Ocelot в среде на базе контейнеров.
ms.date: 03/02/2020
ms.openlocfilehash: 28b9ca22d232baf3545d71b876cecf72fea05c92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846950"
---
# <a name="implement-api-gateways-with-ocelot"></a>Реализация шлюзов API с помощью Ocelot

> [!IMPORTANT]
> В настоящее время приложение микрослужбы [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) использует функции, предоставляемые [Envoy](https://www.envoyproxy.io/) для реализации шлюза API вместо раннее упоминаемого [Ocelot](https://github.com/ThreeMammals/Ocelot).
> Мы внесли этот вариант проектирования из-за встроенной поддержки Envoy для протокола WebSocket, необходимого для нового обмена данными между службами gRPC, реализованного в eShopOnContainers.
> Тем не менее, мы сохранили этот раздел в руководстве, так что вы можете рассматривать Ocelot как простой, совместимый и легкий API шлюз, подходящий для сценариев производственного уровня.

## <a name="architect-and-design-your-api-gateways"></a>Разработка архитектуры и проектирование шлюзов API

На следующей схеме архитектуры показано реализацию шлюзов API с помощью Ocelot в eShopOnContainers.

![Схема, показывающая архитектуру eShopOnContainers.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

**Рис. 6-28**. Архитектура eShopOnContainers со шлюзами API

На схеме показано, как целое приложение развертывается в одном узле Docker или на компьютере разработки с помощью Docker для Windows или Docker для Mac. Развертывание в любом оркестраторе будет выглядеть аналогично, но любой контейнер на схеме можно было бы горизонтально масштабировать в оркестраторе.

Кроме того, ресурсы инфраструктуры, такие как базы данных, кэш и брокеры сообщений, необходимо выгрузить из оркестратора и развернуть в системах высокой доступности для инфраструктуры, таких как база данных SQL Azure, Azure Cosmos DB, Azure Redis, служебная шина Azure или любое локальное решение по кластеризации высокого уровня доступности.

Как видно на схеме, наличие нескольких шлюзов API обеспечивает автономность нескольких команд разработчиков (в данном случае — маркетинговые функции и функции магазина) при разработке и развертывании микрослужб, а также собственных связанных шлюзов API.

Если бы у вас был единый монолитный шлюз API, несколько команд разработчиков обновляли бы одну точку, и все микрослужбы были бы привязаны к одной части приложения.

Если пойти еще дальше, иногда можно выделить один детализированный шлюз API для конкретной микрослужбы в зависимости от выбранной архитектуры. Наличие границ шлюза API, определяемых бизнес-требованиями или доменом, поможет лучше спроектировать шлюз.

Например, высокая детализация для уровня шлюза API может быть особенно удобной для более сложных приложений с составным пользовательским интерфейсом на основе микрослужб, так как концепция детализированного шлюза API похожа на службу с составным пользовательским интерфейсом.

Подробнее этот вопрос рассмотрен в предыдущем разделе [Создание составного пользовательского интерфейса на основе микрослужб](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).

Вкратце, пользовательский шлюз API удобно использовать для многих приложений среднего и большого размера, но не в качестве единого монолитного агрегатора или уникального централизованного пользовательского шлюза API, если только этот шлюз API не допускает несколько независимых областей конфигурации для нескольких групп разработчиков, создающих автономные микрослужбы.

### <a name="sample-microservicescontainers-to-reroute-through-the-api-gateways"></a>Пример микрослужбы и контейнеров для перенаправления через шлюзы API

Например, у eShopOnContainers есть около шести типов внутренних микрослужб, которые требуется публиковать через шлюзы API, как показано на следующем рисунке.

![Снимок экрана папки Services, содержащей вложенные папки](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

**Рис. 6-29**. Папки микрослужб в решении eShopOnContainers в Visual Studio

Что касается службы идентификации, в проекте она не проходит через шлюзы API, так как только она является общей для всей системы, но с помощью Ocelot ее также можно включить в списки перенаправления.

Все эти службы в настоящее время реализованы как службы веб-API ASP.NET Core, как видно из кода. Давайте сосредоточимся на одной из микрослужб, например коде микрослужбы каталога Catalog.

![Снимок экрана обозревателя решений, где показано содержимое проекта Catalog.API.](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

**Рис. 6-30**. Пример микрослужбы веб-API (микрослужба каталога)

Вы видите, что микрослужба каталога является стандартным проектом веб-API ASP.NET Core с несколькими контроллерами и методами, как в следующем коде.

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

HTTP-запрос в итоге запустит такой код C#, который получает доступ к базе данных микрослужбы и выполняет какое-либо необходимое действие.

Если говорить об URL-адресе микрослужбы, при развертывании контейнеров на локальном компьютере разработки (локальном узле Docker) каждый контейнер микрослужбы всегда имеет внутренний порт (обычно это порт 80), указанный в файле Dockerfile, как показано ниже.

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
```

Порт 80, показанный в коде, находится внутри узла Docker, поэтому клиентские приложения не имеют к нему доступа.

Клиентские приложения имеют доступ только к внешним портам (если таковые имеются), которые публикуются при развертывании с помощью `docker-compose`.

Эти внешние порты не следует публиковать при развертывании в рабочей среде. Именно поэтому необходимо использовать шлюз API, чтобы избежать прямого обмена данными между микрослужбами и клиентскими приложениями.

Тем не менее при разработке вам следует обращаться к микрослужбам или контейнерам напрямую и запускать их через Swagger. Вот почему в eShopOnContainers внешние порты по-прежнему указываются даже в том случае, если они будут использоваться шлюзом API или клиентскими приложениями.

Ниже приведен пример файла `docker-compose.override.yml` для микрослужбы каталога.

```yml
catalog-api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

Вы видите, что в конфигурации docker-compose.override.yml внутренний порт контейнера каталога — это порт 80, но порт для внешнего доступа — 5101. Однако этот порт не должен использоваться приложением при использовании шлюза API. Он предназначен только для отладки, запуска и тестирования микрослужбы каталога.

Как правило, вы не выполняете развертывание в рабочей среде с помощью docker-compose, так как правильной рабочей средой для развертывания микрослужб является оркестратор, например Kubernetes или Service Fabric. При развертывании в этих средах вы используете различные файлы конфигурации, где вы не публикуете внешние порты для микрослужб напрямую, но всегда используете обратный прокси-сервер от шлюза API.

Запустите микрослужбу каталога в локальном узле Docker. Для этого запустите полное решение eShopOnContainers из Visual Studio (оно запускает все службы в файлах docker-compose) или запустите микрослужбу каталога с помощью следующей команды docker-compose в CMD или PowerShell в папке, где находятся `docker-compose.yml` и `docker-compose.override.yml`.

```console
docker-compose run --service-ports catalog-api
```

Эта команда только выполняет контейнер службы catalog-api, а также зависимости, указанные в файле docker-compose.yml. В данном случае это контейнер SQL Server и контейнер RabbitMQ.

Затем вы можете напрямую обратиться к микрослужбе каталога и просмотреть ее методы в пользовательском интерфейсе Swagger напрямую через внешний порт, в данном случае `http://localhost:5101/swagger`.

![Снимок экрана интерфейса Swagger, где показан REST API Catalog.API.](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

**Рис. 6-31**. Тестирование микрослужбы каталога с помощью ее пользовательского интерфейса Swagger

На этом этапе можно установить точку останова в коде C# в Visual Studio, протестировать микрослужбу с помощью методов, предоставляемых в пользовательском интерфейсе Swagger, и, наконец, очистить все с помощью команды `docker-compose down`.

Однако прямого взаимодействия с микрослужбой, в этом случае через внешний порт 5101, как раз следует избегать в приложении. Для этого необходимо задать дополнительный уровень косвенного обращения через шлюз API (в данном случае Ocelot). Таким образом, клиентское приложение не будет обращаться к микрослужбе напрямую.

## <a name="implementing-your-api-gateways-with-ocelot"></a>Реализация шлюзов API с помощью Ocelot

По сути, Ocelot — это набор ПО промежуточного слоя, которое можно применить в определенном порядке.

Ocelot предназначен для работы только с ASP.NET Core. Последняя версия пакета предназначена для `.NETCoreApp 3.1` и не подходит для приложений .NET Framework.

Вы устанавливаете Ocelot и его зависимости в проекте ASP.NET Core с помощью [пакета NuGet Ocelot](https://www.nuget.org/packages/Ocelot/) из Visual Studio.

```powershell
Install-Package Ocelot
```

В eShopOnContainers его реализация шлюза API представляет собой простой проект ASP.NET Core WebHost, и ПО промежуточного слоя Ocelot обрабатывает все функции шлюза API, как показано на следующем рисунке.

![Снимок экрана обозревателя решений, где показан проект шлюза API Ocelot.](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

**Рис. 6-32**. Базовый проект OcelotApiGw в eShopOnContainers

Этот проект ASP.NET Core WebHost, по сути, состоит из двух простых файлов: `Program.cs` и `Startup.cs`.

Файл Program.cs просто должен создать и настроить обычный BuildWebHost ASP.NET Core.

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

Важно отметить, что в Ocelot вы должны предоставить построителю файл `configuration.json` через метод `AddJsonFile()`. В файле `configuration.json` вы указываете все объекты ReRoute шлюза API, то есть внешние конечные точки с определенными портами и коррелированные внутренние конечные точки, обычно используя разные порты.

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

Существует два раздела конфигурации: Массив объектов ReRoute и глобальная конфигурация GlobalConfiguration ReRoute — это объекты, которые указывают Ocelot, как обрабатывать вышестоящий запрос. Глобальная конфигурация может переопределять конкретные параметры объектов ReRoute. Это полезно, если вы не хотите управлять большим числом параметров ReRoute.

Ниже приведен упрощенный пример [файла конфигурации ReRoute](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) из одного из шлюзов API в eShopOnContainers.

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

Основная функция шлюзов API Ocelot — принимать входящие HTTP-запросы и перенаправлять их подчиненной службе, в настоящее время в виде другого HTTP запроса. Ocelot описывает направление одного запроса в другой как ReRoute.

Давайте сосредоточимся на одном из ReRoute в файле configuration.json из примера выше, где содержится конфигурация для микрослужбы корзины.

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

DownstreamPathTemplate, Scheme и DownstreamHostAndPorts формируют URL-адрес внутренней микрослужбы, которой будет переадресован запрос.

В качестве порта указан внутренний порт, используемый службой. Если вы используете контейнеры, порт указан в файле dockerfile.

`Host` — это имя службы, которое зависит от используемого разрешения имени службы. При использовании docker-compose имена служб предоставляются узлом Docker, который использует имена служб, предоставленные в файлах docker-compose. При использовании оркестратора, например Kubernetes или Service Fabric, это имя должно разрешаться DNS или службой разрешения имен, предоставляемой каждым оркестратором.

DownstreamHostAndPorts — это массив, содержащий узел и порт любых подчиненных служб, которым вы хотите переадресовывать запросы. Обычно он содержит всего одну запись, но иногда вы можете распределять нагрузку запросов к подчиненным службам, и Ocelot позволяет добавлять несколько записей и выбирать подсистему балансировки нагрузки. Но если вы используете Azure и оркестратор, возможно, лучше распределять нагрузку с помощью инфраструктуры облака и оркестратора.

UpstreamPathTemplate — это URL-адрес, который Ocelot будет использовать для выбора DownstreamPathTemplate для определенного запроса от клиента. Наконец, UpstreamHttpMethod используется для того, чтобы Ocelot различал запросы (GET, POST, PUT) к одному URL-адресу.

На этом этапе у вас может быть один шлюз API Ocelot (ASP.NET Core WebHost), использующий один или [несколько объединенных файлов configuration.json](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files), или вы можете хранить [конфигурацию в хранилище Consul KV](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).

Но, как описывалось в разделах об архитектуре и проектировании, если вы действительно хотите иметь автономные микрослужбы, лучше разделить этот единый монолитный шлюз API на несколько шлюзов API и (или) BFF (Backend for Frontend). Давайте посмотрим, как реализовать этот подход с контейнерами Docker.

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a>Использование одного образа контейнера Docker для запуска нескольких типов шлюзов API/контейнеров BFF

В eShopOnContainers мы используем единый образ контейнера Docker со шлюзом API Ocelot, но затем во время выполнения мы создаем различные службы и контейнеры для каждого типа шлюза API/BFF, предоставляя отдельный файл configuration.json и используя том Docker для доступа к разным папкам на компьютере для каждой службы.

![Схема одного образа Docker шлюза Ocelot для всех шлюзов API.](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

**Рис. 6-33**. Повторное использование одного образа Ocelot Docker в нескольких типах шлюзов API

В eShopOnContainers создается универсальный образ Docker для шлюза API Ocelot с проектом OcelotApiGw и образом eshop/ocelotapigw, который указан в файле docker-compose.yml. Затем при развертывании в Docker будет четыре шлюза API с контейнерами, созданными из этого образа Docker, как показано в следующем фрагменте из файла docker-compose.yml.

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

Кроме того, как видно из приведенного ниже файла docker-compose.override.yml, единственное различие между этими контейнерами в шлюзах API — файл конфигурации Ocelot, который отличается для каждого контейнера службы и указывается во время выполнения с помощью тома Docker.

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

В результате предыдущего кода и как показано в обозревателе Visual Studio ниже, всего один файл configuration.json определяет конкретный шлюз API для BFF или подразделения, поскольку все четыре шлюза API основаны на одном образе Docker.

![Снимок экрана, где показаны все шлюзы API с файлами configuration.json.](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

**Рис. 6-34**. Для определения каждого шлюза API/BFF с помощью Ocelot требуется только файл конфигурации

Если разделить один шлюз API на несколько, разные команды разработчиков, занимающиеся разными подмножествами микрослужб, смогут управлять своими шлюзами API с помощью независимых файлов конфигурации Ocelot. Кроме того, в то же время они могут повторно использовать один и тот же образ Docker Ocelot.

Теперь при запуске eShopOnContainers со шлюзами API (включены по умолчанию в Visual Studio при открытии решения eShopOnContainers-ServicesAndWebApps.sln или выполнении команды docker-compose up) будут выполняться направления запросов, как в следующем примере.

Например, при посещении вышестоящего URL-адреса `http://localhost:5202/api/v1/c/catalog/items/2/`, обслуживаемого шлюзом API webshoppingapigw, вы получаете тот же результат от внутреннего подчиненного URL-адреса `http://catalog-api/api/v1/2` в узле Docker, как показано ниже.

![Снимок экрана браузера, где показан ответ, идущий через шлюз API.](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

**Рис. 6-35**. Доступ к микрослужбе с помощью URL-адреса, предоставленного шлюзом API

В связи с тестированием или отладкой, если вы захотите получить прямой доступ к контейнеру Docker Catalog (только в среде разработки) без передачи через шлюз API, так как "catalog-api" является разрешением DNS внутри узла Docker (обнаружение служб, обрабатываемое именами служб docker-compose), это возможно только через внешний порт, опубликованный в файле docker-compose.override.yml, который предоставляется только для тестирования, например `http://localhost:5101/api/v1/Catalog/items/1` в следующем браузере.

![Снимок экрана браузера, где показан прямой ответ на Catalog.API.](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

**Рис. 6-36**. Прямой доступ к микрослужбе для тестирования

Но приложение настроено так, что обращается ко всем микрослужбам через шлюзы API, а не через прямой порт.

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a>Схема объединения шлюзов в eShopOnContainers

Как уже было сказано, объединять запросы удобнее всего с помощью настраиваемых служб, через код. Вы также можете объединять запросы с помощью [функции "Request Aggregation" в Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), но этот метод может оказаться недостаточно гибким. Поэтому рекомендуется реализовывать объединение в eShopOnContainers с помощью явных служб веб-API ASP.NET Core для каждого агрегатора.

С таким подходом схема шлюзов API в реальности является более расширенной, если учитывать службы агрегатора, которые не отображены в упрощенной схеме архитектуры, показанной ранее.

На следующей схеме видно, как работают службы агрегатора со связанными шлюзами API.

![Схема архитектуры eShopOnContainers со службами агрегатора.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

**Рис. 6-37**. Архитектура eShopOnContainers со службами агрегатора

Если подробнее рассмотреть область покупок на приведенном ниже изображении, можно заметить, что обмен данными между клиентскими приложениями и микрослужбами сокращается при использовании служб агрегатора в шлюзах API.

![Схема, показывающая увеличенную архитектуру eShopOnContainers.](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

**Рис. 6-38**. Службы агрегатора на схеме

Можно заметить, что, когда на схеме показаны возможные запросы, поступающие из шлюзов API, она усложняется. И хотя видно, что синие стрелки можно упростить, с точки зрения клиентских приложений, использование шаблона агрегатора сокращает число вызовов и задержки при обмене данными и, в конечном счете, значительно повышает удобство работы пользователей, особенно с удаленными приложениями (мобильными и одностраничными приложениями).

Для области бизнеса и микрослужб маркетинга схема очень проста и можно обойтись без агрегаторов, но их допустимо использовать при необходимости.

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a>Проверка подлинности и авторизация в шлюзах API Ocelot

В шлюзе API Ocelot можно разместить службу проверки подлинности, например службу веб-API ASP.NET Core, с помощью [IdentityServer](https://identityserver.io/), предоставив маркер проверки подлинности снаружи или внутри шлюза API.

Поскольку eShopOnContainers использует разные шлюзы API с границами на основе BFF и областей бизнеса, службы идентификации или проверки подлинности находятся за пределами шлюзов API (выделено желтым на следующей схеме).

![Схема, показывающая микрослужбу идентификации, расположенную под шлюзом API.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

**Рис. 6-39**. Положение службы идентификации в eShopOnContainers

Тем не менее Ocelot также поддерживает размещение микрослужбы идентификации или проверки подлинности в границах шлюза API, как показано на этой схеме.

![Схема, показывающая проверку подлинности в шлюзе API Ocelot.](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

**Рис. 6-40**. Проверка подлинности в Ocelot

Как показано на предыдущей схеме, если микрослужба идентификации находится под шлюзом API (AG), происходит следующее: 1) AG запрашивает маркер проверки подлинности у микрослужбы идентификации; 2) микрослужба идентификации возвращает маркер в AG; 3–4) AG выполняет запрос из микрослужб с использованием маркера проверки подлинности. Так как приложение eShopOnContainers разделило шлюз API на несколько BFF (Backend for Frontend) и шлюзов API для областей бизнеса, для решения общих задач также можно создать дополнительный шлюз API. Такой вариант подойдет для более сложной архитектуры на базе микрослужб с несколькими микрослужбами, выполняющими общие задачи. Так как в eShopOnContainers есть только одна общая задача, для простоты было решено обрабатывать службу безопасности вне области шлюза API.

В любом случае, если безопасность приложения обеспечивается на уровне шлюзов API, модуль проверки подлинности шлюза API Ocelot посещается первым при попытке использовать защищенную микрослужбу. Он перенаправляет HTTP-запросы в микрослужбу идентификации или проверки подлинности для получения маркера доступа, поэтому вы можете посещать защищенные службы с маркером доступа.

Чтобы защитить любую службу с помощью проверки подлинности на уровне шлюза API, укажите AuthenticationProviderKey в соответствующих параметрах в файле configuration.json.

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

При запуске Ocelot он будет смотреть на AuthenticationOptions.AuthenticationProviderKey для объектов ReRoute и проверит наличие поставщика проверки подлинности, зарегистрированного с указанным ключом. Если его нет, Ocelot не будет запущен. Если он есть, объект ReRoute будет использовать этого поставщика при выполнении.

Поскольку Ocelot WebHost настраивается с помощью `authenticationProviderKey = "IdentityApiKey"`, он требует проверки подлинности каждый раз, когда у службы есть запросы без маркера проверки подлинности.

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

Затем необходимо также настроить авторизацию с помощью атрибута [Authorize] в любом ресурсе, к которому требуется доступ, например в микрослужбах, как в контроллере микрослужбы корзины в следующем примере.

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

Объекты ValidAudiences, например basket, коррелируют с аудиторией, определенной в каждой микрослужбе с помощью `AddJwtBearer()` в ConfigureServices() в классе Startup, как показано в приведенном ниже коде.

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

При попытке получить доступ к любой защищенной микрослужбе, такой как микрослужба корзины с URL-адресом ReRoute на основе шлюза API, например `http://localhost:5202/api/v1/b/basket/1`, возникнет ошибка 401 (неавторизованный доступ), если вы не предоставите допустимый токен. С другой стороны, если URL-адрес ReRoute прошел проверку подлинности, Ocelot будет вызывать связанную с ним подчиненную схему (URL-адрес внутренней микрослужбы).

**Авторизация на уровне объектов ReRoute Ocelot**  Ocelot поддерживает авторизацию на основе утверждений, которая вычисляется после проверки подлинности. Вы задаете авторизацию на уровне маршрута, добавляя приведенные ниже строки в конфигурацию перенаправления.

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

В этом примере при вызове ПО промежуточного слоя авторизации Ocelot обнаружит, имеет ли пользователь тип утверждения UserType в маркере и имеет ли это утверждение значение "employee". Если это не так, пользователь не будет авторизован, и возникнет ошибка 403 (доступ запрещен).

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a>Использование Kubernetes Ingress и шлюзов API Ocelot

При использовании Kubernetes (как в кластере Службы Azure Kubernetes) вы обычно унифицируете все HTTP-запросы через [уровень Kubernetes Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) на основе *Nginx*.

Если в Kubernetes вы не используете точку входа, IP-адреса ваших служб и модулей pod могут перенаправляться только сетью кластера.

Но если вы используете точку входа, у вас есть промежуточный уровень между Интернетом и службами (включая шлюзы API), который выступает в качестве обратного прокси-сервера.

Точка входа — это набор правил, которые разрешают входящие подключения к службам кластера. Обычно точка входа настраивается для предоставления службам доступных извне URL-адресов, распределения нагрузки трафика, завершения SSL-запросов и многого другого. Пользователи запрашивают точку входа с помощью запроса POST для ресурса Ingress к серверу API.

В eShopOnContainers при локальной разработке и использовании только компьютера разработки в качестве узла Docker вы используете не точку входа, а только несколько шлюзов API.

Но при ориентации на рабочую среду на основе Kubernetes eShopOnContainers использует точку входа перед шлюзами API. Таким образом, клиенты по-прежнему вызывают тот же базовый URL-адрес, но запросы направляются к нескольким шлюзам API или BFF.

Шлюзы API — это внешний интерфейс, взаимодействующий только со службами, но не с веб-приложениями, которые обычно находятся вне области их действия. Кроме того, шлюзы API могут скрывать некоторые внутренние микрослужбы.

Но точка входа просто перенаправляет запросы HTTP и не пытается скрыть микрослужбы или веб-приложения.

В идеальной архитектуре есть входящий уровень Nginx в Kubernetes перед веб-приложениями, а также несколько шлюзов API Ocelot/BFF, как показано на приведенной ниже схеме.

![Схема, показывающая входящий уровень в среде AKS.](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

**Рис. 6-41**. Входящий уровень в eShopOnContainers при развертывании в Kubernetes

Kubernetes Ingress выступает в качестве обратного прокси-сервера для всего трафика, направляемого в приложение, включая веб-приложения, которые обычно выходят из области действия шлюза API. При развертывании eShopOnContainers в Kubernetes предоставляется всего несколько служб или конечных точек через _точку входа_, в основном только следующий список постфиксов в URL-адресах:

- `/` для клиента веб-приложения SPA
- `/webmvc` для клиента веб-приложения MVC
- `/webstatus` для клиента веб-приложения с отображением состояния или проверки работоспособности
- `/webshoppingapigw` для веб-BFF и бизнес-процессов покупок
- `/webmarketingapigw` для веб-BFF и бизнес-процессов маркетинга
- `/mobileshoppingapigw` для мобильного BFF и бизнес-процессов покупок
- `/mobilemarketingapigw` для мобильного -BFF и бизнес-процессов маркетинга

При развертывании в Kubernetes каждый шлюз API Ocelot использует отдельный файл configuration.json для каждого модуля _pod_, управляющего шлюзами API. Эти файлы configuration.json предоставляются путем подключения (изначально с помощью сценария deploy.ps1) тома, созданного на основе _схемы конфигурации_ Kubernetes с именем ocelot. Каждый контейнер подключает связанный файл конфигурации в папку контейнера с именем `/app/configuration`.

В файлах исходного кода eShopOnContainers исходные файлы configuration.json можно найти в папке `k8s/ocelot/`. Существует один файл для каждого BFF/шлюза API.

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a>Дополнительные перекрестные функции в шлюзе API Ocelot

Изучите другие важные функции, связанные с использованием шлюза API Ocelot, по следующим ссылкам.

- **Обнаружение службы на стороне клиента через интеграцию Ocelot с Consul или Eureka** \
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- **Кэширование на уровне шлюза API** \
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- **Ведение журнала на уровне шлюза API** \
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- **Качество обслуживания (повторы и размыкатели цепи) на уровне шлюза API** \
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- **Ограничения скорости** \
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> [Назад](background-tasks-with-ihostedservice.md)
> [Вперед](../microservice-ddd-cqrs-patterns/index.md)
