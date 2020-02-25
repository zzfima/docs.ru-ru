---
title: Protobuf поля и Онеоф для типов Variant-gRPC для разработчиков WCF
description: Узнайте, как использовать любые типы и ключевое слово Онеоф для представления типов объектов Variant в сообщениях.
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543200"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="33c04-103">Protobuf поля и Онеоф для типов Variant</span><span class="sxs-lookup"><span data-stu-id="33c04-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="33c04-104">Обработка типов динамических свойств (то есть свойств типа `object`) в Windows Communication Foundation (WCF) является сложной.</span><span class="sxs-lookup"><span data-stu-id="33c04-104">Handling dynamic property types (that is, properties of type `object`) in Windows Communication Foundation (WCF) is complicated.</span></span> <span data-ttu-id="33c04-105">Например, необходимо указать сериализаторы и предоставить атрибуты [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="33c04-105">For example, you must specify serializers and provide [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes.</span></span>

<span data-ttu-id="33c04-106">Протокол buffer (protobuf) предоставляет два простых параметра для работы со значениями, которые могут быть более одного типа.</span><span class="sxs-lookup"><span data-stu-id="33c04-106">Protocol Buffer (Protobuf) provides two simpler options for dealing with values that might be of more than one type.</span></span> <span data-ttu-id="33c04-107">Тип `Any` может представлять любой известный тип сообщений protobuf.</span><span class="sxs-lookup"><span data-stu-id="33c04-107">The `Any` type can represent any known Protobuf message type.</span></span> <span data-ttu-id="33c04-108">Кроме того, можно использовать ключевое слово `oneof`, чтобы указать, что в любом сообщении можно задать только один из диапазонов полей.</span><span class="sxs-lookup"><span data-stu-id="33c04-108">And you can use the `oneof` keyword to specify that only one of a range of fields can be set in any message.</span></span>

## <a name="any"></a><span data-ttu-id="33c04-109">Любой</span><span class="sxs-lookup"><span data-stu-id="33c04-109">Any</span></span>

<span data-ttu-id="33c04-110">`Any` является одним из protobuf "хорошо известных типов": набор полезных, многократно используемых типов сообщений с реализациями на всех поддерживаемых языках.</span><span class="sxs-lookup"><span data-stu-id="33c04-110">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="33c04-111">Чтобы использовать тип `Any`, необходимо импортировать определение `google/protobuf/any.proto`.</span><span class="sxs-lookup"><span data-stu-id="33c04-111">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="33c04-112">В C# коде класс `Any` предоставляет методы для задания поля, извлечения сообщения и проверки типа.</span><span class="sxs-lookup"><span data-stu-id="33c04-112">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="33c04-113">Внутренний код отражения protobuf использует статическое поле `Descriptor` для каждого сформированного типа для разрешения `Any` типов полей.</span><span class="sxs-lookup"><span data-stu-id="33c04-113">Protobuf's internal reflection code uses the `Descriptor` static field on each generated type to resolve `Any` field types.</span></span> <span data-ttu-id="33c04-114">Существует также `TryUnpack<T>` метод, который создает неинициализированный экземпляр `T` даже в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="33c04-114">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails.</span></span> <span data-ttu-id="33c04-115">Лучше использовать метод `Is`, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="33c04-115">It's better to use the `Is` method as shown earlier.</span></span>

## <a name="oneof"></a><span data-ttu-id="33c04-116">онеоф</span><span class="sxs-lookup"><span data-stu-id="33c04-116">Oneof</span></span>

<span data-ttu-id="33c04-117">Поля онеоф — это языковая функция: Компилятор обрабатывает ключевое слово `oneof` при формировании класса Message.</span><span class="sxs-lookup"><span data-stu-id="33c04-117">Oneof fields are a language feature: the compiler handles the `oneof` keyword when it generates the message class.</span></span> <span data-ttu-id="33c04-118">Использование `oneof` для указания `ChangeNotification` сообщения может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33c04-118">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="33c04-119">Поля в наборе `oneof` должны иметь уникальные номера полей в общем объявлении сообщения.</span><span class="sxs-lookup"><span data-stu-id="33c04-119">Fields within the `oneof` set must have unique field numbers in the overall message declaration.</span></span>

<span data-ttu-id="33c04-120">При использовании `oneof`созданный C# код включает перечисление, указывающее, какое из полей было задано.</span><span class="sxs-lookup"><span data-stu-id="33c04-120">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="33c04-121">Можно проверить перечисление, чтобы узнать, какое поле задается.</span><span class="sxs-lookup"><span data-stu-id="33c04-121">You can test the enum to find which field is set.</span></span> <span data-ttu-id="33c04-122">Поля, которые не задают возвращаемые `null` или значение по умолчанию, вместо создания исключения.</span><span class="sxs-lookup"><span data-stu-id="33c04-122">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="33c04-123">При установке любого поля, которое является частью набора `oneof`, автоматически очищаются все другие поля в наборе.</span><span class="sxs-lookup"><span data-stu-id="33c04-123">Setting any field that's part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="33c04-124">Нельзя использовать `repeated` с `oneof`.</span><span class="sxs-lookup"><span data-stu-id="33c04-124">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="33c04-125">Вместо этого можно создать вложенное сообщение с повторяющимся полем или набором `oneof`, чтобы обойти это ограничение.</span><span class="sxs-lookup"><span data-stu-id="33c04-125">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="33c04-126">[Назад](protobuf-reserved.md)
>[Вперед](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="33c04-126">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
