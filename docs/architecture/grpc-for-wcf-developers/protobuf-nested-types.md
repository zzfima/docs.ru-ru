---
title: Вложенные типы protobuf — gRPC для разработчиков WCF
description: Сведения о вложенных типах сообщений в protobuf и gRPC, а также о способах их создания в C#.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: ec9fc522619230c1201bfef1e8128f7356936212
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841405"
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
