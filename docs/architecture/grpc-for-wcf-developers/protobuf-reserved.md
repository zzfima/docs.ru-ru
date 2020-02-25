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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="28e6c-103">Зарезервированные поля Protobuf</span><span class="sxs-lookup"><span data-stu-id="28e6c-103">Protobuf reserved fields</span></span>

<span data-ttu-id="28e6c-104">Гарантии обратной совместимости в буфере протокола (protobuf) полагаются на номера полей, которые всегда представляют один и тот же элемент данных.</span><span class="sxs-lookup"><span data-stu-id="28e6c-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="28e6c-105">Если поле удаляется из сообщения в новой версии службы, этот номер поля никогда не следует использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="28e6c-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="28e6c-106">Это можно енфоре с помощью ключевого слова `reserved`.</span><span class="sxs-lookup"><span data-stu-id="28e6c-106">You can enfore this by using the `reserved` keyword.</span></span> 

<span data-ttu-id="28e6c-107">Если поля `displayName` и `marketId` были удалены из сообщения `Stock`, определенного ранее, их номера полей должны быть зарезервированы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="28e6c-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="28e6c-108">Можно также использовать ключевое слово `reserved` в качестве заполнителя для полей, которые могут быть добавлены в будущем.</span><span class="sxs-lookup"><span data-stu-id="28e6c-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="28e6c-109">Можно выразить смежные номера полей как диапазон с помощью ключевого слова `to`.</span><span class="sxs-lookup"><span data-stu-id="28e6c-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="28e6c-110">[Назад](protobuf-repeated.md)
>[Вперед](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="28e6c-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
