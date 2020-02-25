---
title: Зарезервированные поля protobuf — gRPC для разработчиков WCF
description: Сведения о зарезервированных полях для обеспечения совместимости между версиями.
ms.date: 09/09/2019
ms.openlocfilehash: 50082a1aab2e7707a1839b9d56455124a9e4a6a1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542980"
---
# <a name="protobuf-reserved-fields"></a>Зарезервированные поля Protobuf

Гарантии обратной совместимости в буфере протокола (protobuf) полагаются на номера полей, которые всегда представляют один и тот же элемент данных. Если поле удаляется из сообщения в новой версии службы, этот номер поля никогда не следует использовать повторно. Это можно енфоре с помощью ключевого слова `reserved`. 

Если поля `displayName` и `marketId` были удалены из сообщения `Stock`, определенного ранее, их номера полей должны быть зарезервированы, как показано в следующем примере.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Можно также использовать ключевое слово `reserved` в качестве заполнителя для полей, которые могут быть добавлены в будущем. Можно выразить смежные номера полей как диапазон с помощью ключевого слова `to`.

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
