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
# <a name="comparing-wcf-to-grpc"></a>Сравнение WCF и gRPC

В предыдущем разделе вы должны были получить хорошее представление о protobuf и о том, как gRPC обрабатывает сообщения. Прежде чем выполнять подробное преобразование из WCF в gRPC, важно обратить внимание на то, как диапазон функций, доступных в WCF в настоящее время, будет обрабатываться в gRPC и какие обходные пути можно использовать, если они не являются gRPC эквивалентами. В частности, в этой главе рассматриваются следующие темы:

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

В этой главе мы рассмотрим этот пример кода при объяснении различных концепций и функций gRPC.

>[!div class="step-by-step"]
>[Назад](protobuf-maps.md)
>[Вперед](wcf-endpoints-grpc-methods.md)
