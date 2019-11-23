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
# <a name="metadata"></a><span data-ttu-id="6162f-103">Метаданные</span><span class="sxs-lookup"><span data-stu-id="6162f-103">Metadata</span></span>

<span data-ttu-id="6162f-104">"Метаданные" относятся к дополнительным данным, которые могут быть полезны при обработке запросов и ответов, но не являются частью фактических данных приложения.</span><span class="sxs-lookup"><span data-stu-id="6162f-104">"Metadata" refers to additional data that may be useful while processing requests and responses but is not part of the actual application data.</span></span> <span data-ttu-id="6162f-105">Метаданные могут включать маркеры проверки подлинности, идентификаторы запросов и теги для целей мониторинга, а также сведения о данных, например число записей в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="6162f-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, or information about the data like the number of records in a dataset.</span></span>

<span data-ttu-id="6162f-106">Можно добавить общие заголовки ключа/значения в сообщения WCF с помощью <xref:System.ServiceModel.OperationContextScope> и свойства <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> и обработайте их с помощью <xref:System.ServiceModel.Channels.MessageProperties>.</span><span class="sxs-lookup"><span data-stu-id="6162f-106">It's possible to add generic key/value headers to WCF messages using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property, and handle them using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="6162f-107">вызовы gRPC и ответы также могут содержать метаданные, аналогичные заголовкам HTTP.</span><span class="sxs-lookup"><span data-stu-id="6162f-107">gRPC calls and responses can also include metadata similar to HTTP headers.</span></span> <span data-ttu-id="6162f-108">Они в основном невидимы для gRPC и передаются для обработки кодом приложения или по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="6162f-108">These are mostly invisible to gRPC itself and are passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="6162f-109">Метаданные представляются в виде пар "ключ-значение", в которых ключ является строкой, а значение — строкой или двоичными данными.</span><span class="sxs-lookup"><span data-stu-id="6162f-109">Metadata is represented as key/value pairs where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="6162f-110">Не нужно указывать метаданные в файле `.proto`.</span><span class="sxs-lookup"><span data-stu-id="6162f-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="6162f-111">Метаданные обрабатываются с помощью класса `Metadata` из пакета NuGet [GRPC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) .</span><span class="sxs-lookup"><span data-stu-id="6162f-111">Metadata is handled using the `Metadata` class from the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="6162f-112">Этот класс можно использовать с синтаксисом инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="6162f-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="6162f-113">В следующем примере показано, как добавить метаданные в вызов из C# клиента.</span><span class="sxs-lookup"><span data-stu-id="6162f-113">The following example shows how to add metadata to a call from a C# client:</span></span>

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

<span data-ttu-id="6162f-114">gRPC Services могут обращаться к метаданным из свойства `RequestHeaders` аргумента `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="6162f-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

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

<span data-ttu-id="6162f-115">Службы могут отсылать метаданные клиентам с помощью свойства `ResponseTrailers` `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="6162f-115">Services can send metadata to clients using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="6162f-116">[Назад](rpc-types.md)
>[Вперед](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="6162f-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
