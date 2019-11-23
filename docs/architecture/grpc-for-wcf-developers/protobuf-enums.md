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
# <a name="protobuf-enumerations"></a><span data-ttu-id="85cec-103">Перечисления Protobuf</span><span class="sxs-lookup"><span data-stu-id="85cec-103">Protobuf enumerations</span></span>

<span data-ttu-id="85cec-104">Protobuf поддерживает типы перечисления, как показано в предыдущем разделе, где для определения типа поля `oneof` использовалось перечисление.</span><span class="sxs-lookup"><span data-stu-id="85cec-104">Protobuf supports enumeration types, as seen in the previous section where an enum was used to determine the type of a `oneof` field.</span></span> <span data-ttu-id="85cec-105">Можно определить собственные типы перечисления, и protobuf будет компилировать их в C# типы Enum.</span><span class="sxs-lookup"><span data-stu-id="85cec-105">You can define your own enumeration types and Protobuf will compile them to C# enum types.</span></span> <span data-ttu-id="85cec-106">Так как protobuf можно использовать с различными языками, соглашения об именовании для перечислений отличаются C# от соглашений.</span><span class="sxs-lookup"><span data-stu-id="85cec-106">Since Protobuf can be used with different languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="85cec-107">Однако генератор кода является разумным и преобразует имена в традиционный C# регистр.</span><span class="sxs-lookup"><span data-stu-id="85cec-107">However, the code generator is clever and converts the names to the traditional C# case.</span></span> <span data-ttu-id="85cec-108">Если в стиле Pascal, эквивалентном имени поля, начинается имя перечисления, то оно удаляется.</span><span class="sxs-lookup"><span data-stu-id="85cec-108">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="85cec-109">Например, в этом перечислении protobuf поля добавляются с префиксом `ACCOUNT_STATUS`, что эквивалентно имени перечисления в стиле Pascal: `AccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="85cec-109">For example, in this Protobuf enumeration the fields are prefixed with `ACCOUNT_STATUS`, which is equivalent to the Pascal case enum name: `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="85cec-110">Таким образом, генератор создает C# перечисление, эквивалентное следующему коду:</span><span class="sxs-lookup"><span data-stu-id="85cec-110">So, the generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="85cec-111">Определения перечисления protobuf **должны** иметь нулевую константу в качестве первого поля.</span><span class="sxs-lookup"><span data-stu-id="85cec-111">Protobuf enumeration definitions **must** have a zero constant as their first field.</span></span> <span data-ttu-id="85cec-112">Как и C#в, можно объявить несколько полей с одинаковым значением, но необходимо явно включить этот параметр с помощью параметра `allow_alias` в перечислении:</span><span class="sxs-lookup"><span data-stu-id="85cec-112">As in C#, you can declare multiple fields with the same value, but you must explicitly enable this option using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="85cec-113">Перечисления можно объявить на верхнем уровне в `.proto`ном файле или вложить в определение сообщения.</span><span class="sxs-lookup"><span data-stu-id="85cec-113">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="85cec-114">Вложенные перечисления, такие как вложенные сообщения, будут объявлены в статическом классе `.Types` в созданном классе сообщений.</span><span class="sxs-lookup"><span data-stu-id="85cec-114">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="85cec-115">Невозможно применить атрибут [[flags]](xref:System.FlagsAttribute) к перечислению, созданному protobuf, а protobuf не понимает побитовое сочетание перечислений.</span><span class="sxs-lookup"><span data-stu-id="85cec-115">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="85cec-116">Взгляните на следующий пример:</span><span class="sxs-lookup"><span data-stu-id="85cec-116">Take a look at the following example:</span></span>

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

<span data-ttu-id="85cec-117">Если для `product.AvailableIn` задано значение `Region.NorthAmerica | Region.SouthAmerica`, оно сериализуется как целое число `3`.</span><span class="sxs-lookup"><span data-stu-id="85cec-117">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="85cec-118">Когда клиент или сервер пытается десериализовать значение, он не находит совпадение в определении перечисления для `3` и результат будет `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="85cec-118">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3` and the result will be `Region.None`.</span></span>

<span data-ttu-id="85cec-119">Лучшим способом работы с несколькими перечисляемыми значениями в protobuf является использование поля `repeated` типа Enum.</span><span class="sxs-lookup"><span data-stu-id="85cec-119">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="85cec-120">[Назад](protobuf-any-oneof.md)
>[Вперед](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="85cec-120">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
