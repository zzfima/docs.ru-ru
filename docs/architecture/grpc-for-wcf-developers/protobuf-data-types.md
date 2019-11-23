---
title: Protobuf скалярные типы данных — gRPC для разработчиков WCF
description: Сведения об основных и хорошо известных типах данных, поддерживаемых protobuf и gRPC в .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: ae7f5f48099000dff0eefb36e23cb9b9f2ac517c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971554"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="61855-103">Скалярные типы данных Protobuf</span><span class="sxs-lookup"><span data-stu-id="61855-103">Protobuf scalar data types</span></span>

<span data-ttu-id="61855-104">Protobuf поддерживает ряд собственных скалярных типов значений.</span><span class="sxs-lookup"><span data-stu-id="61855-104">Protobuf supports a range of native scalar value types.</span></span> <span data-ttu-id="61855-105">В следующей таблице перечислены все типы с эквивалентными C# типами:</span><span class="sxs-lookup"><span data-stu-id="61855-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="61855-106">Тип protobuf</span><span class="sxs-lookup"><span data-stu-id="61855-106">Protobuf type</span></span> | <span data-ttu-id="61855-107">Тип C#</span><span class="sxs-lookup"><span data-stu-id="61855-107">C# type</span></span>      | <span data-ttu-id="61855-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="61855-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="61855-109">1</span><span class="sxs-lookup"><span data-stu-id="61855-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="61855-110">1</span><span class="sxs-lookup"><span data-stu-id="61855-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="61855-111">1</span><span class="sxs-lookup"><span data-stu-id="61855-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="61855-112">1</span><span class="sxs-lookup"><span data-stu-id="61855-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="61855-113">2</span><span class="sxs-lookup"><span data-stu-id="61855-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="61855-114">2</span><span class="sxs-lookup"><span data-stu-id="61855-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="61855-115">2</span><span class="sxs-lookup"><span data-stu-id="61855-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="61855-116">2</span><span class="sxs-lookup"><span data-stu-id="61855-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="61855-117">3</span><span class="sxs-lookup"><span data-stu-id="61855-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="61855-118">4</span><span class="sxs-lookup"><span data-stu-id="61855-118">4</span></span>     |

## <a name="notes"></a><span data-ttu-id="61855-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="61855-119">Notes</span></span>

1. <span data-ttu-id="61855-120">Стандартная кодировка для `int32` и `int64` неэффективна при работе со значениями со знаком.</span><span class="sxs-lookup"><span data-stu-id="61855-120">The standard encoding for `int32` and `int64` is inefficient when working with signed values.</span></span> <span data-ttu-id="61855-121">Если в поле могут содержаться отрицательные числа, используйте вместо него `sint32` или `sint64`.</span><span class="sxs-lookup"><span data-stu-id="61855-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="61855-122">Оба типа сопоставляются с C# типами `int` и `long` соответственно.</span><span class="sxs-lookup"><span data-stu-id="61855-122">Both types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="61855-123">`fixed` поля всегда используют одинаковое число байтов независимо от значения.</span><span class="sxs-lookup"><span data-stu-id="61855-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="61855-124">Такое поведение позволяет ускорить сериализацию и десериализацию для больших значений.</span><span class="sxs-lookup"><span data-stu-id="61855-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="61855-125">Строки protobuf имеют кодировку UTF-8 (или 7-разрядный код ASCII), а длина кодировки не может превышать 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="61855-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded, and the encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="61855-126">Среда выполнения protobuf предоставляет тип `ByteString`, который легко сопоставляется с `byte[]` C# массивами и из них.</span><span class="sxs-lookup"><span data-stu-id="61855-126">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="61855-127">Другие типы-примитивы .NET</span><span class="sxs-lookup"><span data-stu-id="61855-127">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="61855-128">Значения даты и времени</span><span class="sxs-lookup"><span data-stu-id="61855-128">Dates and times</span></span>

