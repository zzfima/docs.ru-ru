---
title: Перечисления protobuf — gRPC для разработчиков WCF
description: Сведения об объявлении и использовании перечислений в protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 4ea4d03bede2a9ebfd1f2c3ee56f299e918800e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971579"
---
# <a name="protobuf-enumerations"></a>Перечисления Protobuf

Protobuf поддерживает типы перечисления, как показано в предыдущем разделе, где для определения типа поля `oneof` использовалось перечисление. Можно определить собственные типы перечисления, и protobuf будет компилировать их в C# типы Enum. Так как protobuf можно использовать с различными языками, соглашения об именовании для перечислений отличаются C# от соглашений. Однако генератор кода является разумным и преобразует имена в традиционный C# регистр. Если в стиле Pascal, эквивалентном имени поля, начинается имя перечисления, то оно удаляется.

Например, в этом перечислении protobuf поля добавляются с префиксом `ACCOUNT_STATUS`, что эквивалентно имени перечисления в стиле Pascal: `AccountStatus`.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Таким образом, генератор создает C# перечисление, эквивалентное следующему коду:

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

Определения перечисления protobuf **должны** иметь нулевую константу в качестве первого поля. Как и C#в, можно объявить несколько полей с одинаковым значением, но необходимо явно включить этот параметр с помощью параметра `allow_alias` в перечислении:

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

Перечисления можно объявить на верхнем уровне в `.proto`ном файле или вложить в определение сообщения. Вложенные перечисления, такие как вложенные сообщения, будут объявлены в статическом классе `.Types` в созданном классе сообщений.

Невозможно применить атрибут [[flags]](xref:System.FlagsAttribute) к перечислению, созданному protobuf, а protobuf не понимает побитовое сочетание перечислений. Взгляните на следующий пример:

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

Если для `product.AvailableIn` задано значение `Region.NorthAmerica | Region.SouthAmerica`, оно сериализуется как целое число `3`. Когда клиент или сервер пытается десериализовать значение, он не находит совпадение в определении перечисления для `3` и результат будет `Region.None`.

Лучшим способом работы с несколькими перечисляемыми значениями в protobuf является использование поля `repeated` типа Enum.

>[!div class="step-by-step"]
>[Назад](protobuf-any-oneof.md)
>[Вперед](protobuf-maps.md)
