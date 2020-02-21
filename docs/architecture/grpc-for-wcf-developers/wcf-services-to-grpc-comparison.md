---
title: Сравнение WCF с gRPC-gRPC для разработчиков WCF
description: Сравнение платформ WCF и gRPC для создания распределенных приложений.
ms.date: 09/02/2019
ms.openlocfilehash: 4f54db76c9512b770b4dd993496d95437dd89753
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503334"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="0cdf2-103">Сравнение WCF и gRPC</span><span class="sxs-lookup"><span data-stu-id="0cdf2-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="0cdf2-104">В предыдущей главе вы узнаете о protobuf и том, как gRPC обрабатывает сообщения.</span><span class="sxs-lookup"><span data-stu-id="0cdf2-104">The previous chapter gave you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="0cdf2-105">Прежде чем выполнять подробное преобразование из Windows Communication Foundation (WCF) в gRPC, важно понять, как функции, доступные в WCF, обрабатываются в gRPC и какие обходные пути можно использовать при отсутствии эквивалента gRPC.</span><span class="sxs-lookup"><span data-stu-id="0cdf2-105">Before you work through a detailed conversion from Windows Communication Foundation (WCF) to gRPC, it's important know how the features available in WCF are handled in gRPC and what workarounds you can use when there's no gRPC equivalent.</span></span> <span data-ttu-id="0cdf2-106">В частности, в этой главе рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="0cdf2-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="0cdf2-107">Операции и методы</span><span class="sxs-lookup"><span data-stu-id="0cdf2-107">Operations and methods</span></span>
- <span data-ttu-id="0cdf2-108">Привязки и транспорты</span><span class="sxs-lookup"><span data-stu-id="0cdf2-108">Bindings and transports</span></span>
- <span data-ttu-id="0cdf2-109">Типы RPC</span><span class="sxs-lookup"><span data-stu-id="0cdf2-109">RPC types</span></span>
- <span data-ttu-id="0cdf2-110">Метаданные</span><span class="sxs-lookup"><span data-stu-id="0cdf2-110">Metadata</span></span>
- <span data-ttu-id="0cdf2-111">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="0cdf2-111">Error handling</span></span>
- <span data-ttu-id="0cdf2-112">Протоколы WS-\*</span><span class="sxs-lookup"><span data-stu-id="0cdf2-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="0cdf2-113">Пример gRPC</span><span class="sxs-lookup"><span data-stu-id="0cdf2-113">gRPC example</span></span>

<span data-ttu-id="0cdf2-114">При создании нового проекта ASP.NET Core 3,0 gRPC из Visual Studio 2019 или командной строки для вас создается gRPC эквивалент "Hello World".</span><span class="sxs-lookup"><span data-stu-id="0cdf2-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="0cdf2-115">Он состоит из `greeter.proto` файла, определяющего службу и ее сообщения, а также `GreeterService.cs` файл с реализацией службы.</span><span class="sxs-lookup"><span data-stu-id="0cdf2-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

<span data-ttu-id="0cdf2-116">В этой главе мы рассмотрим этот пример кода при объяснении различных концепций и функций gRPC.</span><span class="sxs-lookup"><span data-stu-id="0cdf2-116">This chapter will refer to this example code when explaining different concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0cdf2-117">[Назад](protobuf-maps.md)
>[Вперед](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="0cdf2-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
