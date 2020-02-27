---
title: Перенос службы WCF "запрос — ответ" в gRPC — gRPC для разработчиков WCF
description: Узнайте, как перенести простую службу "запрос — ответ" из WCF в gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 018aa94a15cdcb1e0f559afb7b3a88cd4f915398
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628557"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a>Перенос службы WCF "запрос — ответ" в gRPC унарный RPC

В этом разделе описано, как перенести базовую службу "запрос-ответ" в WCF в унарную службу RPC в ASP.NET Core gRPC. Эти службы являются простейшими типами служб как в Windows Communication Foundation (WCF), так и в gRPC, поэтому лучше всего начать с этого места. После переноса службы вы узнаете, как создать клиентскую библиотеку из того же файла `.proto`, чтобы использовать службу из клиентского приложения .NET.

## <a name="the-wcf-solution"></a>Решение WCF

[Решение портфолиоссампле](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) включает в себя простую службу портфеля "запрос-ответ" для загрузки одного портфеля или всех портфелей для конкретного торговца. Служба определена в интерфейсе `IPortfolioService` атрибутом `ServiceContract`:

```csharp
[ServiceContract]
public interface IPortfolioService
{
    [OperationContract]
    Task<Portfolio> Get(Guid traderId, int portfolioId);

    [OperationContract]
    Task<List<Portfolio>> GetAll(Guid traderId);
}
```

Модель `Portfolio` — это простой C# класс, помеченный как [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) и включающий список объектов `PortfolioItem`. Эти модели определяются в проекте `TraderSys.PortfolioData` вместе с классом репозитория, представляющим абстракцию доступа к данным.

```csharp
[DataContract]
public class Portfolio
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public Guid TraderId { get; set; }

    [DataMember]
    public List<PortfolioItem> Items { get; set; }
}

[DataContract]
public class PortfolioItem
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public int ShareId { get; set; }

    [DataMember]
    public int Holding { get; set; }

    [DataMember]
    public decimal Cost { get; set; }
}
```

В реализации `ServiceContract` используется класс репозитория, предоставляемый путем внедрения зависимостей, который возвращает экземпляры типов `DataContract`:

```csharp
public class PortfolioService : IPortfolioService
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }

    public async Task<Portfolio> Get(Guid traderId, int portfolioId)
    {
        return await _repository.GetAsync(traderId, portfolioId);
    }

    public async Task<List<Portfolio>> GetAll(Guid traderId)
    {
        return await _repository.GetAllAsync(traderId);
    }
}
```

## <a name="the-portfoliosproto-file"></a>Файл портфелей.

Если вы выполнили инструкции из предыдущего раздела, у вас должен быть проект gRPC с файлом `portfolios.proto`, который выглядит следующим образом:

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

Первым шагом является перенос классов `DataContract` в их эквиваленты protobuf.

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a>Преобразование классов DataContract в сообщения gRPC

Сначала класс `PortfolioItem` будет преобразован в сообщение protobuf, так как от него зависит класс `Portfolio`. Класс прост, а три свойства сопоставляются непосредственно с типами данных gRPC. Свойство `Cost`, которое представляет цену, уплаченную для общих ресурсов по закупке, является полем `decimal`. gRPC поддерживает только `float` или `double` для реальных чисел, которые не подходят для валюты. Так как цены на общий ресурс зависят от минимума одного цента, стоимость может быть выражена в `int32` центов.

> [!NOTE]
> Не забудьте использовать camelCase для имен полей в файле `.proto`. Генератор C# кода преобразует их в PascalCase, и пользователи других языков будут поблагодарить вас за соблюдение разных стандартов кодирования.

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

Класс `Portfolio` немного сложнее. В коде WCF разработчик использовал `Guid` для свойства `TraderId` и содержит `List<PortfolioItem>`. В protobuf, который не имеет типа `UUID` первого класса, следует использовать `string` для поля `traderId` и анализировать его в собственном коде. Для списка элементов используйте ключевое слово `repeated` в поле.

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

Теперь, когда у вас есть сообщения с данными, можно объявить конечные точки RPC службы.

## <a name="convert-servicecontract-to-a-grpc-service"></a>Преобразование ServiceContract в службу gRPC

Метод `Get` WCF принимает два параметра: `Guid traderId` и `int portfolioId`. методы службы gRPC могут принимать только один параметр, поэтому необходимо создать сообщение для хранения двух значений. Обычно имена этих объектов запроса имеют то же имя, что и метод, за которым следует суффикс `Request`. Опять же, `string` используется для поля `traderId`, а не `Guid`.

