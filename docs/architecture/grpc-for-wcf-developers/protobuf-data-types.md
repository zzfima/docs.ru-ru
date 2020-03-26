---
title: Типы данных Protobuf scalar - gRPC для разработчиков WCF
description: Узнайте об основных и хорошо известных типах данных, поддерживаемых Protobuf и gRPC в .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: ea3b53426ecf6f50f3bae22a537e227b07248508
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249439"
---
# <a name="protobuf-scalar-data-types"></a>Скалярные типы данных Protobuf

Протокол буфера (Protobuf) поддерживает ряд местных типов масштабирования значений. В следующей таблице перечислены все они с эквивалентным типом C':

| Тип протобуфа | Тип C#      | Примечания |
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

1. Стандартное кодирование для `int32` `int64` и является неэффективным, когда вы работаете с подписанными значениями. Если поле, вероятно, содержит отрицательные числа, используйте `sint32` или `sint64` вместо него. Эти типы отображали карты к C и `int` `long` типам, соответственно.
2. Поля `fixed` всегда используют одинаковое количество байтов независимо от значения. Такое поведение ускоряет сериализацию и десериализацию для больших значений.
3. Строки Protobuf кодируются UTF-8 (или 7-битный ASCII). Закодированная длина не может быть больше 2<sup>32</sup>.
4. Время выполнения Protobuf `ByteString` обеспечивает тип, который легко `byte[]` картирует к массивам И КЗ и из нее.

## <a name="other-net-primitive-types"></a>Другие примитивные типы .NET

### <a name="dates-and-times"></a>Даты и время

Родные типы масштабирования не обеспечивают значения даты и времени, эквивалентные значениям C's, <xref:System.DateTimeOffset> <xref:System.DateTime>и <xref:System.TimeSpan>. Вы можете указать эти типы, используя некоторые из Google "Хорошо известных типов" расширений. Эти расширения обеспечивают генерацию кода и поддержку времени выполнения сложных типов полей на поддерживаемых платформах.

В следующей таблице показаны типы даты и времени:

| Тип C# | Протобуф известный тип |
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

Генерируемые свойства в классе C'не являются типами даты и времени .NET. Свойства используют `Timestamp` и `Duration` классы `Google.Protobuf.WellKnownTypes` в пространстве имен. Эти классы предоставляют методы для `DateTimeOffset` `DateTime`преобразования `TimeSpan`в и из , и .

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
> Тип `Timestamp` работает со временем UTC. `DateTimeOffset`значения всегда имеют смещение нуля, и свойство `DateTime.Kind` всегда `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Protobuf напрямую не <xref:System.Guid> поддерживает тип, известный как `UUID` на других платформах. Там нет хорошо известного типа для него.

Наилучший подход заключается `Guid` в `string` обработке значений `8-4-4-4-12` в качестве поля, используя стандартный `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`гексадецимальный формат (например, ). Все языки и платформы могут разбирать этот формат.

Не используйте `bytes` поле `Guid` для значений. Проблемы с *эндиансом* [(определение Википедии)](https://en.wikipedia.org/wiki/Endianness)могут привести к неустойчивому поведению, когда Protobuf взаимодействует с другими платформами, такими как Java.

### <a name="nullable-types"></a>Типы, допускающие значения NULL

В генерации кода Protobuf для C's `int` `int32`используются наиродные типы, например для . Таким образом, значения всегда включены и не могут быть нулевыми.

Для значений, требующих явного `int?` нулевого, например, с использованием кода C,, Protobuf 'Well Known Types' включает обертки, которые компилируются в недействительные типы C. Чтобы использовать их, `wrappers.proto` `.proto` импортируйте в файл, как это:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf будет использовать `T?` простой `int?`(например, ) для генерируемого свойства сообщения.

В следующей таблице показан полный список типов обертки с эквивалентным типом C':

| Тип C#   | Хорошо известный тип обертки       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Известные типы `Timestamp` `Duration` и представлены в .NET как классы. В C- 8 и далее можно использовать недействительные типы ссылок. Но важно, чтобы проверить на нулевую свойства этих типов, когда вы преобразования `DateTimeOffset` или `TimeSpan`.

## <a name="decimals"></a>Десятичные знаки

Protobuf не поддерживает тип .NET, `decimal` просто `double` `float`и . В проекте Protobuf продолжается дискуссия о возможности `Decimal` добавления стандартного типа к известным типам, с поддержкой языков и платформ, которые его поддерживают. Ничего не реализовано.

Можно создать определение сообщений, чтобы `decimal` представить тип, который будет работать для безопасной сериализации между клиентами и серверами .NET. Но разработчики на других платформах должны понимать используемый формат и реализовывать для него собственную обработку.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Создание пользовательского десятичного типа для Protobuf

Простая реализация может быть похожа `Money` на нестандартный тип, `currency` который используют некоторые AA Google без поля.

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

Поле `nanos` представляет значения `0.999_999_999` от `-0.999_999_999`. Например, `decimal` значение `1.5m` будет представлено `{ units = 1, nanos = 500_000_000 }`как . Вот почему `nanos` поле в этом `sfixed32` примере использует тип, который `int32` кодирует более эффективно, чем для больших значений. Если `units` поле отрицательное, `nanos` поле также должно быть отрицательным.

> [!NOTE]
> Существует несколько других алгоритмов кодирования `decimal` значений в качестве строк байт, но это сообщение легче понять, чем любой из них. Значения не зависят от эндиансности на разных платформах.

Преобразование между этим `decimal` типом и типом BCL может быть реализовано в C- q следующим образом:

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
> Всякий раз, когда вы используете пользовательские типы сообщений, как это, вы *должны* документировать их с комментариями в `.proto`. Другие разработчики могут реализовать преобразование в и из эквивалентного типа на своем родном языке или в фрейм-системе.

>[!div class="step-by-step"]
>[Предыдущий](protobuf-messages.md)
>[Следующий](protobuf-nested-types.md)
