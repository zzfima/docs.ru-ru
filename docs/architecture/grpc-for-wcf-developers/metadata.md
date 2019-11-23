---
title: Метаданные — gRPC для разработчиков WCF
description: Использование метаданных в gRPC для передачи дополнительного контекста между клиентами и серверами
ms.date: 09/02/2019
ms.openlocfilehash: 723d877bfbf0c2b0785949ff15939aedbac4d4e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971976"
---
# <a name="metadata"></a>Метаданные

"Метаданные" относятся к дополнительным данным, которые могут быть полезны при обработке запросов и ответов, но не являются частью фактических данных приложения. Метаданные могут включать маркеры проверки подлинности, идентификаторы запросов и теги для целей мониторинга, а также сведения о данных, например число записей в наборе данных.

Можно добавить общие заголовки ключа/значения в сообщения WCF с помощью <xref:System.ServiceModel.OperationContextScope> и свойства <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> и обработайте их с помощью <xref:System.ServiceModel.Channels.MessageProperties>.

вызовы gRPC и ответы также могут содержать метаданные, аналогичные заголовкам HTTP. Они в основном невидимы для gRPC и передаются для обработки кодом приложения или по промежуточного слоя. Метаданные представляются в виде пар "ключ-значение", в которых ключ является строкой, а значение — строкой или двоичными данными. Не нужно указывать метаданные в файле `.proto`.

Метаданные обрабатываются с помощью класса `Metadata` из пакета NuGet [GRPC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) . Этот класс можно использовать с синтаксисом инициализатора коллекции.

В следующем примере показано, как добавить метаданные в вызов из C# клиента.

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

Службы могут отсылать метаданные клиентам с помощью свойства `ResponseTrailers` `ServerCallContext`:

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
