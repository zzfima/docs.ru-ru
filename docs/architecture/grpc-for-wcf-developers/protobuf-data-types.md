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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="579f5-103">Скалярные типы данных Protobuf</span><span class="sxs-lookup"><span data-stu-id="579f5-103">Protobuf scalar data types</span></span>

<span data-ttu-id="579f5-104">Буфер протокола (protobuf) поддерживает ряд собственных скалярных типов значений.</span><span class="sxs-lookup"><span data-stu-id="579f5-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="579f5-105">В следующей таблице перечислены все типы с эквивалентными C# типами:</span><span class="sxs-lookup"><span data-stu-id="579f5-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="579f5-106">Тип protobuf</span><span class="sxs-lookup"><span data-stu-id="579f5-106">Protobuf type</span></span> | <span data-ttu-id="579f5-107">Тип C#</span><span class="sxs-lookup"><span data-stu-id="579f5-107">C# type</span></span>      | <span data-ttu-id="579f5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="579f5-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="579f5-109">1</span><span class="sxs-lookup"><span data-stu-id="579f5-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="579f5-110">1</span><span class="sxs-lookup"><span data-stu-id="579f5-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="579f5-111">1</span><span class="sxs-lookup"><span data-stu-id="579f5-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="579f5-112">1</span><span class="sxs-lookup"><span data-stu-id="579f5-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="579f5-113">2</span><span class="sxs-lookup"><span data-stu-id="579f5-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="579f5-114">2</span><span class="sxs-lookup"><span data-stu-id="579f5-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="579f5-115">2</span><span class="sxs-lookup"><span data-stu-id="579f5-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="579f5-116">2</span><span class="sxs-lookup"><span data-stu-id="579f5-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="579f5-117">3</span><span class="sxs-lookup"><span data-stu-id="579f5-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="579f5-118">4</span><span class="sxs-lookup"><span data-stu-id="579f5-118">4</span></span>     |

<span data-ttu-id="579f5-119">Примечания.</span><span class="sxs-lookup"><span data-stu-id="579f5-119">Notes:</span></span>

1. <span data-ttu-id="579f5-120">Стандартная кодировка для `int32` и `int64` неэффективна при работе со значениями со знаком.</span><span class="sxs-lookup"><span data-stu-id="579f5-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="579f5-121">Если в поле могут содержаться отрицательные числа, используйте вместо него `sint32` или `sint64`.</span><span class="sxs-lookup"><span data-stu-id="579f5-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="579f5-122">Эти типы сопоставляются с C# типами `int` и `long` соответственно.</span><span class="sxs-lookup"><span data-stu-id="579f5-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="579f5-123">`fixed` поля всегда используют одинаковое число байтов независимо от значения.</span><span class="sxs-lookup"><span data-stu-id="579f5-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="579f5-124">Такое поведение позволяет ускорить сериализацию и десериализацию для больших значений.</span><span class="sxs-lookup"><span data-stu-id="579f5-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="579f5-125">Строки protobuf имеют кодировку UTF-8 (или 7-разрядный код ASCII).</span><span class="sxs-lookup"><span data-stu-id="579f5-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="579f5-126">Длина закодированного байта не может превышать 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="579f5-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="579f5-127">Среда выполнения protobuf предоставляет тип `ByteString`, который легко сопоставляется с `byte[]` C# массивами и из них.</span><span class="sxs-lookup"><span data-stu-id="579f5-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="579f5-128">Другие типы-примитивы .NET</span><span class="sxs-lookup"><span data-stu-id="579f5-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="579f5-129">Значения даты и времени</span><span class="sxs-lookup"><span data-stu-id="579f5-129">Dates and times</span></span>

