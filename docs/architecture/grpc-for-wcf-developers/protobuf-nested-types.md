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
# <a name="protobuf-nested-types"></a><span data-ttu-id="23871-103">Вложенные типы Protobuf</span><span class="sxs-lookup"><span data-stu-id="23871-103">Protobuf nested types</span></span>

<span data-ttu-id="23871-104">Точно так C# же, как позволяет объявлять классы внутри других классов, protobuf позволяет вкладывать определения сообщений в другие сообщения.</span><span class="sxs-lookup"><span data-stu-id="23871-104">Just like C# allows you to declare classes inside other classes, Protobuf allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="23871-105">В следующем примере показано, как создать вложенные типы сообщений.</span><span class="sxs-lookup"><span data-stu-id="23871-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="23871-106">В созданном C# коде тип `Inner` будет объявлен во вложенном статическом `Types` классе в классе `HelloRequest`:</span><span class="sxs-lookup"><span data-stu-id="23871-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="23871-107">[Назад](protobuf-data-types.md)
>[Вперед](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="23871-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
