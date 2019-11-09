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