<span data-ttu-id="579f5-130">Собственные скалярные типы не предоставляют значения даты и времени, эквиваленты C#<xref:System.DateTimeOffset>, <xref:System.DateTime>и <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="579f5-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="579f5-131">Эти типы можно указать с помощью некоторых расширений "хорошо известных типов Google".</span><span class="sxs-lookup"><span data-stu-id="579f5-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="579f5-132">Эти расширения обеспечивают поддержку создания кода и среды выполнения для сложных типов полей на поддерживаемых платформах.</span><span class="sxs-lookup"><span data-stu-id="579f5-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span> 

<span data-ttu-id="579f5-133">В следующей таблице показаны типы даты и времени.</span><span class="sxs-lookup"><span data-stu-id="579f5-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="579f5-134">Тип C#</span><span class="sxs-lookup"><span data-stu-id="579f5-134">C# type</span></span> | <span data-ttu-id="579f5-135">Известный тип protobuf</span><span class="sxs-lookup"><span data-stu-id="579f5-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="579f5-136">Созданные свойства в C# классе не являются типами даты и времени .NET.</span><span class="sxs-lookup"><span data-stu-id="579f5-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="579f5-137">Свойства используют классы `Timestamp` и `Duration` в пространстве имен `Google.Protobuf.WellKnownTypes`.</span><span class="sxs-lookup"><span data-stu-id="579f5-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="579f5-138">Эти классы предоставляют методы для преобразования в `DateTimeOffset`, `DateTime`и `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="579f5-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="579f5-139">Тип `Timestamp` работает со временем в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="579f5-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="579f5-140">`DateTimeOffset` значения всегда имеют нулевое смещение, а свойство `DateTime.Kind` всегда `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="579f5-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="579f5-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="579f5-141">System.Guid</span></span>

<span data-ttu-id="579f5-142">Protobuf напрямую не поддерживает тип <xref:System.Guid>, известный как `UUID` на других платформах.</span><span class="sxs-lookup"><span data-stu-id="579f5-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="579f5-143">Для него не существует хорошо известного типа.</span><span class="sxs-lookup"><span data-stu-id="579f5-143">There's no well-known type for it.</span></span> 

