---
title: Protobuf перечисления - gRPC для разработчиков WCF
description: Узнайте, как декларировать и использовать перечисления в Protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148079"
---
# <a name="protobuf-enumerations"></a>Перечисления Protobuf

Protobuf поддерживает типы перечисления. Вы видели эту поддержку в предыдущем разделе, где для определения `Oneof` типа поля использовался enum. Вы можете определить свои собственные типы перечисления, и Protobuf будет компилировать их в типах C' enum.

Поскольку протобуф можно использовать с различными языками, конвенции именования для перечислений отличаются от конвенций C.'. Тем не менее, генератор кода преобразует имена в традиционный корпус C'. Если эквивалент имени поля Pascal начинается с имени перечисления, то оно удаляется.

Например, в следующем перечислении Protobuf поля прикрепляются с `ACCOUNT_STATUS`. Эта приставка эквивалентна названию перечисления `AccountStatus`pascal-case.

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

Генератор создает enum, эквивалентный следующему коду:

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

Определения перечисления Protobuf *должны* иметь нулевую константу в качестве своего первого поля. Как и в C, можно объявить несколько полей с одинаковым значением. Но вы должны явно включить эту `allow_alias` опцию, используя опцию в enum:

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

Вы можете объявить перечисления на верхнем уровне в файле `.proto` или вложенные в определение сообщения. Вложенные перечисления, например вложенные сообщения, будут `.Types` объявлены в статический класс в сгенерированном классе сообщений.

Нет никакого способа применить атрибут [«Флаги»](xref:System.FlagsAttribute) к enum, генерируемому Протобуфом, и Протобуф не понимает битомые комбинации enum. Посмотрите на следующий пример:

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

Если вы `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`установите, это сериализовано как `3`целый значение. Когда клиент или сервер пытается десериализировать значение, он не найдет совпадения в определении enum для `3`. Результат будет `Region.None`.

Лучший способ работы с несколькими значениями в Протобуфе — использовать `repeated` поле типа enum.

>[!div class="step-by-step"]
>[Предыдущий](protobuf-any-oneof.md)
>[Следующий](protobuf-maps.md)
