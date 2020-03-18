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
# <a name="repeated-fields-for-lists-and-arrays"></a>Повторяющиеся поля для списков и массивов

Вы указываете списки в Протоколе Буфер `repeated` (Protobuf) с помощью ключевого слова префикса. В следующем примере показано, как создать список:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

В генерируемом `repeated` коде поля `Google.Protobuf.Collections.RepeatedField<T>` представлены общим типом, а не любым из встроенных типов коллекции .NET.

Тип `RepeatedField<T>` включает в себя код, необходимый для сериализации и десеризанизации списка в формате двоичного провода. Он реализует все стандартные интерфейсы коллекции <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IEnumerable%601>.NET, такие как и . Таким образом, вы можете использовать запросы LIN'а или легко преобразовать их в массив или список.

>[!div class="step-by-step"]
>[Предыдущий](protobuf-nested-types.md)
>[Следующий](protobuf-reserved.md)
