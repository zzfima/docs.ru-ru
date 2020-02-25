---
title: Карты protobuf для словарей — gRPC для разработчиков WCF
description: Узнайте, как использовать карты protobuf для представления типов словарей в .NET.
ms.date: 09/09/2019
ms.openlocfilehash: bf848bbc7e3618f6d78e280fcd85d5eb88d5cfae
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543135"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="e4a1e-103">Карты Protobuf для словарей</span><span class="sxs-lookup"><span data-stu-id="e4a1e-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="e4a1e-104">Важно иметь возможность представлять произвольные коллекции именованных значений в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="e4a1e-105">В .NET это обычно осуществляется с помощью типов словаря.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="e4a1e-106">Эквивалентом типа <xref:System.Collections.Generic.IDictionary%602> .NET в буфере протокола (protobuf) является тип `map<key_type, value_type>`.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="e4a1e-107">В этом разделе показано, как объявить тип `map` в protobuf и как использовать созданный код.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="e4a1e-108">В созданном коде `map` поля используют класс `Google.Protobuf.Collections.MapField<TKey, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class.</span></span> <span data-ttu-id="e4a1e-109">Этот класс реализует стандартные интерфейсы коллекции .NET, в том числе <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-109">This class implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="e4a1e-110">Поля карт не могут повторяться непосредственно в определении сообщения.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="e4a1e-111">Однако можно создать вложенное сообщение, содержащее карту и использовать `repeated` для типа сообщений, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e4a1e-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="e4a1e-112">Использование свойств Мапфиелд в коде</span><span class="sxs-lookup"><span data-stu-id="e4a1e-112">Using MapField properties in code</span></span>

<span data-ttu-id="e4a1e-113">Свойства `MapField`, созданные из `map` полей, доступны только для чтения и никогда не будут `null`.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="e4a1e-114">Чтобы задать свойство Map, используйте метод `Add(IDictionary<TKey,TValue> values)` для свойства Empty `MapField`, чтобы скопировать значения из любого словаря .NET.</span><span class="sxs-lookup"><span data-stu-id="e4a1e-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="e4a1e-115">Дополнительные материалы</span><span class="sxs-lookup"><span data-stu-id="e4a1e-115">Further reading</span></span>

<span data-ttu-id="e4a1e-116">Дополнительные сведения о protobuf см. в официальной [документации protobuf](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="e4a1e-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e4a1e-117">[Назад](protobuf-enums.md)
>[Вперед](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="e4a1e-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
