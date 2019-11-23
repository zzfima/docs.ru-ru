---
title: Зарезервированные поля protobuf — gRPC для разработчиков WCF
description: Сведения о зарезервированных полях для обеспечения совместимости между версиями.
ms.date: 09/09/2019
ms.openlocfilehash: e589cd38a712ce014fa2c4d847fbde359d538dd0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967312"
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
