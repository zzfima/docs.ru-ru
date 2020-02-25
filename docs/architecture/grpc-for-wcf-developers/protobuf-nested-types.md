---
title: Вложенные типы protobuf — gRPC для разработчиков WCF
description: Сведения о вложенных типах сообщений в protobuf и gRPC, а также о способах их создания в C#.
ms.date: 09/09/2019
ms.openlocfilehash: 7b9a331336ebe1ca7bc75fdd164b7b88ae4f9db2
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542850"
---
# <a name="protobuf-nested-types"></a>Вложенные типы Protobuf

Точно так C# же, как позволяет объявлять классы внутри других классов, буфер протокола (protobuf) позволяет вкладывать определения сообщений в другие сообщения. В следующем примере показано, как создать вложенные типы сообщений.

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
