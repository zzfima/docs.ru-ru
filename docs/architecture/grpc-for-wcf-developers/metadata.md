---
title: Метаданные — gRPC для разработчиков WCF
description: Использование метаданных в gRPC для передачи дополнительного контекста между клиентами и серверами.
ms.date: 09/02/2019
ms.openlocfilehash: 64fa94d1e63af480cbc7363631de161c5b8b8fb8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628583"
---
# <a name="metadata"></a>Метаданные

*Метаданные* — это дополнительные данные, которые могут быть полезны во время обработки запросов и ответов, но не являются частью реальных данных приложения. Метаданные могут включать маркеры проверки подлинности, идентификаторы запросов и теги для целей мониторинга, а также сведения о данных, например число записей в наборе данных.

Можно добавить общие заголовки "ключ-значение" в Windows Communication Foundation сообщения (WCF) с помощью <xref:System.ServiceModel.OperationContextScope> и свойства <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> и обработайте их с помощью <xref:System.ServiceModel.Channels.MessageProperties>.

вызовы gRPC и ответы также могут включать метаданные, похожие на заголовки HTTP. Эти метаданные в основном невидимы для gRPC и передаются для обработки кодом приложения или по промежуточного слоя. Метаданные представляются в виде пар "ключ-значение", где ключ является строкой, а значение — строкой или двоичными данными. Не нужно указывать метаданные в файле `.proto`.

Метаданные обрабатываются классом `Metadata` пакета NuGet [GRPC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) . Этот класс можно использовать с синтаксисом инициализатора коллекции.

В этом примере показано, как добавить метаданные в вызов из C# клиента.

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

gRPC Services могут обращаться к метаданным из свойства `RequestHeaders` аргумента `ServerCallContext`:

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

Службы могут отсылать метаданные клиентам с помощью свойства `ResponseTrailers` `ServerCallContext`.

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
>[Назад](rpc-types.md)
>[Вперед](error-handling.md)
