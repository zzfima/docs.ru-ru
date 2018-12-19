---
title: Справочник по C#. Таблица неявных числовых преобразований
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 98774a0f7ad86e43178c6d0216e29e7b4767f3f2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235258"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="403fd-102">Таблица неявных числовых преобразований (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="403fd-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="403fd-103">В следующей таблице приведены предопределенные неявные преобразования между числовыми типами .NET.</span><span class="sxs-lookup"><span data-stu-id="403fd-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="403fd-104">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="403fd-104">From</span></span>|<span data-ttu-id="403fd-105">Кому</span><span class="sxs-lookup"><span data-stu-id="403fd-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="403fd-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="403fd-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="403fd-107">`short`, `int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-108">byte</span><span class="sxs-lookup"><span data-stu-id="403fd-108">byte</span></span>](byte.md)|<span data-ttu-id="403fd-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-110">short</span><span class="sxs-lookup"><span data-stu-id="403fd-110">short</span></span>](short.md)|<span data-ttu-id="403fd-111">`int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-111">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-112">ushort</span><span class="sxs-lookup"><span data-stu-id="403fd-112">ushort</span></span>](ushort.md)|<span data-ttu-id="403fd-113">`int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-113">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-114">int</span><span class="sxs-lookup"><span data-stu-id="403fd-114">int</span></span>](int.md)|<span data-ttu-id="403fd-115">`long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-115">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-116">uint</span><span class="sxs-lookup"><span data-stu-id="403fd-116">uint</span></span>](uint.md)|<span data-ttu-id="403fd-117">`long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-117">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-118">long</span><span class="sxs-lookup"><span data-stu-id="403fd-118">long</span></span>](long.md)|<span data-ttu-id="403fd-119">`float`, `double`или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-119">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-120">char</span><span class="sxs-lookup"><span data-stu-id="403fd-120">char</span></span>](char.md)|<span data-ttu-id="403fd-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="403fd-122">float</span><span class="sxs-lookup"><span data-stu-id="403fd-122">float</span></span>](float.md)|`double`|  
|[<span data-ttu-id="403fd-123">ulong</span><span class="sxs-lookup"><span data-stu-id="403fd-123">ulong</span></span>](ulong.md)|<span data-ttu-id="403fd-124">`float`, `double`или `decimal`</span><span class="sxs-lookup"><span data-stu-id="403fd-124">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="403fd-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="403fd-125">Remarks</span></span>  

- <span data-ttu-id="403fd-126">Любой [целочисленный тип](integral-types-table.md) неявно преобразуется к любому [типу с плавающей запятой](floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="403fd-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="403fd-127">При преобразовании из `int`, `uint`, `long` или `ulong` в `float` и из `long` или `ulong` в `double` может быть потеряна точность, но не величина.</span><span class="sxs-lookup"><span data-stu-id="403fd-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="403fd-128">Не поддерживается неявное преобразование в тип `char`.</span><span class="sxs-lookup"><span data-stu-id="403fd-128">There are no implicit conversions to the `char` type.</span></span>  
  
- <span data-ttu-id="403fd-129">Не поддерживается неявное преобразование между типами `float` и `double` и типом `decimal`.</span><span class="sxs-lookup"><span data-stu-id="403fd-129">There are no implicit conversions between the `float` and `double` types and the `decimal` type.</span></span>  
  
- <span data-ttu-id="403fd-130">Значение константного выражения типа `int` (например, значение, представленное целочисленным литералом) может быть преобразовано в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong`, если оно находится в диапазоне конечного типа.</span><span class="sxs-lookup"><span data-stu-id="403fd-130">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="403fd-131">Дополнительные сведения о неявных преобразованиях см. в разделе [Неявные преобразования](~/_csharplang/spec/conversions.md#implicit-conversions) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="403fd-131">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="403fd-132">См. также</span><span class="sxs-lookup"><span data-stu-id="403fd-132">See also</span></span>

- [<span data-ttu-id="403fd-133">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="403fd-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="403fd-134">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="403fd-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="403fd-135">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="403fd-135">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="403fd-136">Таблица типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="403fd-136">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="403fd-137">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="403fd-137">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="403fd-138">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="403fd-138">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="403fd-139">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="403fd-139">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