<span data-ttu-id="579f5-144">Наилучший подход заключается в обработке `Guid` значений в виде поля `string`, используя стандартный `8-4-4-4-12` шестнадцатеричный формат (например, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span><span class="sxs-lookup"><span data-stu-id="579f5-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="579f5-145">Все языки и платформы могут анализировать этот формат.</span><span class="sxs-lookup"><span data-stu-id="579f5-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="579f5-146">Не используйте `bytes` поле для `Guid` значений.</span><span class="sxs-lookup"><span data-stu-id="579f5-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="579f5-147">Проблемы с *порядок следования байтов* ([Определение Википедии](https://en.wikipedia.org/wiki/Endianness)) могут привести к непредсказуемому поведению, когда protobuf взаимодействует с другими платформами, такими как Java.</span><span class="sxs-lookup"><span data-stu-id="579f5-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="579f5-148">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="579f5-148">Nullable types</span></span>

<span data-ttu-id="579f5-149">При создании кода protobuf для C# используются собственные типы, например `int` для `int32`.</span><span class="sxs-lookup"><span data-stu-id="579f5-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="579f5-150">Поэтому значения всегда включаются и не могут иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="579f5-150">So the values are always included and can't be null.</span></span> 

<span data-ttu-id="579f5-151">Для значений, для которых требуется явное значение null, например использование C# `int?` в коде, protobuf "хорошо известные типы" включает оболочки, компилируемые в типы C# , допускающие значение null.</span><span class="sxs-lookup"><span data-stu-id="579f5-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="579f5-152">Чтобы использовать их, импортируйте `wrappers.proto` в файл `.proto` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="579f5-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="579f5-153">Protobuf будет использовать простое `T?` (например `int?`) для создаваемого свойства сообщения.</span><span class="sxs-lookup"><span data-stu-id="579f5-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="579f5-154">В следующей таблице приведен полный список типов оболочек с эквивалентным C# типом:</span><span class="sxs-lookup"><span data-stu-id="579f5-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="579f5-155">Тип C#</span><span class="sxs-lookup"><span data-stu-id="579f5-155">C# type</span></span>   | <span data-ttu-id="579f5-156">Оболочка хорошо известных типов</span><span class="sxs-lookup"><span data-stu-id="579f5-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="579f5-157">Хорошо известные типы `Timestamp` и `Duration` представлены в .NET как классы, поэтому нет необходимости в версии, допускающей значение null.</span><span class="sxs-lookup"><span data-stu-id="579f5-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="579f5-158">Но при преобразовании в `DateTimeOffset` или `TimeSpan`важно проверять наличие значения NULL в свойствах этих типов.</span><span class="sxs-lookup"><span data-stu-id="579f5-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="579f5-159">Десятичные числа</span><span class="sxs-lookup"><span data-stu-id="579f5-159">Decimals</span></span>

<span data-ttu-id="579f5-160">Protobuf изначально не поддерживает тип .NET `decimal`, просто `double` и `float`.</span><span class="sxs-lookup"><span data-stu-id="579f5-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="579f5-161">В проекте protobuf есть текущее обсуждение о возможности добавления стандартного типа `Decimal` к хорошо известным типам с поддержкой платформы для языков и платформ, поддерживающих эту возможность.</span><span class="sxs-lookup"><span data-stu-id="579f5-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="579f5-162">Еще ничего не реализовано.</span><span class="sxs-lookup"><span data-stu-id="579f5-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="579f5-163">Можно создать определение сообщения, представляющее тип `decimal`, который будет работать для безопасного сериализации между клиентами и серверами .NET.</span><span class="sxs-lookup"><span data-stu-id="579f5-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="579f5-164">Но разработчики на других платформах должны понимать, какой формат используется, и реализовать их собственную обработку.</span><span class="sxs-lookup"><span data-stu-id="579f5-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="579f5-165">Создание пользовательского десятичного типа для protobuf</span><span class="sxs-lookup"><span data-stu-id="579f5-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="579f5-166">Простая реализация может быть аналогична нестандартному типу `Money`, используемому некоторыми API-интерфейсами Google, без поля `currency`.</span><span class="sxs-lookup"><span data-stu-id="579f5-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="579f5-167">Поле `nanos` представляет значения из `0.999_999_999` в `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="579f5-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="579f5-168">Например, `decimal` значение `1.5m` будет представлено как `{ units = 1, nanos = 500_000_000 }`.</span><span class="sxs-lookup"><span data-stu-id="579f5-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="579f5-169">Именно поэтому в поле `nanos` в этом примере используется тип `sfixed32`, который более эффективно кодируется, чем `int32` для больших значений.</span><span class="sxs-lookup"><span data-stu-id="579f5-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="579f5-170">Если поле `units` имеет отрицательное значение, поле `nanos` также должно быть отрицательным.</span><span class="sxs-lookup"><span data-stu-id="579f5-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="579f5-171">Существует несколько других алгоритмов кодирования `decimal` значений в виде строк байтов, но это сообщение проще понять, чем любое из них.</span><span class="sxs-lookup"><span data-stu-id="579f5-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="579f5-172">На значения не влияют порядок следования байтов на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="579f5-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="579f5-173">Преобразование между этим типом и типом BCL `decimal` может быть реализовано C# следующим образом:</span><span class="sxs-lookup"><span data-stu-id="579f5-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="579f5-174">При использовании пользовательских типов сообщений, таких как это, *необходимо* документировать их с помощью комментариев в `.proto`.</span><span class="sxs-lookup"><span data-stu-id="579f5-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="579f5-175">Другие разработчики могут затем реализовать преобразование в эквивалентный тип и из него на своем языке или в собственной платформе.</span><span class="sxs-lookup"><span data-stu-id="579f5-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="579f5-176">[Назад](protobuf-messages.md)
>[Вперед](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="579f5-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
