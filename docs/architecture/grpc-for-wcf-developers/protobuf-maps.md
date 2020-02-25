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
# <a name="protobuf-maps-for-dictionaries"></a>Карты Protobuf для словарей

Важно иметь возможность представлять произвольные коллекции именованных значений в сообщениях. В .NET это обычно осуществляется с помощью типов словаря. Эквивалентом типа <xref:System.Collections.Generic.IDictionary%602> .NET в буфере протокола (protobuf) является тип `map<key_type, value_type>`. В этом разделе показано, как объявить тип `map` в protobuf и как использовать созданный код.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

В созданном коде `map` поля используют класс `Google.Protobuf.Collections.MapField<TKey, TValue>`. Этот класс реализует стандартные интерфейсы коллекции .NET, в том числе <xref:System.Collections.Generic.IDictionary%602>.

Поля карт не могут повторяться непосредственно в определении сообщения. Однако можно создать вложенное сообщение, содержащее карту и использовать `repeated` для типа сообщений, как показано в следующем примере:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Использование свойств Мапфиелд в коде

Свойства `MapField`, созданные из `map` полей, доступны только для чтения и никогда не будут `null`. Чтобы задать свойство Map, используйте метод `Add(IDictionary<TKey,TValue> values)` для свойства Empty `MapField`, чтобы скопировать значения из любого словаря .NET.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Дополнительные материалы

Дополнительные сведения о protobuf см. в официальной [документации protobuf](https://developers.google.com/protocol-buffers/docs/overview).

>[!div class="step-by-step"]
>[Назад](protobuf-enums.md)
>[Вперед](wcf-services-to-grpc-comparison.md)
