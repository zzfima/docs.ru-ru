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
# <a name="protobuf-enumerations"></a><span data-ttu-id="06cb2-103">Перечисления Protobuf</span><span class="sxs-lookup"><span data-stu-id="06cb2-103">Protobuf enumerations</span></span>

<span data-ttu-id="06cb2-104">Protobuf поддерживает типы перечисления.</span><span class="sxs-lookup"><span data-stu-id="06cb2-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="06cb2-105">Вы видели эту поддержку в предыдущем разделе, где для определения `Oneof` типа поля использовался enum.</span><span class="sxs-lookup"><span data-stu-id="06cb2-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="06cb2-106">Вы можете определить свои собственные типы перечисления, и Protobuf будет компилировать их в типах C' enum.</span><span class="sxs-lookup"><span data-stu-id="06cb2-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span>

<span data-ttu-id="06cb2-107">Поскольку протобуф можно использовать с различными языками, конвенции именования для перечислений отличаются от конвенций C.'.</span><span class="sxs-lookup"><span data-stu-id="06cb2-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="06cb2-108">Тем не менее, генератор кода преобразует имена в традиционный корпус C'.</span><span class="sxs-lookup"><span data-stu-id="06cb2-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="06cb2-109">Если эквивалент имени поля Pascal начинается с имени перечисления, то оно удаляется.</span><span class="sxs-lookup"><span data-stu-id="06cb2-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="06cb2-110">Например, в следующем перечислении Protobuf поля прикрепляются с `ACCOUNT_STATUS`.</span><span class="sxs-lookup"><span data-stu-id="06cb2-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="06cb2-111">Эта приставка эквивалентна названию перечисления `AccountStatus`pascal-case.</span><span class="sxs-lookup"><span data-stu-id="06cb2-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="06cb2-112">Генератор создает enum, эквивалентный следующему коду:</span><span class="sxs-lookup"><span data-stu-id="06cb2-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="06cb2-113">Определения перечисления Protobuf *должны* иметь нулевую константу в качестве своего первого поля.</span><span class="sxs-lookup"><span data-stu-id="06cb2-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="06cb2-114">Как и в C, можно объявить несколько полей с одинаковым значением.</span><span class="sxs-lookup"><span data-stu-id="06cb2-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="06cb2-115">Но вы должны явно включить эту `allow_alias` опцию, используя опцию в enum:</span><span class="sxs-lookup"><span data-stu-id="06cb2-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="06cb2-116">Вы можете объявить перечисления на верхнем уровне в файле `.proto` или вложенные в определение сообщения.</span><span class="sxs-lookup"><span data-stu-id="06cb2-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="06cb2-117">Вложенные перечисления, например вложенные сообщения, будут `.Types` объявлены в статический класс в сгенерированном классе сообщений.</span><span class="sxs-lookup"><span data-stu-id="06cb2-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="06cb2-118">Нет никакого способа применить атрибут [«Флаги»](xref:System.FlagsAttribute) к enum, генерируемому Протобуфом, и Протобуф не понимает битомые комбинации enum.</span><span class="sxs-lookup"><span data-stu-id="06cb2-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="06cb2-119">Посмотрите на следующий пример:</span><span class="sxs-lookup"><span data-stu-id="06cb2-119">Look at the following example:</span></span>

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

<span data-ttu-id="06cb2-120">Если вы `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`установите, это сериализовано как `3`целый значение.</span><span class="sxs-lookup"><span data-stu-id="06cb2-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="06cb2-121">Когда клиент или сервер пытается десериализировать значение, он не найдет совпадения в определении enum для `3`.</span><span class="sxs-lookup"><span data-stu-id="06cb2-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="06cb2-122">Результат будет `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="06cb2-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="06cb2-123">Лучший способ работы с несколькими значениями в Протобуфе — использовать `repeated` поле типа enum.</span><span class="sxs-lookup"><span data-stu-id="06cb2-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06cb2-124">[Предыдущий](protobuf-any-oneof.md)
>[Следующий](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="06cb2-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
