---
title: Protobuf зарезервированные поля - gRPC для разработчиков WCF
description: Узнайте о зарезервированных полях для совместимости кросс-версий.
ms.date: 09/09/2019
ms.openlocfilehash: f89513c4659a02cbc94e1c659baecb9e750acbdc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111040"
---
# <a name="protobuf-reserved-fields"></a>Зарезервированные поля Protobuf

Гарантии обратной совместимости в буфере протокола (Protobuf) зависят от полевых чисел, всегда представляющих один и тот же элемент данных. Если поле удалено из сообщения в новой версии службы, этот номер поля никогда не должен использоваться повторно. Вы можете задействовать `reserved` это с помощью ключевого слова.

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
