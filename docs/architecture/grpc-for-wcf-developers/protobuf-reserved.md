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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="0fdef-103">Зарезервированные поля Protobuf</span><span class="sxs-lookup"><span data-stu-id="0fdef-103">Protobuf reserved fields</span></span>

<span data-ttu-id="0fdef-104">Гарантии обратной совместимости в буфере протокола (Protobuf) зависят от полевых чисел, всегда представляющих один и тот же элемент данных.</span><span class="sxs-lookup"><span data-stu-id="0fdef-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="0fdef-105">Если поле удалено из сообщения в новой версии службы, этот номер поля никогда не должен использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="0fdef-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="0fdef-106">Вы можете завести это, `reserved` используя ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0fdef-106">You can enfore this by using the `reserved` keyword.</span></span>

<span data-ttu-id="0fdef-107">Если `displayName` поля `marketId` и поля `Stock` были удалены из сообщения, определяемого ранее, их полевые номера должны быть зарезервированы, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0fdef-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="0fdef-108">Вы также можете `reserved` использовать ключевое слово в качестве заполнителя для полей, которые могут быть добавлены в будущем.</span><span class="sxs-lookup"><span data-stu-id="0fdef-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="0fdef-109">Вы можете выразить смежные полевые номера `to` в качестве диапазона с помощью ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="0fdef-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="0fdef-110">[Предыдущий](protobuf-repeated.md)
>[Следующий](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="0fdef-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
