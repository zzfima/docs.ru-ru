---
title: Сравнение WCF с gRPC-gRPC для разработчиков WCF
description: Сравнение платформ WCF и gRPC для создания распределенных приложений.
ms.date: 09/02/2019
ms.openlocfilehash: 312492dcce4bdef61feff0bf924c6df287b9c676
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966950"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="1ad43-103">Сравнение WCF и gRPC</span><span class="sxs-lookup"><span data-stu-id="1ad43-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="1ad43-104">В предыдущем разделе вы должны были получить хорошее представление о protobuf и о том, как gRPC обрабатывает сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ad43-104">The previous chapter should have given you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="1ad43-105">Прежде чем выполнять подробное преобразование из WCF в gRPC, важно обратить внимание на то, как диапазон функций, доступных в WCF в настоящее время, будет обрабатываться в gRPC и какие обходные пути можно использовать, если они не являются gRPC эквивалентами.</span><span class="sxs-lookup"><span data-stu-id="1ad43-105">Before working through a detailed conversion from WCF to gRPC, it's important to look at how the range of features currently available in WCF are handled in gRPC and what workarounds you can use when there doesn't appear to be a gRPC equivalent.</span></span> <span data-ttu-id="1ad43-106">В частности, в этой главе рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="1ad43-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="1ad43-107">Операции и методы</span><span class="sxs-lookup"><span data-stu-id="1ad43-107">Operations and methods</span></span>
- <span data-ttu-id="1ad43-108">Привязки и транспорты</span><span class="sxs-lookup"><span data-stu-id="1ad43-108">Bindings and transports</span></span>
- <span data-ttu-id="1ad43-109">Типы RPC</span><span class="sxs-lookup"><span data-stu-id="1ad43-109">RPC types</span></span>
- <span data-ttu-id="1ad43-110">Метаданные</span><span class="sxs-lookup"><span data-stu-id="1ad43-110">Metadata</span></span>
- <span data-ttu-id="1ad43-111">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="1ad43-111">Error handling</span></span>
- <span data-ttu-id="1ad43-112">Протоколы WS-\*</span><span class="sxs-lookup"><span data-stu-id="1ad43-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="1ad43-113">Пример gRPC</span><span class="sxs-lookup"><span data-stu-id="1ad43-113">gRPC example</span></span>

<span data-ttu-id="1ad43-114">При создании нового проекта ASP.NET Core 3,0 gRPC из Visual Studio 2019 или командной строки для вас создается gRPC эквивалент "Hello World".</span><span class="sxs-lookup"><span data-stu-id="1ad43-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="1ad43-115">Он состоит из `greeter.proto` файла, определяющего службу и ее сообщения, а также `GreeterService.cs` файл с реализацией службы.</span><span class="sxs-lookup"><span data-stu-id="1ad43-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings.
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

<span data-ttu-id="1ad43-116">В этой главе мы рассмотрим этот пример кода при объяснении различных концепций и функций gRPC.</span><span class="sxs-lookup"><span data-stu-id="1ad43-116">This chapter will refer to this example code when explaining various concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1ad43-117">[Назад](protobuf-maps.md)
>[Вперед](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="1ad43-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
