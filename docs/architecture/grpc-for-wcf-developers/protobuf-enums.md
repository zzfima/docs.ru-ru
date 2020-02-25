---
title: Перечисления protobuf — gRPC для разработчиков WCF
description: Сведения об объявлении и использовании перечислений в protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543148"
---
# <a name="protobuf-enumerations"></a>Перечисления Protobuf

Protobuf поддерживает типы перечисления. Вы видели эту поддержку в предыдущем разделе, где для определения типа поля `Oneof` использовалось перечисление. Можно определить собственные типы перечисления, а protobuf будет компилировать их в C# типы Enum. 

Так как вы можете использовать protobuf с различными языками, соглашения об именовании для перечислений C# отличаются от соглашений. Однако генератор кода преобразует имена в традиционный C# регистр. Если в стиле Pascal, эквивалентном имени поля, начинается имя перечисления, то оно удаляется.

Например, в следующем перечислении protobuf поля начинаются с префикса `ACCOUNT_STATUS`. Этот префикс эквивалентен имени перечисления Pascal-Case `AccountStatus`.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Генератор создает перечисление, C# эквивалентное следующему коду:

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

Определения перечисления protobuf *должны* иметь нулевую константу в качестве первого поля. Как и C#в, можно объявить несколько полей с одинаковым значением. Но этот параметр необходимо явно включить с помощью параметра `allow_alias` в перечислении:

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

Невозможно применить атрибут [[flags]](xref:System.FlagsAttribute) к перечислению, созданному protobuf, а protobuf не понимает побитовое сочетание перечислений. Рассмотрим следующий пример:

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

Если для `product.AvailableIn` задано значение `Region.NorthAmerica | Region.SouthAmerica`, оно сериализуется как целое число `3`. Когда клиент или сервер пытается десериализовать значение, он не находит совпадения в определении перечисления для `3`. Результат будет `Region.None`.

Лучшим способом работы с несколькими перечисляемыми значениями в protobuf является использование поля `repeated` типа Enum.

>[!div class="step-by-step"]
>[Назад](protobuf-any-oneof.md)
>[Вперед](protobuf-maps.md)
