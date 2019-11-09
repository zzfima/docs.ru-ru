---
title: Зарезервированные поля protobuf — gRPC для разработчиков WCF
description: Сведения о зарезервированных полях для обеспечения совместимости между версиями.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 34697371299bdc5d9a58c0696c1ce7d19816ca87
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841393"
---
# <a name="protobuf-reserved-fields"></a>Зарезервированные поля Protobuf

Гарантии обратной совместимости protobuf полагаются на номера полей, которые всегда представляют один и тот же элемент данных. Если поле удаляется из сообщения в новой версии службы, этот номер поля никогда не следует использовать повторно. Это можно реализовать с помощью ключевого слова `reserved`. Если поля `displayName` и `marketId` были удалены из сообщения `Stock`, определенного ранее, их номера полей должны быть зарезервированы, как показано в следующем примере.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Ключевое слово `reserved` также можно использовать в качестве заполнителя для полей, которые могут быть добавлены в будущем. Последовательные номера полей могут быть выражены в диапазоне с помощью ключевого слова `to`.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Назад](protobuf-repeated.md)
>[Вперед](protobuf-any-oneof.md)
