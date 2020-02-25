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
# <a name="repeated-fields-for-lists-and-arrays"></a>Повторяющиеся поля для списков и массивов

Списки в буфере протокола (protobuf) указываются с помощью ключевого слова prefix `repeated`. В следующем примере показано, как создать список.

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

В созданном коде `repeated` поля представлены `Google.Protobuf.Collections.RepeatedField<T>` универсальным типом, а не любым из встроенных типов коллекций .NET. 

Тип `RepeatedField<T>` включает код, необходимый для сериализации и десериализации списка в двоичный формат сети. Он реализует все стандартные интерфейсы коллекции .NET, такие как <xref:System.Collections.Generic.IList%601> и <xref:System.Collections.Generic.IEnumerable%601>. Поэтому можно легко использовать запросы LINQ или преобразовать их в массив или список.

>[!div class="step-by-step"]
>[Назад](protobuf-nested-types.md)
>[Вперед](protobuf-reserved.md)
