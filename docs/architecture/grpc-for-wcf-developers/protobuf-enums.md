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
# <a name="protobuf-enumerations"></a><span data-ttu-id="3f154-103">Перечисления Protobuf</span><span class="sxs-lookup"><span data-stu-id="3f154-103">Protobuf enumerations</span></span>

<span data-ttu-id="3f154-104">Protobuf поддерживает типы перечисления.</span><span class="sxs-lookup"><span data-stu-id="3f154-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="3f154-105">Вы видели эту поддержку в предыдущем разделе, где для определения типа поля `Oneof` использовалось перечисление.</span><span class="sxs-lookup"><span data-stu-id="3f154-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="3f154-106">Можно определить собственные типы перечисления, а protobuf будет компилировать их в C# типы Enum.</span><span class="sxs-lookup"><span data-stu-id="3f154-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span> 

<span data-ttu-id="3f154-107">Так как вы можете использовать protobuf с различными языками, соглашения об именовании для перечислений C# отличаются от соглашений.</span><span class="sxs-lookup"><span data-stu-id="3f154-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="3f154-108">Однако генератор кода преобразует имена в традиционный C# регистр.</span><span class="sxs-lookup"><span data-stu-id="3f154-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="3f154-109">Если в стиле Pascal, эквивалентном имени поля, начинается имя перечисления, то оно удаляется.</span><span class="sxs-lookup"><span data-stu-id="3f154-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="3f154-110">Например, в следующем перечислении protobuf поля начинаются с префикса `ACCOUNT_STATUS`.</span><span class="sxs-lookup"><span data-stu-id="3f154-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="3f154-111">Этот префикс эквивалентен имени перечисления Pascal-Case `AccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="3f154-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="3f154-112">Генератор создает перечисление, C# эквивалентное следующему коду:</span><span class="sxs-lookup"><span data-stu-id="3f154-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="3f154-113">Определения перечисления protobuf *должны* иметь нулевую константу в качестве первого поля.</span><span class="sxs-lookup"><span data-stu-id="3f154-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="3f154-114">Как и C#в, можно объявить несколько полей с одинаковым значением.</span><span class="sxs-lookup"><span data-stu-id="3f154-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="3f154-115">Но этот параметр необходимо явно включить с помощью параметра `allow_alias` в перечислении:</span><span class="sxs-lookup"><span data-stu-id="3f154-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="3f154-116">Перечисления можно объявить на верхнем уровне в `.proto`ном файле или вложить в определение сообщения.</span><span class="sxs-lookup"><span data-stu-id="3f154-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="3f154-117">Вложенные перечисления, такие как вложенные сообщения, будут объявлены в статическом классе `.Types` в созданном классе сообщений.</span><span class="sxs-lookup"><span data-stu-id="3f154-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="3f154-118">Невозможно применить атрибут [[flags]](xref:System.FlagsAttribute) к перечислению, созданному protobuf, а protobuf не понимает побитовое сочетание перечислений.</span><span class="sxs-lookup"><span data-stu-id="3f154-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="3f154-119">Рассмотрим следующий пример:</span><span class="sxs-lookup"><span data-stu-id="3f154-119">Look at the following example:</span></span>

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

<span data-ttu-id="3f154-120">Если для `product.AvailableIn` задано значение `Region.NorthAmerica | Region.SouthAmerica`, оно сериализуется как целое число `3`.</span><span class="sxs-lookup"><span data-stu-id="3f154-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="3f154-121">Когда клиент или сервер пытается десериализовать значение, он не находит совпадения в определении перечисления для `3`.</span><span class="sxs-lookup"><span data-stu-id="3f154-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="3f154-122">Результат будет `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="3f154-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="3f154-123">Лучшим способом работы с несколькими перечисляемыми значениями в protobuf является использование поля `repeated` типа Enum.</span><span class="sxs-lookup"><span data-stu-id="3f154-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3f154-124">[Назад](protobuf-any-oneof.md)
>[Вперед](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="3f154-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
