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
# <a name="error-handling"></a>Обработка ошибок

WCF использует `FaultException<T>` и `FaultContract` для предоставления подробных сведений об ошибках, включая поддержку стандарта SOAP Fault.

К сожалению, в текущей версии gRPC отсутствует платформа, найденная в WCF, и имеется ограниченная встроенная обработка ошибок на основе простых кодов состояния и метаданных. В следующей таблице приведено краткое руководство по наиболее часто используемым кодам состояния:

| Код состояния | Проблема |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | Метод не был записан. |
| `GRPC_STATUS_UNAVAILABLE` | Проблема со всей службой. |
| `GRPC_STATUS_UNKNOWN` | Недопустимый ответ. |
| `GRPC_STATUS_INTERNAL` | Проблема с кодированием и декодированием. |
| `GRPC_STATUS_UNAUTHENTICATED` | Ошибка проверки подлинности. |
| `GRPC_STATUS_PERMISSION_DENIED` | Ошибка авторизации. |
| `GRPC_STATUS_CANCELLED` | Вызов был отменен (обычно вызывающей стороной). |

## <a name="raising-errors-in-aspnet-core-grpc"></a>Возникновение ошибок в ASP.NET Core gRPC

Служба ASP.NET Core gRPC может отправить ответ об ошибке, вызывая `RpcException`, который может быть перехвачен клиентом, как если бы он находился в том же процессе. `RpcException` должен включать код состояния и описание, а также может содержать метаданные и более длинное сообщение об исключении. Метаданные можно использовать для отправки вспомогательных данных аналогично тому, как `FaultContract` объекты могут содержать дополнительные данные для ошибок WCF.

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

## <a name="catching-errors-in-grpc-clients"></a>Перехват ошибок в клиентах gRPC

Так же, как клиенты WCF могут перехватывать ошибки <xref:System.ServiceModel.FaultException%601>, клиент gRPC может перехватить `RpcException`, чтобы обрабатывались ошибки. Поскольку `RpcException` не является универсальным типом, нельзя перехватывать различные типы ошибок в разных блоках, но можно C#использовать функцию *фильтров исключений* , чтобы объявить отдельные блоки `catch` для различных кодов состояния, как показано в следующем примере:

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
> При предоставлении дополнительных метаданных об ошибках обязательно задокументируйте соответствующие ключи и значения в документации по API или комментарии в файле `.proto`.

## <a name="grpc-richer-error-model"></a>gRPC Расширенная модель ошибок

Сейчас Google разработал более [обширную модель ошибок](https://cloud.google.com/apis/design/errors#error_model) , которая более похожа на [фаултконтракт](xref:System.ServiceModel.FaultContractAttribute)WCF, но C# пока не поддерживается. В настоящее время он доступен только для Go, Java, Python и C++, но поддержка для C# должна приходиться на следующий год.

>[!div class="step-by-step"]
>[Назад](metadata.md)
>[Вперед](ws-protocols.md)
