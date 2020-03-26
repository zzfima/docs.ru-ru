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
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="63436-103">Зарезервированные поля Protobuf</span><span class="sxs-lookup"><span data-stu-id="63436-103">Protobuf reserved fields</span></span>

<span data-ttu-id="63436-104">Гарантии обратной совместимости в буфере протокола (Protobuf) зависят от полевых чисел, всегда представляющих один и тот же элемент данных.</span><span class="sxs-lookup"><span data-stu-id="63436-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="63436-105">Если поле удалено из сообщения в новой версии службы, этот номер поля никогда не должен использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="63436-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="63436-106">Вы можете задействовать `reserved` это с помощью ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="63436-106">You can enforce this by using the `reserved` keyword.</span></span>

<span data-ttu-id="63436-107">Если `displayName` поля `marketId` и поля `Stock` были удалены из сообщения, определяемого ранее, их полевые номера должны быть зарезервированы, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="63436-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="63436-108">Вы также можете `reserved` использовать ключевое слово в качестве заполнителя для полей, которые могут быть добавлены в будущем.</span><span class="sxs-lookup"><span data-stu-id="63436-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="63436-109">Вы можете выразить смежные полевые номера `to` в качестве диапазона с помощью ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="63436-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="63436-110">[Предыдущий](protobuf-repeated.md)
>[Следующий](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="63436-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
