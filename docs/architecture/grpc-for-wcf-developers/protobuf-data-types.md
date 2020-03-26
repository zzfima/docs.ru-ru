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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="43686-103">Скалярные типы данных Protobuf</span><span class="sxs-lookup"><span data-stu-id="43686-103">Protobuf scalar data types</span></span>

<span data-ttu-id="43686-104">Протокол буфера (Protobuf) поддерживает ряд местных типов масштабирования значений.</span><span class="sxs-lookup"><span data-stu-id="43686-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="43686-105">В следующей таблице перечислены все они с эквивалентным типом C':</span><span class="sxs-lookup"><span data-stu-id="43686-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="43686-106">Тип протобуфа</span><span class="sxs-lookup"><span data-stu-id="43686-106">Protobuf type</span></span> | <span data-ttu-id="43686-107">Тип C#</span><span class="sxs-lookup"><span data-stu-id="43686-107">C# type</span></span>      | <span data-ttu-id="43686-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="43686-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="43686-109">1</span><span class="sxs-lookup"><span data-stu-id="43686-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="43686-110">1</span><span class="sxs-lookup"><span data-stu-id="43686-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="43686-111">1</span><span class="sxs-lookup"><span data-stu-id="43686-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="43686-112">1</span><span class="sxs-lookup"><span data-stu-id="43686-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="43686-113">2</span><span class="sxs-lookup"><span data-stu-id="43686-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="43686-114">2</span><span class="sxs-lookup"><span data-stu-id="43686-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="43686-115">2</span><span class="sxs-lookup"><span data-stu-id="43686-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="43686-116">2</span><span class="sxs-lookup"><span data-stu-id="43686-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="43686-117">3</span><span class="sxs-lookup"><span data-stu-id="43686-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="43686-118">4</span><span class="sxs-lookup"><span data-stu-id="43686-118">4</span></span>     |

<span data-ttu-id="43686-119">Примечания.</span><span class="sxs-lookup"><span data-stu-id="43686-119">Notes:</span></span>

1. <span data-ttu-id="43686-120">Стандартное кодирование для `int32` `int64` и является неэффективным, когда вы работаете с подписанными значениями.</span><span class="sxs-lookup"><span data-stu-id="43686-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="43686-121">Если поле, вероятно, содержит отрицательные числа, используйте `sint32` или `sint64` вместо него.</span><span class="sxs-lookup"><span data-stu-id="43686-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="43686-122">Эти типы отображали карты к C и `int` `long` типам, соответственно.</span><span class="sxs-lookup"><span data-stu-id="43686-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="43686-123">Поля `fixed` всегда используют одинаковое количество байтов независимо от значения.</span><span class="sxs-lookup"><span data-stu-id="43686-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="43686-124">Такое поведение ускоряет сериализацию и десериализацию для больших значений.</span><span class="sxs-lookup"><span data-stu-id="43686-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="43686-125">Строки Protobuf кодируются UTF-8 (или 7-битный ASCII).</span><span class="sxs-lookup"><span data-stu-id="43686-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="43686-126">Закодированная длина не может быть больше 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="43686-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="43686-127">Время выполнения Protobuf `ByteString` обеспечивает тип, который легко `byte[]` картирует к массивам И КЗ и из нее.</span><span class="sxs-lookup"><span data-stu-id="43686-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="43686-128">Другие примитивные типы .NET</span><span class="sxs-lookup"><span data-stu-id="43686-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="43686-129">Даты и время</span><span class="sxs-lookup"><span data-stu-id="43686-129">Dates and times</span></span>

