---
title: Обработка ошибок — gRPC для разработчиков WCF
description: Подлежит написанию
ms.date: 09/02/2019
ms.openlocfilehash: 2c44bd9264c877a7c7a86c115b6da9f759006016
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967783"
---
# <a name="error-handling"></a><span data-ttu-id="5e325-103">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="5e325-103">Error handling</span></span>

<span data-ttu-id="5e325-104">WCF использует `FaultException<T>` и `FaultContract` для предоставления подробных сведений об ошибках, включая поддержку стандарта SOAP Fault.</span><span class="sxs-lookup"><span data-stu-id="5e325-104">WCF uses `FaultException<T>` and `FaultContract` to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="5e325-105">К сожалению, в текущей версии gRPC отсутствует платформа, найденная в WCF, и имеется ограниченная встроенная обработка ошибок на основе простых кодов состояния и метаданных.</span><span class="sxs-lookup"><span data-stu-id="5e325-105">Unfortunately, the current version of gRPC lacks the sophistication found with WCF and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="5e325-106">В следующей таблице приведено краткое руководство по наиболее часто используемым кодам состояния:</span><span class="sxs-lookup"><span data-stu-id="5e325-106">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="5e325-107">Код состояния</span><span class="sxs-lookup"><span data-stu-id="5e325-107">Status Code</span></span> | <span data-ttu-id="5e325-108">Проблема</span><span class="sxs-lookup"><span data-stu-id="5e325-108">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="5e325-109">Метод не был записан.</span><span class="sxs-lookup"><span data-stu-id="5e325-109">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="5e325-110">Проблема со всей службой.</span><span class="sxs-lookup"><span data-stu-id="5e325-110">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="5e325-111">Недопустимый ответ.</span><span class="sxs-lookup"><span data-stu-id="5e325-111">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="5e325-112">Проблема с кодированием и декодированием.</span><span class="sxs-lookup"><span data-stu-id="5e325-112">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="5e325-113">Ошибка проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5e325-113">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="5e325-114">Ошибка авторизации.</span><span class="sxs-lookup"><span data-stu-id="5e325-114">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="5e325-115">Вызов был отменен (обычно вызывающей стороной).</span><span class="sxs-lookup"><span data-stu-id="5e325-115">Call was canceled, usually by the caller.</span></span> |

## <a name="raising-errors-in-aspnet-core-grpc"></a><span data-ttu-id="5e325-116">Возникновение ошибок в ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="5e325-116">Raising errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="5e325-117">Служба ASP.NET Core gRPC может отправить ответ об ошибке, вызывая `RpcException`, который может быть перехвачен клиентом, как если бы он находился в том же процессе.</span><span class="sxs-lookup"><span data-stu-id="5e325-117">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="5e325-118">`RpcException` должен включать код состояния и описание, а также может содержать метаданные и более длинное сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="5e325-118">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="5e325-119">Метаданные можно использовать для отправки вспомогательных данных аналогично тому, как `FaultContract` объекты могут содержать дополнительные данные для ошибок WCF.</span><span class="sxs-lookup"><span data-stu-id="5e325-119">The metadata can be used to send supporting data, similar to how `FaultContract` objects could carry additional data for WCF errors.</span></span>

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

## <a name="catching-errors-in-grpc-clients"></a><span data-ttu-id="5e325-120">Перехват ошибок в клиентах gRPC</span><span class="sxs-lookup"><span data-stu-id="5e325-120">Catching errors in gRPC clients</span></span>

<span data-ttu-id="5e325-121">Так же, как клиенты WCF могут перехватывать ошибки <xref:System.ServiceModel.FaultException%601>, клиент gRPC может перехватить `RpcException`, чтобы обрабатывались ошибки.</span><span class="sxs-lookup"><span data-stu-id="5e325-121">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="5e325-122">Поскольку `RpcException` не является универсальным типом, нельзя перехватывать различные типы ошибок в разных блоках, но можно C#использовать функцию *фильтров исключений* , чтобы объявить отдельные блоки `catch` для различных кодов состояния, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5e325-122">Since `RpcException` isn't a generic type, you can't catch different error types in different blocks, but you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="5e325-123">При предоставлении дополнительных метаданных об ошибках обязательно задокументируйте соответствующие ключи и значения в документации по API или комментарии в файле `.proto`.</span><span class="sxs-lookup"><span data-stu-id="5e325-123">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="5e325-124">gRPC Расширенная модель ошибок</span><span class="sxs-lookup"><span data-stu-id="5e325-124">gRPC Richer Error Model</span></span>

<span data-ttu-id="5e325-125">Сейчас Google разработал более [обширную модель ошибок](https://cloud.google.com/apis/design/errors#error_model) , которая более похожа на [фаултконтракт](xref:System.ServiceModel.FaultContractAttribute)WCF, но C# пока не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5e325-125">Looking ahead, Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that is more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but isn't supported in C# yet.</span></span> <span data-ttu-id="5e325-126">В настоящее время он доступен только для Go, Java, Python и C++, но поддержка для C# должна приходиться на следующий год.</span><span class="sxs-lookup"><span data-stu-id="5e325-126">Currently, it's only available for Go, Java, Python and C++, but support for C# is expected to come next year.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5e325-127">[Назад](metadata.md)
>[Вперед](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="5e325-127">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
