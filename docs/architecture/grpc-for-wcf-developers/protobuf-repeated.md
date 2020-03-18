---
title: Повторные поля для списков и массивов - gRPC для разработчиков WCF
description: Понять, как Protobuf обрабатывает коллекции и как они связаны с коллекциями .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 63d99532d14deea7800673dd5a6350dd9362ad54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147975"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="62ed6-103">Повторяющиеся поля для списков и массивов</span><span class="sxs-lookup"><span data-stu-id="62ed6-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="62ed6-104">Вы указываете списки в Протоколе Буфер `repeated` (Protobuf) с помощью ключевого слова префикса.</span><span class="sxs-lookup"><span data-stu-id="62ed6-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="62ed6-105">В следующем примере показано, как создать список:</span><span class="sxs-lookup"><span data-stu-id="62ed6-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="62ed6-106">В генерируемом `repeated` коде поля `Google.Protobuf.Collections.RepeatedField<T>` представлены общим типом, а не любым из встроенных типов коллекции .NET.</span><span class="sxs-lookup"><span data-stu-id="62ed6-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span>

<span data-ttu-id="62ed6-107">Тип `RepeatedField<T>` включает в себя код, необходимый для сериализации и десеризанизации списка в формате двоичного провода.</span><span class="sxs-lookup"><span data-stu-id="62ed6-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="62ed6-108">Он реализует все стандартные интерфейсы коллекции <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IEnumerable%601>.NET, такие как и .</span><span class="sxs-lookup"><span data-stu-id="62ed6-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="62ed6-109">Таким образом, вы можете использовать запросы LIN'а или легко преобразовать их в массив или список.</span><span class="sxs-lookup"><span data-stu-id="62ed6-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="62ed6-110">[Предыдущий](protobuf-nested-types.md)
>[Следующий](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="62ed6-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