Служба может просто вернуть сообщение `Portfolio` напрямую, но опять же это может повлиять на обратную совместимость в будущем. Рекомендуется определять отдельные `Request` и `Response` сообщения для каждого метода в службе, даже если многие из них одинаковы. Поэтому объявите сообщение `GetResponse` с одним `Portfolio` полем.

В этом примере показано объявление метода службы gRPC с сообщением `GetRequest`:

```protobuf
message GetRequest {
    string trader_id = 1;
    int32 portfolio_id = 2;
}

message GetResponse {
    Portfolio portfolio = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (GetResponse);
}
```

Метод `GetAll` WCF принимает только один параметр, `traderId`, поэтому может показаться, что в качестве типа параметра можно указать `string`. Но для gRPC требуется определенный тип сообщений. Это требование позволяет принудительно использовать пользовательские сообщения для всех входных и выходных данных, чтобы обеспечить обратную совместимость.

Метод WCF также возвращает `List<Portfolio>`, но по той же причине он не допускает простые типы параметров, gRPC не допускает `repeated Portfolio` как тип возвращаемого значения. Вместо этого создайте тип `GetAllResponse` для заключения в список.

> [!WARNING]
> Возможно, вы можете создать `PortfolioList` сообщение или нечто похожее и использовать его в нескольких методах службы, но вы должны быть бесискушенияными. Невозможно понять, как будут развиваться различные методы в службе, чтобы обеспечить их конкретную и четко разделенную.

```protobuf
message GetAllRequest {
    string trader_id = 1;
}

message PortfolioList {
    repeated Portfolio portfolios = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (Portfolio);
    rpc GetAll(GetAllRequest) returns (GetAllResponse);
}
```

Если сохранить проект с этими изменениями, целевой объект сборки gRPC будет выполняться в фоновом режиме и создавать все типы сообщений protobuf и базовый класс, который можно унаследовать для реализации службы.

Откройте класс `Services/GreeterService.cs` и удалите код примера. Теперь можно добавить реализацию службы портфеля. Созданный базовый класс будет находиться в пространстве имен `Protos` и создан как вложенный класс. gRPC создает статический класс с тем же именем, что и служба в файле `.proto`, и базовый класс с суффиксом `Base` внутри этого статического класса, поэтому полный идентификатор для базового типа — `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

Базовый класс объявляет `virtual` методы для `Get` и `GetAll`, которые могут быть переопределены для реализации службы. Методы `virtual`, а не `abstract` поэтому, если их не реализовать, служба может возвращать явный код состояния `Unimplemented` gRPC, подобно тому, что вы можете создать `NotImplementedException` в обычном C# коде.

Сигнатура для всех методов унарной службы gRPC в ASP.NET Core является единообразной. Существует два параметра: первый — тип сообщения, объявленный в файле `.proto`, второй — `ServerCallContext`, который работает аналогично `HttpContext` из ASP.NET Core. На самом деле, существует метод расширения, именуемый `GetHttpContext` класса `ServerCallContext`, который можно использовать для получения базовой `HttpContext`, хотя это не должно часто использоваться. Мы рассмотрим `ServerCallContext` далее в этой главе, а также в главе, посвященной проверке подлинности.

Тип возвращаемого значения метода — это `Task<T>`, где `T` является типом ответного сообщения. Все методы службы gRPC являются асинхронными.

## <a name="migrate-the-portfoliodata-library-to-net-core"></a>Миграция библиотеки Портфолиодата в .NET Core

На этом этапе проекту требуется репозиторий портфеля и модели, содержащиеся в библиотеке классов `TraderSys.PortfolioData` в решении WCF. Самый простой способ сделать это — создать новую библиотеку классов с помощью диалогового окна **Новый проект** Visual Studio с шаблоном библиотеки классов (.NET Standard) или из командной строки с помощью .NET Core CLI запуска этих команд из каталога, содержащего файл `TraderSys.sln`:

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

После создания библиотеки и добавления ее в решение удалите созданный файл `Class1.cs` и скопируйте файлы из библиотеки решения WCF в папку новой библиотеки классов, сохранив структуру папок:

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

Проекты .NET в стиле пакета SDK автоматически включают в себя любые `.cs` файлы в или в собственном каталоге, поэтому не нужно явно добавлять их в проект. Осталось только удалить `DataContract` и `DataMember` атрибуты из классов `Portfolio` и `PortfolioItem`, чтобы они были простыми старыми C# классами:

```csharp
public class Portfolio
{
    public int Id { get; set; }
    public Guid TraderId { get; set; }
    public List<PortfolioItem> Items { get; set; }
}

