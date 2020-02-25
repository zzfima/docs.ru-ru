---
title: Повторяющиеся поля для списков и массивов — gRPC для разработчиков WCF
description: Узнайте, как protobuf обрабатывает коллекции и как они связаны с коллекциями .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542963"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="d781e-103">Повторяющиеся поля для списков и массивов</span><span class="sxs-lookup"><span data-stu-id="d781e-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="d781e-104">Списки в буфере протокола (protobuf) указываются с помощью ключевого слова prefix `repeated`.</span><span class="sxs-lookup"><span data-stu-id="d781e-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="d781e-105">В следующем примере показано, как создать список.</span><span class="sxs-lookup"><span data-stu-id="d781e-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="d781e-106">В созданном коде `repeated` поля представлены `Google.Protobuf.Collections.RepeatedField<T>` универсальным типом, а не любым из встроенных типов коллекций .NET.</span><span class="sxs-lookup"><span data-stu-id="d781e-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> 

<span data-ttu-id="d781e-107">Тип `RepeatedField<T>` включает код, необходимый для сериализации и десериализации списка в двоичный формат сети.</span><span class="sxs-lookup"><span data-stu-id="d781e-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="d781e-108">Он реализует все стандартные интерфейсы коллекции .NET, такие как <xref:System.Collections.Generic.IList%601> и <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d781e-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="d781e-109">Поэтому можно легко использовать запросы LINQ или преобразовать их в массив или список.</span><span class="sxs-lookup"><span data-stu-id="d781e-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d781e-110">[Назад](protobuf-nested-types.md)
>[Вперед](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="d781e-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
