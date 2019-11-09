---
title: Повторяющиеся поля для списков и массивов — gRPC для разработчиков WCF
description: Узнайте, как коллекции обрабатываются protobuf и как они связаны с коллекциями .NET.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 740af8af39af9bf31be17ad831f481176e30d81f
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841399"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="4ae57-103">Повторяющиеся поля для списков и массивов</span><span class="sxs-lookup"><span data-stu-id="4ae57-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="4ae57-104">Списки указываются в protobuf с помощью ключевого слова `repeated` prefix.</span><span class="sxs-lookup"><span data-stu-id="4ae57-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="4ae57-105">В следующем примере показано, как создать список.</span><span class="sxs-lookup"><span data-stu-id="4ae57-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="4ae57-106">В созданном коде `repeated` поля представлены `Google.Protobuf.Collections.RepeatedField<T>` универсальным типом, а не любым из встроенных типов коллекций .NET.</span><span class="sxs-lookup"><span data-stu-id="4ae57-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="4ae57-107">Тип `RepeatedField<T>` включает код, необходимый для сериализации и десериализации списка в двоичный формат сети.</span><span class="sxs-lookup"><span data-stu-id="4ae57-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="4ae57-108">В нем реализованы все стандартные интерфейсы коллекций .NET, такие как <xref:System.Collections.Generic.IList%601> и <xref:System.Collections.Generic.IEnumerable%601>, поэтому можно использовать запросы LINQ или легко преобразовать их в массив или список.</span><span class="sxs-lookup"><span data-stu-id="4ae57-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4ae57-109">[Назад](protobuf-nested-types.md)
>[Вперед](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="4ae57-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
