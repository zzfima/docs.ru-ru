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
# <a name="protobuf-nested-types"></a><span data-ttu-id="eece8-103">Вложенные типы Protobuf</span><span class="sxs-lookup"><span data-stu-id="eece8-103">Protobuf nested types</span></span>

<span data-ttu-id="eece8-104">Точно так C# же, как позволяет объявлять классы внутри других классов, буфер протокола (protobuf) позволяет вкладывать определения сообщений в другие сообщения.</span><span class="sxs-lookup"><span data-stu-id="eece8-104">Just as C# allows you to declare classes inside other classes, Protocol Buffer (Protobuf) allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="eece8-105">В следующем примере показано, как создать вложенные типы сообщений.</span><span class="sxs-lookup"><span data-stu-id="eece8-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="eece8-106">В созданном C# коде тип `Inner` будет объявлен во вложенном статическом `Types` классе в классе `HelloRequest`:</span><span class="sxs-lookup"><span data-stu-id="eece8-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="eece8-107">[Назад](protobuf-data-types.md)
>[Вперед](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="eece8-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
