---
title: Protobuf скалярные типы данных — gRPC для разработчиков WCF
description: Сведения об основных и хорошо известных типах данных, которые protobuf и gRPC поддерживаются в .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: f5215550a6a2d54dfe2e859c574a34f641fdb68d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543161"
---
# <a name="protobuf-scalar-data-types"></a>Скалярные типы данных Protobuf

Буфер протокола (protobuf) поддерживает ряд собственных скалярных типов значений. В следующей таблице перечислены все типы с эквивалентными C# типами:

| Тип protobuf | Тип C#      | Примечания |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

Примечания.

1. Стандартная кодировка для `int32` и `int64` неэффективна при работе со значениями со знаком. Если в поле могут содержаться отрицательные числа, используйте вместо него `sint32` или `sint64`. Эти типы сопоставляются с C# типами `int` и `long` соответственно.
2. `fixed` поля всегда используют одинаковое число байтов независимо от значения. Такое поведение позволяет ускорить сериализацию и десериализацию для больших значений.
3. Строки protobuf имеют кодировку UTF-8 (или 7-разрядный код ASCII). Длина закодированного байта не может превышать 2<sup>32</sup>.
4. Среда выполнения protobuf предоставляет тип `ByteString`, который легко сопоставляется с `byte[]` C# массивами и из них.

## <a name="other-net-primitive-types"></a>Другие типы-примитивы .NET

### <a name="dates-and-times"></a>Значения даты и времени

Собственные скалярные типы не предоставляют значения даты и времени, эквиваленты C#<xref:System.DateTimeOffset>, <xref:System.DateTime>и <xref:System.TimeSpan>. Эти типы можно указать с помощью некоторых расширений "хорошо известных типов Google". Эти расширения обеспечивают поддержку создания кода и среды выполнения для сложных типов полей на поддерживаемых платформах. 

В следующей таблице показаны типы даты и времени.

| Тип C# | Известный тип protobuf |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

Созданные свойства в C# классе не являются типами даты и времени .NET. Свойства используют классы `Timestamp` и `Duration` в пространстве имен `Google.Protobuf.WellKnownTypes`. Эти классы предоставляют методы для преобразования в `DateTimeOffset`, `DateTime`и `TimeSpan`.

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> Тип `Timestamp` работает со временем в формате UTC. `DateTimeOffset` значения всегда имеют нулевое смещение, а свойство `DateTime.Kind` всегда `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Protobuf напрямую не поддерживает тип <xref:System.Guid>, известный как `UUID` на других платформах. Для него не существует хорошо известного типа. 

Наилучший подход заключается в обработке `Guid` значений в виде поля `string`, используя стандартный `8-4-4-4-12` шестнадцатеричный формат (например, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`). Все языки и платформы могут анализировать этот формат.

Не используйте `bytes` поле для `Guid` значений. Проблемы с *порядок следования байтов* ([Определение Википедии](https://en.wikipedia.org/wiki/Endianness)) могут привести к непредсказуемому поведению, когда protobuf взаимодействует с другими платформами, такими как Java.

### <a name="nullable-types"></a>Типы, допускающие значения NULL

При создании кода protobuf для C# используются собственные типы, например `int` для `int32`. Поэтому значения всегда включаются и не могут иметь значение null. 

Для значений, для которых требуется явное значение null, например использование C# `int?` в коде, protobuf "хорошо известные типы" включает оболочки, компилируемые в типы C# , допускающие значение null. Чтобы использовать их, импортируйте `wrappers.proto` в файл `.proto` следующим образом:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf будет использовать простое `T?` (например `int?`) для создаваемого свойства сообщения.

В следующей таблице приведен полный список типов оболочек с эквивалентным C# типом:

| Тип C#   | Оболочка хорошо известных типов       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Хорошо известные типы `Timestamp` и `Duration` представлены в .NET как классы, поэтому нет необходимости в версии, допускающей значение null. Но при преобразовании в `DateTimeOffset` или `TimeSpan`важно проверять наличие значения NULL в свойствах этих типов.

## <a name="decimals"></a>Десятичные числа

Protobuf изначально не поддерживает тип .NET `decimal`, просто `double` и `float`. В проекте protobuf есть текущее обсуждение о возможности добавления стандартного типа `Decimal` к хорошо известным типам с поддержкой платформы для языков и платформ, поддерживающих эту возможность. Еще ничего не реализовано.

Можно создать определение сообщения, представляющее тип `decimal`, который будет работать для безопасного сериализации между клиентами и серверами .NET. Но разработчики на других платформах должны понимать, какой формат используется, и реализовать их собственную обработку.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Создание пользовательского десятичного типа для protobuf

Простая реализация может быть аналогична нестандартному типу `Money`, используемому некоторыми API-интерфейсами Google, без поля `currency`.

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message Decimal {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

Поле `nanos` представляет значения из `0.999_999_999` в `-0.999_999_999`. Например, `decimal` значение `1.5m` будет представлено как `{ units = 1, nanos = 500_000_000 }`. Именно поэтому в поле `nanos` в этом примере используется тип `sfixed32`, который более эффективно кодируется, чем `int32` для больших значений. Если поле `units` имеет отрицательное значение, поле `nanos` также должно быть отрицательным.

> [!NOTE]
> Существует несколько других алгоритмов кодирования `decimal` значений в виде строк байтов, но это сообщение проще понять, чем любое из них. На значения не влияют порядок следования байтов на разных платформах.

Преобразование между этим типом и типом BCL `decimal` может быть реализовано C# следующим образом:

```csharp
namespace CustomTypes
{
    public partial class GrpcDecimal
    {
        private const decimal NanoFactor = 1_000_000_000;
        public GrpcDecimal(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.Decimal grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.Decimal(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.Decimal(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> При использовании пользовательских типов сообщений, таких как это, *необходимо* документировать их с помощью комментариев в `.proto`. Другие разработчики могут затем реализовать преобразование в эквивалентный тип и из него на своем языке или в собственной платформе.

>[!div class="step-by-step"]
>[Назад](protobuf-messages.md)
>[Вперед](protobuf-nested-types.md)
