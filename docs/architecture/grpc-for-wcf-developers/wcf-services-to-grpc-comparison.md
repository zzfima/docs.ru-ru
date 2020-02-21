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
# <a name="comparing-wcf-to-grpc"></a>Сравнение WCF и gRPC

В предыдущей главе вы узнаете о protobuf и том, как gRPC обрабатывает сообщения. Прежде чем выполнять подробное преобразование из Windows Communication Foundation (WCF) в gRPC, важно понять, как функции, доступные в WCF, обрабатываются в gRPC и какие обходные пути можно использовать при отсутствии эквивалента gRPC. В частности, в этой главе рассматриваются следующие темы:

- Операции и методы
- Привязки и транспорты
- Типы RPC
- Метаданные
- Обработка ошибок
- Протоколы WS-\*

## <a name="grpc-example"></a>Пример gRPC

При создании нового проекта ASP.NET Core 3,0 gRPC из Visual Studio 2019 или командной строки для вас создается gRPC эквивалент "Hello World". Он состоит из `greeter.proto` файла, определяющего службу и ее сообщения, а также `GreeterService.cs` файл с реализацией службы.

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

В этой главе мы рассмотрим этот пример кода при объяснении различных концепций и функций gRPC.

>[!div class="step-by-step"]
>[Назад](protobuf-maps.md)
>[Вперед](wcf-endpoints-grpc-methods.md)