<span data-ttu-id="43686-130">Родные типы масштабирования не обеспечивают значения даты и времени, эквивалентные значениям C's, <xref:System.DateTimeOffset> <xref:System.DateTime>и <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="43686-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="43686-131">Вы можете указать эти типы, используя некоторые из Google "Хорошо известных типов" расширений.</span><span class="sxs-lookup"><span data-stu-id="43686-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="43686-132">Эти расширения обеспечивают генерацию кода и поддержку времени выполнения сложных типов полей на поддерживаемых платформах.</span><span class="sxs-lookup"><span data-stu-id="43686-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="43686-133">В следующей таблице показаны типы даты и времени:</span><span class="sxs-lookup"><span data-stu-id="43686-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="43686-134">Тип C#</span><span class="sxs-lookup"><span data-stu-id="43686-134">C# type</span></span> | <span data-ttu-id="43686-135">Протобуф известный тип</span><span class="sxs-lookup"><span data-stu-id="43686-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="43686-136">Генерируемые свойства в классе C'не являются типами даты и времени .NET.</span><span class="sxs-lookup"><span data-stu-id="43686-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="43686-137">Свойства используют `Timestamp` и `Duration` классы `Google.Protobuf.WellKnownTypes` в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="43686-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="43686-138">Эти классы предоставляют методы для `DateTimeOffset` `DateTime`преобразования `TimeSpan`в и из , и .</span><span class="sxs-lookup"><span data-stu-id="43686-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="43686-139">Тип `Timestamp` работает со временем UTC.</span><span class="sxs-lookup"><span data-stu-id="43686-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="43686-140">`DateTimeOffset`значения всегда имеют смещение нуля, и свойство `DateTime.Kind` всегда `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="43686-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="43686-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="43686-141">System.Guid</span></span>

<span data-ttu-id="43686-142">Protobuf напрямую не <xref:System.Guid> поддерживает тип, известный как `UUID` на других платформах.</span><span class="sxs-lookup"><span data-stu-id="43686-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="43686-143">Там нет хорошо известного типа для него.</span><span class="sxs-lookup"><span data-stu-id="43686-143">There's no well-known type for it.</span></span>

<span data-ttu-id="43686-144">Наилучший подход заключается `Guid` в `string` обработке значений `8-4-4-4-12` в качестве поля, используя стандартный `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`гексадецимальный формат (например, ).</span><span class="sxs-lookup"><span data-stu-id="43686-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="43686-145">Все языки и платформы могут разбирать этот формат.</span><span class="sxs-lookup"><span data-stu-id="43686-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="43686-146">Не используйте `bytes` поле `Guid` для значений.</span><span class="sxs-lookup"><span data-stu-id="43686-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="43686-147">Проблемы с *эндиансом* [(определение Википедии)](https://en.wikipedia.org/wiki/Endianness)могут привести к неустойчивому поведению, когда Protobuf взаимодействует с другими платформами, такими как Java.</span><span class="sxs-lookup"><span data-stu-id="43686-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="43686-148">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="43686-148">Nullable types</span></span>

<span data-ttu-id="43686-149">В генерации кода Protobuf для C's `int` `int32`используются наиродные типы, например для .</span><span class="sxs-lookup"><span data-stu-id="43686-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="43686-150">Таким образом, значения всегда включены и не могут быть нулевыми.</span><span class="sxs-lookup"><span data-stu-id="43686-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="43686-151">Для значений, требующих явного `int?` нулевого, например, с использованием кода C,, Protobuf 'Well Known Types' включает обертки, которые компилируются в недействительные типы C.</span><span class="sxs-lookup"><span data-stu-id="43686-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="43686-152">Чтобы использовать их, `wrappers.proto` `.proto` импортируйте в файл, как это:</span><span class="sxs-lookup"><span data-stu-id="43686-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="43686-153">Protobuf будет использовать `T?` простой `int?`(например, ) для генерируемого свойства сообщения.</span><span class="sxs-lookup"><span data-stu-id="43686-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="43686-154">В следующей таблице показан полный список типов обертки с эквивалентным типом C':</span><span class="sxs-lookup"><span data-stu-id="43686-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="43686-155">Тип C#</span><span class="sxs-lookup"><span data-stu-id="43686-155">C# type</span></span>   | <span data-ttu-id="43686-156">Хорошо известный тип обертки</span><span class="sxs-lookup"><span data-stu-id="43686-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="43686-157">Известные типы `Timestamp` `Duration` и представлены в .NET как классы.</span><span class="sxs-lookup"><span data-stu-id="43686-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="43686-158">В C- 8 и далее можно использовать недействительные типы ссылок.</span><span class="sxs-lookup"><span data-stu-id="43686-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="43686-159">Но важно, чтобы проверить на нулевую свойства этих типов, когда вы преобразования `DateTimeOffset` или `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="43686-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="43686-160">Десятичные знаки</span><span class="sxs-lookup"><span data-stu-id="43686-160">Decimals</span></span>

<span data-ttu-id="43686-161">Protobuf не поддерживает тип .NET, `decimal` просто `double` `float`и .</span><span class="sxs-lookup"><span data-stu-id="43686-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="43686-162">В проекте Protobuf продолжается дискуссия о возможности `Decimal` добавления стандартного типа к известным типам, с поддержкой языков и платформ, которые его поддерживают.</span><span class="sxs-lookup"><span data-stu-id="43686-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="43686-163">Ничего не реализовано.</span><span class="sxs-lookup"><span data-stu-id="43686-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="43686-164">Можно создать определение сообщений, чтобы `decimal` представить тип, который будет работать для безопасной сериализации между клиентами и серверами .NET.</span><span class="sxs-lookup"><span data-stu-id="43686-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="43686-165">Но разработчики на других платформах должны понимать используемый формат и реализовывать для него собственную обработку.</span><span class="sxs-lookup"><span data-stu-id="43686-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="43686-166">Создание пользовательского десятичного типа для Protobuf</span><span class="sxs-lookup"><span data-stu-id="43686-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="43686-167">Простая реализация может быть похожа `Money` на нестандартный тип, `currency` который используют некоторые AA Google без поля.</span><span class="sxs-lookup"><span data-stu-id="43686-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="43686-168">Поле `nanos` представляет значения `0.999_999_999` от `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="43686-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="43686-169">Например, `decimal` значение `1.5m` будет представлено `{ units = 1, nanos = 500_000_000 }`как .</span><span class="sxs-lookup"><span data-stu-id="43686-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="43686-170">Вот почему `nanos` поле в этом `sfixed32` примере использует тип, который `int32` кодирует более эффективно, чем для больших значений.</span><span class="sxs-lookup"><span data-stu-id="43686-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="43686-171">Если `units` поле отрицательное, `nanos` поле также должно быть отрицательным.</span><span class="sxs-lookup"><span data-stu-id="43686-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="43686-172">Существует несколько других алгоритмов кодирования `decimal` значений в качестве строк байт, но это сообщение легче понять, чем любой из них.</span><span class="sxs-lookup"><span data-stu-id="43686-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="43686-173">Значения не зависят от эндиансности на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="43686-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="43686-174">Преобразование между этим `decimal` типом и типом BCL может быть реализовано в C- q следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43686-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="43686-175">Всякий раз, когда вы используете пользовательские типы сообщений, как это, вы *должны* документировать их с комментариями в `.proto`.</span><span class="sxs-lookup"><span data-stu-id="43686-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="43686-176">Другие разработчики могут реализовать преобразование в и из эквивалентного типа на своем родном языке или в фрейм-системе.</span><span class="sxs-lookup"><span data-stu-id="43686-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="43686-177">[Предыдущий](protobuf-messages.md)
>[Следующий](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="43686-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
