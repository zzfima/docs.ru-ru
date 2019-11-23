---
title: Повторяющиеся поля для списков и массивов — gRPC для разработчиков WCF
description: Узнайте, как коллекции обрабатываются protobuf и как они связаны с коллекциями .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 17c579bc98ba62ea74b9452bdb28efd96fc51406
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967368"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Повторяющиеся поля для списков и массивов

Списки указываются в protobuf с помощью ключевого слова `repeated` prefix. В следующем примере показано, как создать список.

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

В созданном коде `repeated` поля представлены `Google.Protobuf.Collections.RepeatedField<T>` универсальным типом, а не любым из встроенных типов коллекций .NET. Тип `RepeatedField<T>` включает код, необходимый для сериализации и десериализации списка в двоичный формат сети. В нем реализованы все стандартные интерфейсы коллекций .NET, такие как <xref:System.Collections.Generic.IList%601> и <xref:System.Collections.Generic.IEnumerable%601>, поэтому можно использовать запросы LINQ или легко преобразовать их в массив или список.

>[!div class="step-by-step"]
>[Назад](protobuf-nested-types.md)
>[Вперед](protobuf-reserved.md)
