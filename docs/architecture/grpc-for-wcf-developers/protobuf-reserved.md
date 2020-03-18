---
title: Protobuf зарезервированные поля - gRPC для разработчиков WCF
description: Узнайте о зарезервированных полях для совместимости кросс-версий.
ms.date: 09/09/2019
ms.openlocfilehash: bde658c671e970b7ec841d71d5b4284eb91195f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147949"
---
# <a name="protobuf-reserved-fields"></a>Зарезервированные поля Protobuf

Гарантии обратной совместимости в буфере протокола (Protobuf) зависят от полевых чисел, всегда представляющих один и тот же элемент данных. Если поле удалено из сообщения в новой версии службы, этот номер поля никогда не должен использоваться повторно. Вы можете завести это, `reserved` используя ключевое слово.

Если `displayName` поля `marketId` и поля `Stock` были удалены из сообщения, определяемого ранее, их полевые номера должны быть зарезервированы, как в следующем примере.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Вы также можете `reserved` использовать ключевое слово в качестве заполнителя для полей, которые могут быть добавлены в будущем. Вы можете выразить смежные полевые номера `to` в качестве диапазона с помощью ключевого слова.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Предыдущий](protobuf-repeated.md)
>[Следующий](protobuf-any-oneof.md)
