---
title: Обработка ошибок — gRPC для разработчиков WCF
description: Темы, относящиеся к обработке ошибок в gRPC. Включает таблицу наиболее часто используемых кодов состояния.
ms.date: 09/02/2019
ms.openlocfilehash: c380c651f854adc97e8b2ead36d30c3b83662aac
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542797"
---
# <a name="error-handling"></a><span data-ttu-id="50cf0-104">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="50cf0-104">Error handling</span></span>

<span data-ttu-id="50cf0-105">Windows Communication Foundation (WCF) использует <xref:System.ServiceModel.FaultException%601> и [фаултконтракт](xref:System.ServiceModel.FaultContractAttribute) для предоставления подробных сведений об ошибках, включая поддержку стандарта SOAP Fault.</span><span class="sxs-lookup"><span data-stu-id="50cf0-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="50cf0-106">К сожалению, в текущей версии gRPC отсутствует платформа, найденная в WCF, и имеется ограниченная встроенная обработка ошибок на основе простых кодов состояния и метаданных.</span><span class="sxs-lookup"><span data-stu-id="50cf0-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="50cf0-107">В следующей таблице приведено краткое руководство по наиболее часто используемым кодам состояния:</span><span class="sxs-lookup"><span data-stu-id="50cf0-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="50cf0-108">Код состояния</span><span class="sxs-lookup"><span data-stu-id="50cf0-108">Status code</span></span> | <span data-ttu-id="50cf0-109">Проблема</span><span class="sxs-lookup"><span data-stu-id="50cf0-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="50cf0-110">Метод не был записан.</span><span class="sxs-lookup"><span data-stu-id="50cf0-110">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="50cf0-111">Проблема со всей службой.</span><span class="sxs-lookup"><span data-stu-id="50cf0-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="50cf0-112">Недопустимый ответ.</span><span class="sxs-lookup"><span data-stu-id="50cf0-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="50cf0-113">Проблема с кодированием и декодированием.</span><span class="sxs-lookup"><span data-stu-id="50cf0-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="50cf0-114">Ошибка проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="50cf0-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="50cf0-115">Ошибка авторизации.</span><span class="sxs-lookup"><span data-stu-id="50cf0-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="50cf0-116">Вызов был отменен (обычно вызывающей стороной).</span><span class="sxs-lookup"><span data-stu-id="50cf0-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="50cf0-117">Вызвать ошибки в ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="50cf0-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="50cf0-118">Служба ASP.NET Core gRPC может отправить ответ об ошибке, вызывая `RpcException`, который может быть перехвачен клиентом, как если бы он находился в том же процессе.</span><span class="sxs-lookup"><span data-stu-id="50cf0-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="50cf0-119">`RpcException` должен включать код состояния и описание, а также может содержать метаданные и более длинное сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="50cf0-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="50cf0-120">Метаданные можно использовать для отправки вспомогательных данных аналогично тому, как `FaultContract` объекты могут содержать дополнительные данные для ошибок WCF.</span><span class="sxs-lookup"><span data-stu-id="50cf0-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="50cf0-121">Перехват ошибок в клиентах gRPC</span><span class="sxs-lookup"><span data-stu-id="50cf0-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="50cf0-122">Так же, как клиенты WCF могут перехватывать ошибки <xref:System.ServiceModel.FaultException%601>, клиент gRPC может перехватить `RpcException`, чтобы обрабатывались ошибки.</span><span class="sxs-lookup"><span data-stu-id="50cf0-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="50cf0-123">Поскольку `RpcException` не является универсальным типом, нельзя перехватывать различные типы ошибок в разных блоках.</span><span class="sxs-lookup"><span data-stu-id="50cf0-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="50cf0-124">Однако можно использовать C#функции *фильтров исключений* , чтобы объявить отдельные блоки `catch` для различных кодов состояния, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="50cf0-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> <span data-ttu-id="50cf0-125">При предоставлении дополнительных метаданных об ошибках обязательно задокументируйте соответствующие ключи и значения в документации по API или комментарии в файле `.proto`.</span><span class="sxs-lookup"><span data-stu-id="50cf0-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="50cf0-126">gRPC Расширенная модель ошибок</span><span class="sxs-lookup"><span data-stu-id="50cf0-126">gRPC richer error model</span></span>

<span data-ttu-id="50cf0-127">Google разработал более [обширную модель ошибок](https://cloud.google.com/apis/design/errors#error_model) , которая более похожа на [фаултконтракт](xref:System.ServiceModel.FaultContractAttribute)WCF, но эта модель C# пока не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="50cf0-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="50cf0-128">В настоящее время он доступен только для Go, Java, Python и C++.</span><span class="sxs-lookup"><span data-stu-id="50cf0-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="50cf0-129">[Назад](metadata.md)
>[Вперед](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="50cf0-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