<span data-ttu-id="61855-129">Собственные скалярные типы не предоставляют значения даты и времени, эквиваленты C#<xref:System.DateTimeOffset>, <xref:System.DateTime>и <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="61855-129">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="61855-130">Эти типы можно указать с помощью некоторых расширений Google "хорошо известных типов", которые обеспечивают создание кода и поддержку среды выполнения для более сложных типов полей на поддерживаемых платформах.</span><span class="sxs-lookup"><span data-stu-id="61855-130">These types can be specified using some of Google's "Well Known Types" extensions, which provide code generation and runtime support for more complex field types across the supported platforms.</span></span> <span data-ttu-id="61855-131">В следующей таблице показаны типы даты и времени.</span><span class="sxs-lookup"><span data-stu-id="61855-131">The following table shows the date and time types:</span></span>

| <span data-ttu-id="61855-132">Тип C#</span><span class="sxs-lookup"><span data-stu-id="61855-132">C# type</span></span> | <span data-ttu-id="61855-133">Известный тип protobuf</span><span class="sxs-lookup"><span data-stu-id="61855-133">Protobuf well-known type</span></span> |
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

<span data-ttu-id="61855-134">Созданные свойства в C# классе не являются типами даты и времени .NET.</span><span class="sxs-lookup"><span data-stu-id="61855-134">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="61855-135">Свойства используют классы `Timestamp` и `Duration` в пространстве имен `Google.Protobuf.WellKnownTypes`, которые предоставляют методы для преобразования в `DateTimeOffset`, `DateTime`и `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="61855-135">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace, which provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="61855-136">Тип `Timestamp` работает со временем в формате UTC; `DateTimeOffset` значения всегда имеют нулевое смещение, а свойство `DateTime.Kind` всегда будет `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="61855-136">The `Timestamp` type works with UTC times; `DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property will always be `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="61855-137">System.Guid</span><span class="sxs-lookup"><span data-stu-id="61855-137">System.Guid</span></span>

<span data-ttu-id="61855-138">Тип <xref:System.Guid>, известный как `UUID` на других платформах, не поддерживается напрямую protobuf, и для него не существует хорошо известного типа.</span><span class="sxs-lookup"><span data-stu-id="61855-138">The <xref:System.Guid> type, known as `UUID` on other platforms, isn't directly supported by Protobuf and there's no well-known type for it.</span></span> <span data-ttu-id="61855-139">Наилучший подход заключается в обработке `Guid` значений в виде `string` поля, используя стандартный `8-4-4-4-12` шестнадцатеричный формат (например, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), который может быть проанализирован всеми языками и платформами.</span><span class="sxs-lookup"><span data-stu-id="61855-139">The best approach is to handle `Guid` values as `string` field, using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), which can be parsed by all languages and platforms.</span></span> <span data-ttu-id="61855-140">Не используйте `bytes` поле для `Guid` значений, так как проблемы с порядок следования байтов могут привести к неустойчивому поведению при взаимодействии с другими платформами, такими как Java.</span><span class="sxs-lookup"><span data-stu-id="61855-140">Don't use a `bytes` field for `Guid` values, as problems with endianness can result in erratic behavior when interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="61855-141">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="61855-141">Nullable types</span></span>

<span data-ttu-id="61855-142">При создании кода protobuf для C# используются собственные типы, например `int` для `int32`.</span><span class="sxs-lookup"><span data-stu-id="61855-142">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="61855-143">Это означает, что значения всегда включены и не могут иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="61855-143">This means that the values are always included and can't be null.</span></span> <span data-ttu-id="61855-144">Для значений, для которых требуется явное значение null, например использование C# `int?` в коде, protobuf "хорошо известные типы" включает оболочки, компилируемые в типы C# , допускающие значение null.</span><span class="sxs-lookup"><span data-stu-id="61855-144">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="61855-145">Чтобы использовать их, импортируйте `wrappers.proto` в файл `.proto` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="61855-145">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="61855-146">Protobuf будет использовать простое `T?` (например `int?`) для создаваемого свойства сообщения.</span><span class="sxs-lookup"><span data-stu-id="61855-146">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="61855-147">В следующей таблице приведен полный список типов оболочек с эквивалентным C# типом:</span><span class="sxs-lookup"><span data-stu-id="61855-147">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="61855-148">Тип C#</span><span class="sxs-lookup"><span data-stu-id="61855-148">C# type</span></span>   | <span data-ttu-id="61855-149">Оболочка хорошо известных типов</span><span class="sxs-lookup"><span data-stu-id="61855-149">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="61855-150">Хорошо известные типы `Timestamp` и `Duration` представлены в .NET как классы, поэтому нет необходимости в версии, допускающей значение null, но при преобразовании в `DateTimeOffset` или `TimeSpan`важно проверять наличие значения NULL в свойствах этих типов.</span><span class="sxs-lookup"><span data-stu-id="61855-150">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version, but it's important to check for null on properties of those types when converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="61855-151">Десятичные числа</span><span class="sxs-lookup"><span data-stu-id="61855-151">Decimals</span></span>