public class PortfolioItem
{
    public int Id { get; set; }
    public int ShareId { get; set; }
    public int Holding { get; set; }
    public decimal Cost { get; set; }
}
```

## <a name="use-aspnet-core-dependency-injection"></a>Использование внедрения зависимостей ASP.NET Core

Теперь можно добавить ссылку на эту библиотеку в проект приложения gRPC и использовать класс `PortfolioRepository` с помощью внедрения зависимостей в реализации службы gRPC. В приложении WCF внедрение зависимостей было предоставлено контейнером IoC Autofac. ASP.NET Core помогут с внедрением зависимостей в. Зарегистрировать репозиторий можно в методе `ConfigureServices` класса `Startup`:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Register the repository class as a scoped service (instance per request)
        services.AddScoped<IPortfolioRepository, PortfolioRepository>();

        services.AddGrpc();
    }

    // ...
}
```

Теперь можно указать `IPortfolioRepository` реализацию в качестве параметра конструктора в классе `PortfolioService`, как показано ниже.

```csharp
public class PortfolioService : Protos.Portfolios.PortfoliosBase
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }
}
```

## <a name="implement-the-grpc-service"></a>Реализация службы gRPC

Теперь, когда вы объявили сообщения и службу в файле `portfolios.proto`, необходимо реализовать методы службы в классе `PortfolioService`, который наследуется от класса `Portfolios.PortfoliosBase`, созданного gRPC. Методы объявляются как `virtual` в базовом классе. Если вы не переопределяете их, они возвращают код состояния gRPC "не реализован" по умолчанию.

Начните с реализации метода `Get`. Переопределение по умолчанию выглядит следующим образом:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

Первая проблема заключается в том, что `request.TraderId` является строкой, а для службы требуется `Guid`. Несмотря на то, что ожидаемый формат строки `UUID`, код должен иметь дело с возможностью, когда вызывающий объект отправил недопустимое значение и отвечал соответствующим образом. Служба может реагировать на ошибки, вызывая `RpcException` и использовать стандартный код состояния `InvalidArgument` для выражения проблемы:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    return base.Get(request, context);
}
```

После получения верного значения `Guid` для `traderId`можно использовать репозиторий, чтобы получить портфель и вернуть его клиенту:

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a>Сопоставьте внутренние модели с gRPC сообщениями

Предыдущий код не работает, так как репозиторий возвращает собственную модель POCO `Portfolio`, но для gRPC требуется собственное сообщение protobuf `Portfolio`. Как и при сопоставлении типов Entity Framework с типами передачи данных, лучшим решением будет обеспечение преобразования между ними. Поместите код для этого преобразования в создаваемый protobuf класс, который объявлен как класс `partial`, чтобы его можно было расширить:

```csharp
namespace TraderSys.Portfolios.Protos
{
    public partial class PortfolioItem
    {
        public static PortfolioItem FromRepositoryModel(PortfolioData.Models.PortfolioItem source)
        {
            if (source is null) return null;

            return new PortfolioItem
            {
                Id = source.Id,
                ShareId = source.ShareId,
                Holding = source.Holding,
                CostCents = (int)(source.Cost * 100)
            };
        }
    }

    public partial class Portfolio
    {
        public static Portfolio FromRepositoryModel(PortfolioData.Models.Portfolio source)
        {
            if (source is null) return null;

            var target = new Portfolio
            {
                Id = source.Id,
                TraderId = source.TraderId.ToString(),
            };

            target.Items.AddRange(source.Items.Select(PortfolioItem.FromRepositoryModel));

            return target;
        }
    }
}
```

> [!NOTE]
> Можно использовать библиотеку [, например Автопреобразование, для](https://automapper.org/) обработки преобразования из внутренних классов модели в типы protobuf, если вы настроили преобразования типов нижнего уровня, такие как `string`/`Guid` или `decimal`/`double` и сопоставление списка.

Теперь, когда имеется код преобразования, можно выполнить реализацию `Get` метода:

```csharp
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}

