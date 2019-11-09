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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="cc4b0-103">Зарезервированные поля Protobuf</span><span class="sxs-lookup"><span data-stu-id="cc4b0-103">Protobuf reserved fields</span></span>

<span data-ttu-id="cc4b0-104">Гарантии обратной совместимости protobuf полагаются на номера полей, которые всегда представляют один и тот же элемент данных.</span><span class="sxs-lookup"><span data-stu-id="cc4b0-104">Protobuf's backward-compatibility guarantees rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="cc4b0-105">Если поле удаляется из сообщения в новой версии службы, этот номер поля никогда не следует использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="cc4b0-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="cc4b0-106">Это можно реализовать с помощью ключевого слова `reserved`.</span><span class="sxs-lookup"><span data-stu-id="cc4b0-106">This can be enforced using the `reserved` keyword.</span></span> <span data-ttu-id="cc4b0-107">Если поля `displayName` и `marketId` были удалены из сообщения `Stock`, определенного ранее, их номера полей должны быть зарезервированы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cc4b0-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="cc4b0-108">Ключевое слово `reserved` также можно использовать в качестве заполнителя для полей, которые могут быть добавлены в будущем.</span><span class="sxs-lookup"><span data-stu-id="cc4b0-108">The `reserved` keyword can also be used as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="cc4b0-109">Последовательные номера полей могут быть выражены в диапазоне с помощью ключевого слова `to`.</span><span class="sxs-lookup"><span data-stu-id="cc4b0-109">Contiguous field numbers can be expressed as a range using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="cc4b0-110">[Назад](protobuf-repeated.md)
>[Вперед](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="cc4b0-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
