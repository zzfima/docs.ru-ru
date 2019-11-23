---
title: Карты protobuf для словарей — gRPC для разработчиков WCF
description: Узнайте, как использовать protobuf Maps для представления. Типы словарей NET.
ms.date: 09/09/2019
ms.openlocfilehash: 8b4f29daa263f329dc533d3ddc596d0f47c1b6e0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967414"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="06956-103">Карты Protobuf для словарей</span><span class="sxs-lookup"><span data-stu-id="06956-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="06956-104">Важно иметь возможность представлять произвольные коллекции именованных значений в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="06956-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="06956-105">В .NET это обычно осуществляется с помощью типов словаря.</span><span class="sxs-lookup"><span data-stu-id="06956-105">In .NET this is commonly handled using dictionary types.</span></span> <span data-ttu-id="06956-106">Эквивалентом типа <xref:System.Collections.Generic.IDictionary%602> .NET для protobuf является тип `map<key_type, value_type>`.</span><span class="sxs-lookup"><span data-stu-id="06956-106">Protobuf's equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="06956-107">В этом разделе показано, как объявить `map` в protobuf и как использовать созданный код.</span><span class="sxs-lookup"><span data-stu-id="06956-107">This section shows how to declare a `map` in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="06956-108">В созданном коде `map` поля используют класс `Google.Protobuf.Collections.MapField<TKey, TValue>`, который реализует стандартные интерфейсы коллекции .NET, в том числе <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="06956-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class, which implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="06956-109">Поля карт не могут повторяться непосредственно в определении сообщения, но можно создать вложенное сообщение, содержащее карту и использовать `repeated` для типа сообщений, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="06956-109">Map fields can't be directly repeated in a message definition, but you can create a nested message containing a map and use `repeated` on the message type, like in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="06956-110">Использование свойств Мапфиелд в коде</span><span class="sxs-lookup"><span data-stu-id="06956-110">Using MapField properties in code</span></span>

<span data-ttu-id="06956-111">Свойства `MapField`, созданные из `map` полей, доступны только для чтения и никогда не будут `null`.</span><span class="sxs-lookup"><span data-stu-id="06956-111">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="06956-112">Чтобы задать свойство Map, используйте метод `Add(IDictionary<TKey,TValue> values)` для свойства Empty `MapField`, чтобы скопировать значения из любого словаря .NET.</span><span class="sxs-lookup"><span data-stu-id="06956-112">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="06956-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="06956-113">Further reading</span></span>

<span data-ttu-id="06956-114">Дополнительные сведения о protobuf см. в официальной [документации protobuf](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="06956-114">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06956-115">[Назад](protobuf-enums.md)
>[Вперед](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="06956-115">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
