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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="4dd81-103">Зарезервированные поля Protobuf</span><span class="sxs-lookup"><span data-stu-id="4dd81-103">Protobuf reserved fields</span></span>

<span data-ttu-id="4dd81-104">Гарантии обратной совместимости protobuf полагаются на номера полей, которые всегда представляют один и тот же элемент данных.</span><span class="sxs-lookup"><span data-stu-id="4dd81-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="4dd81-105">Если поле удаляется из сообщения в новой версии службы, этот номер поля никогда не следует использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="4dd81-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="4dd81-106">Это можно реализовать с помощью ключевого слова `reserved`.</span><span class="sxs-lookup"><span data-stu-id="4dd81-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="4dd81-107">Если поля `displayName` и `marketId` были удалены из сообщения `Stock`, определенного ранее, их номера полей должны быть зарезервированы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4dd81-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="4dd81-108">Ключевое слово `reserved` также можно использовать в качестве заполнителя для полей, которые могут быть добавлены в будущем.</span><span class="sxs-lookup"><span data-stu-id="4dd81-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="4dd81-109">Последовательные номера полей могут быть выражены в диапазоне с помощью ключевого слова `to`.</span><span class="sxs-lookup"><span data-stu-id="4dd81-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="4dd81-110">[Назад](protobuf-repeated.md)
>[Вперед](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="4dd81-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