```

Реализация метода `GetAll` аналогична. Обратите внимание, что поля `repeated` в сообщениях protobuf создаются как `readonly` свойства типа `RepeatedField<T>`, поэтому необходимо добавить элементы в них с помощью метода `AddRange`, как в следующем примере:

```csharp
public override async Task<GetAllResponse> GetAll(GetAllRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolios = await _repository.GetAllAsync(traderId);

    var response = new GetAllResponse();
    response.Portfolios.AddRange(portfolios.Select(Portfolio.FromRepositoryModel));

    return response;
}
```

После успешного переноса службы WCF "запрос — ответ" в gRPC рассмотрим создание клиента для него из файла `.proto`.

## <a name="generate-client-code"></a>Создание клиентского кода

Создайте .NET Standard библиотеку классов в том же решении, в котором будет содержаться клиент. Это, в первую очередь, пример создания клиентского кода, но можно упаковать такую библиотеку с помощью NuGet и распространить ее во внутреннем репозитории для использования другими командами .NET. Добавьте новую библиотеку классов .NET Standard с именем `TraderSys.Portfolios.Client` в решение и удалите файл `Class1.cs`.

> [!CAUTION]
> Для пакета NuGet [.NET. Client GRPC](https://www.nuget.org/packages/Grpc.Net.Client) требуется .net Core 3,0 (или другая .NET Standard 2,1-совместимая среда выполнения). Более ранние версии .NET Framework и .NET Core поддерживаются пакетом NuGet [GRPC. Core](https://www.nuget.org/packages/Grpc.Core) .

В Visual Studio 2019 можно добавить ссылки на службы gRPC так же, как вы добавите ссылки на службы в проекты WCF в более ранних версиях Visual Studio. Ссылки на службы и подключенные службы управляются в одном пользовательском интерфейсе. Чтобы получить доступ к пользовательскому интерфейсу, щелкните правой кнопкой мыши узел **зависимости** в проекте `TraderSys.Portfolios.Client` в Обозреватель решений и выберите команду **Добавить подключенную службу**. В появившемся окне инструментов выберите раздел ссылки на **службу** , а затем щелкните **Добавить новую ссылку на службу gRPC**:

![Подключенные службы пользовательский интерфейс в Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

Перейдите к файлу `portfolios.proto` в проекте `TraderSys.Portfolios`, оставьте **клиент** в разделе **выберите тип создаваемого класса**и нажмите кнопку **ОК**.

![Диалоговое окно "Добавление новой ссылки на службу gRPC" в Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> Обратите внимание, что в этом диалоговом окне также есть поле URL-адреса. Если ваша организация поддерживает доступ к веб-каталогу `.proto` файлов, можно создать клиенты, просто задав этот URL-адрес.

При использовании компонента Visual Studio **Add Connected Service** файл `portfolios.proto` добавляется в проект библиотеки классов как *связанный файл* , а не копируется, поэтому изменения в файле проекта службы будут автоматически применены в клиентском проекте. Элемент `<Protobuf>` в файле `csproj` выглядит следующим образом:

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> Если вы не используете Visual Studio или предпочитаете работать из командной строки, можно использовать глобальное средство `dotnet-grpc` для управления ссылками protobuf в проекте .NET gRPC. Дополнительные сведения см. в [документации по`dotnet-grpc`](/aspnet/core/grpc/dotnet-grpc).

### <a name="use-the-portfolios-service-from-a-client-application"></a>Использование службы "портфолио" из клиентского приложения

Следующий код является кратким примером использования созданного клиента в консольном приложении. Более подробное изучение кода клиента gRPC находится в конце этой главы.

```csharp
public class Program
{
    public async Task Main(string[] args)
    {
        GetResponse response;

        using (var channel = GrpcChannel.ForAddress("https://localhost:5001"))
        {
            var client = new Protos.Portfolios.PortfoliosClient(channel);

            response = await client.GetAsync(new GetRequest
            {
                TraderId = args[0],
                PortfolioId = int.Parse(args[1])
            });
        }

        foreach (var item in response.Portfolio.Items)
        {
            Console.WriteLine($"Holding {item.Holding} of Share ID {item.ShareId}.");
        }
    }
}
```

Теперь вы перенесли базовое приложение WCF в службу ASP.NET Core gRPC и создали клиент для использования службы из приложения .NET. В следующем разделе будут рассмотрены более используемые Дуплексные службы.

>[!div class="step-by-step"]
>[Назад](create-project.md)
>[Вперед](migrate-duplex-services.md)
