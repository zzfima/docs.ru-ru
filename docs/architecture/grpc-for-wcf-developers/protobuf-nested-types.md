---
title: Вложенные типы protobuf — gRPC для разработчиков WCF
description: Сведения о вложенных типах сообщений в protobuf и gRPC, а также о способах их создания в C#.
ms.date: 09/09/2019
ms.openlocfilehash: bbc7ed41516d29f867bbc9da5b258f6a3c9ff261
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967388"
---
# <a name="protobuf-nested-types"></a>Вложенные типы Protobuf

Точно так C# же, как позволяет объявлять классы внутри других классов, protobuf позволяет вкладывать определения сообщений в другие сообщения. В следующем примере показано, как создать вложенные типы сообщений.

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

В созданном C# коде тип `Inner` будет объявлен во вложенном статическом `Types` классе в классе `HelloRequest`:

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[Назад](protobuf-data-types.md)
>[Вперед](protobuf-repeated.md)
