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
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a>Protobuf поля и Онеоф для типов Variant

Обработка динамических типов свойств (то есть свойств типа `object`) в WCF сложна. Должны быть указаны сериализаторы, должны быть предоставлены атрибуты [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) и т. д.

Protobuf предоставляет два простых параметра для работы со значениями, которые могут быть более одного типа. Тип `Any` может представлять любой известный тип сообщений protobuf, а ключевое слово `oneof` позволяет указать, что в любом конкретном сообщении может быть задан только один из диапазонов полей.

## <a name="any"></a>Любой

`Any` является одним из protobuf "хорошо известных типов": набор полезных, многократно используемых типов сообщений с реализациями на всех поддерживаемых языках. Чтобы использовать тип `Any`, необходимо импортировать определение `google/protobuf/any.proto`.

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

В C# коде класс `Any` предоставляет методы для задания поля, извлечения сообщения и проверки типа.

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

`Descriptor` статическое поле для каждого сформированного типа используется внутренним кодом отражения protobuf для разрешения типов полей `Any`. Существует также `TryUnpack<T>` метод, который создает неинициализированный экземпляр `T` даже в случае сбоя, поэтому лучше использовать метод `Is`, как показано выше.

## <a name="oneof"></a>онеоф

Онеоф поля — это языковая функция: ключевое слово `oneof` обрабатывается компилятором при формировании класса сообщений. Использование `oneof` для указания `ChangeNotification` сообщения может выглядеть следующим образом:

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

Поля в наборе `oneof` должны иметь уникальные номера полей в общем объявлении сообщения.

При использовании `oneof`созданный C# код включает перечисление, указывающее, какое из полей было задано. Можно проверить перечисление, чтобы узнать, какое поле задается. Поля, которые не задают возвращаемые `null` или значение по умолчанию, вместо создания исключения.

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

При установке любого поля, которое является частью набора `oneof`, автоматически очищаются все другие поля в наборе. Нельзя использовать `repeated` с `oneof`. Вместо этого можно создать вложенное сообщение с повторяющимся полем или набором `oneof`, чтобы обойти это ограничение.

>[!div class="step-by-step"]
>[Назад](protobuf-reserved.md)
>[Вперед](protobuf-enums.md)
