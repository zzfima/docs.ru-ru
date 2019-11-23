---
title: Protobuf поля и Онеоф для типов Variant-gRPC для разработчиков WCF
description: Узнайте, как использовать любые типы и ключевое слово Онеоф для представления типов объектов Variant в сообщениях.
ms.date: 09/09/2019
ms.openlocfilehash: af3ba22c238aa80a8c6119f62d5d8914770cad68
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971615"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="a9494-103">Protobuf поля и Онеоф для типов Variant</span><span class="sxs-lookup"><span data-stu-id="a9494-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="a9494-104">Обработка динамических типов свойств (то есть свойств типа `object`) в WCF сложна.</span><span class="sxs-lookup"><span data-stu-id="a9494-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="a9494-105">Должны быть указаны сериализаторы, должны быть предоставлены атрибуты [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) и т. д.</span><span class="sxs-lookup"><span data-stu-id="a9494-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="a9494-106">Protobuf предоставляет два простых параметра для работы со значениями, которые могут быть более одного типа.</span><span class="sxs-lookup"><span data-stu-id="a9494-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="a9494-107">Тип `Any` может представлять любой известный тип сообщений protobuf, а ключевое слово `oneof` позволяет указать, что в любом конкретном сообщении может быть задан только один из диапазонов полей.</span><span class="sxs-lookup"><span data-stu-id="a9494-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="a9494-108">Любой</span><span class="sxs-lookup"><span data-stu-id="a9494-108">Any</span></span>

<span data-ttu-id="a9494-109">`Any` является одним из protobuf "хорошо известных типов": набор полезных, многократно используемых типов сообщений с реализациями на всех поддерживаемых языках.</span><span class="sxs-lookup"><span data-stu-id="a9494-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="a9494-110">Чтобы использовать тип `Any`, необходимо импортировать определение `google/protobuf/any.proto`.</span><span class="sxs-lookup"><span data-stu-id="a9494-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

<span data-ttu-id="a9494-111">В C# коде класс `Any` предоставляет методы для задания поля, извлечения сообщения и проверки типа.</span><span class="sxs-lookup"><span data-stu-id="a9494-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="a9494-112">`Descriptor` статическое поле для каждого сформированного типа используется внутренним кодом отражения protobuf для разрешения типов полей `Any`.</span><span class="sxs-lookup"><span data-stu-id="a9494-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="a9494-113">Существует также `TryUnpack<T>` метод, который создает неинициализированный экземпляр `T` даже в случае сбоя, поэтому лучше использовать метод `Is`, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="a9494-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="a9494-114">онеоф</span><span class="sxs-lookup"><span data-stu-id="a9494-114">Oneof</span></span>

<span data-ttu-id="a9494-115">Онеоф поля — это языковая функция: ключевое слово `oneof` обрабатывается компилятором при формировании класса сообщений.</span><span class="sxs-lookup"><span data-stu-id="a9494-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="a9494-116">Использование `oneof` для указания `ChangeNotification` сообщения может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9494-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

<span data-ttu-id="a9494-117">Поля в наборе `oneof` должны иметь уникальные номера полей в общем объявлении сообщения.</span><span class="sxs-lookup"><span data-stu-id="a9494-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="a9494-118">При использовании `oneof`созданный C# код включает перечисление, указывающее, какое из полей было задано.</span><span class="sxs-lookup"><span data-stu-id="a9494-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="a9494-119">Можно проверить перечисление, чтобы узнать, какое поле задается.</span><span class="sxs-lookup"><span data-stu-id="a9494-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="a9494-120">Поля, которые не задают возвращаемые `null` или значение по умолчанию, вместо создания исключения.</span><span class="sxs-lookup"><span data-stu-id="a9494-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="a9494-121">При установке любого поля, которое является частью набора `oneof`, автоматически очищаются все другие поля в наборе.</span><span class="sxs-lookup"><span data-stu-id="a9494-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="a9494-122">Нельзя использовать `repeated` с `oneof`.</span><span class="sxs-lookup"><span data-stu-id="a9494-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="a9494-123">Вместо этого можно создать вложенное сообщение с повторяющимся полем или набором `oneof`, чтобы обойти это ограничение.</span><span class="sxs-lookup"><span data-stu-id="a9494-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a9494-124">[Назад](protobuf-reserved.md)
>[Вперед](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="a9494-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
