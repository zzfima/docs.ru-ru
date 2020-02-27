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
# <a name="metadata"></a><span data-ttu-id="3533a-103">Метаданные</span><span class="sxs-lookup"><span data-stu-id="3533a-103">Metadata</span></span>

<span data-ttu-id="3533a-104">*Метаданные* — это дополнительные данные, которые могут быть полезны во время обработки запросов и ответов, но не являются частью реальных данных приложения.</span><span class="sxs-lookup"><span data-stu-id="3533a-104">*Metadata* refers to additional data that might be useful during the processing of requests and responses but that’s not part of the actual application data.</span></span> <span data-ttu-id="3533a-105">Метаданные могут включать маркеры проверки подлинности, идентификаторы запросов и теги для целей мониторинга, а также сведения о данных, например число записей в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="3533a-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, and information about the data, like the number of records in a dataset.</span></span>

<span data-ttu-id="3533a-106">Можно добавить общие заголовки "ключ-значение" в Windows Communication Foundation сообщения (WCF) с помощью <xref:System.ServiceModel.OperationContextScope> и свойства <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> и обработайте их с помощью <xref:System.ServiceModel.Channels.MessageProperties>.</span><span class="sxs-lookup"><span data-stu-id="3533a-106">It's possible to add generic key/value headers to Windows Communication Foundation (WCF) messages by using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property and handle them by using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="3533a-107">вызовы gRPC и ответы также могут включать метаданные, похожие на заголовки HTTP.</span><span class="sxs-lookup"><span data-stu-id="3533a-107">gRPC calls and responses can also include metadata that's similar to HTTP headers.</span></span> <span data-ttu-id="3533a-108">Эти метаданные в основном невидимы для gRPC и передаются для обработки кодом приложения или по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="3533a-108">This metadata is mostly invisible to gRPC itself and is passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="3533a-109">Метаданные представляются в виде пар "ключ-значение", где ключ является строкой, а значение — строкой или двоичными данными.</span><span class="sxs-lookup"><span data-stu-id="3533a-109">Metadata is represented as key/value pairs, where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="3533a-110">Не нужно указывать метаданные в файле `.proto`.</span><span class="sxs-lookup"><span data-stu-id="3533a-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="3533a-111">Метаданные обрабатываются классом `Metadata` пакета NuGet [GRPC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) .</span><span class="sxs-lookup"><span data-stu-id="3533a-111">Metadata is handled by the `Metadata` class of the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="3533a-112">Этот класс можно использовать с синтаксисом инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="3533a-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="3533a-113">В этом примере показано, как добавить метаданные в вызов из C# клиента.</span><span class="sxs-lookup"><span data-stu-id="3533a-113">This example shows how to add metadata to a call from a C# client:</span></span>

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

<span data-ttu-id="3533a-114">gRPC Services могут обращаться к метаданным из свойства `RequestHeaders` аргумента `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="3533a-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

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

<span data-ttu-id="3533a-115">Службы могут отсылать метаданные клиентам с помощью свойства `ResponseTrailers` `ServerCallContext`.</span><span class="sxs-lookup"><span data-stu-id="3533a-115">Services can send metadata to clients by using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="3533a-116">[Назад](rpc-types.md)
>[Вперед](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="3533a-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