<span data-ttu-id="61855-152">Protobuf изначально не поддерживает тип .NET `decimal`, просто `double` и `float`.</span><span class="sxs-lookup"><span data-stu-id="61855-152">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="61855-153">В проекте protobuf есть текущее обсуждение о возможности добавления стандартного типа `Decimal` к хорошо известным типам с поддержкой платформы для языков и платформ, поддерживающих эту возможность, но пока ничего не реализовано.</span><span class="sxs-lookup"><span data-stu-id="61855-153">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it, but nothing has been implemented yet.</span></span>

<span data-ttu-id="61855-154">Можно создать определение сообщения, представляющее тип `decimal`, который будет работать для надежной сериализации между клиентами и серверами .NET, но разработчики на других платформах должны понимать, какой формат используется, и реализовать их собственную обработку.</span><span class="sxs-lookup"><span data-stu-id="61855-154">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers, but developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="61855-155">Создание пользовательского десятичного типа для protobuf</span><span class="sxs-lookup"><span data-stu-id="61855-155">Creating a custom Decimal type for Protobuf</span></span>

<span data-ttu-id="61855-156">Очень простая реализация может быть похожа на нестандартный тип `Money`, используемый некоторыми API-интерфейсами Google, без поля `currency`.</span><span class="sxs-lookup"><span data-stu-id="61855-156">A very simple implementation could be similar to the non-standard `Money` type used by some Google APIs, without the `currency` field.</span></span>

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

<span data-ttu-id="61855-157">Поле `nanos` представляет значения из `0.999_999_999` в `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="61855-157">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="61855-158">Например, `decimal` значение `1.5m` будет представляться как `{ units = 1, nanos = 500_000_000 }` (именно поэтому в поле `nanos` в этом примере используется тип `sfixed32`, который более эффективно кодируется, чем `int32` для больших значений).</span><span class="sxs-lookup"><span data-stu-id="61855-158">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }` (this is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values).</span></span> <span data-ttu-id="61855-159">Если поле `units` имеет отрицательное значение, поле `nanos` также должно быть отрицательным.</span><span class="sxs-lookup"><span data-stu-id="61855-159">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="61855-160">Существует несколько других алгоритмов кодирования `decimal` значений в виде строк байтов, но это сообщение гораздо проще понять, чем любое из них, и значения не затрагиваются *[порядок следования байтов](https://en.wikipedia.org/wiki/Endianness)* на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="61855-160">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is much easier to understand than any of them, and the values are not affected by *[endianness](https://en.wikipedia.org/wiki/Endianness)* on different platforms.</span></span>

<span data-ttu-id="61855-161">Преобразование между этим типом и типом BCL `decimal` может быть реализовано в C# следующим образом.</span><span class="sxs-lookup"><span data-stu-id="61855-161">Conversion between this type and the BCL `decimal` type could be implemented in C# like this.</span></span>

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
> <span data-ttu-id="61855-162">При использовании таких типов сообщений служебной программы, как это, **необходимо** документировать их с комментариями в `.proto`, чтобы другие разработчики могли реализовать преобразование в эквивалентный тип и из него на своем языке или в собственной платформе.</span><span class="sxs-lookup"><span data-stu-id="61855-162">Whenever you use custom utility message types like this, you **must** document them with comments in the `.proto` so that other developers can implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="61855-163">[Назад](protobuf-messages.md)
>[Вперед](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="61855-163">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
