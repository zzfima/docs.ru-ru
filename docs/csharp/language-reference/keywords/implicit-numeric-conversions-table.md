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
ms.openlocfilehash: 703f60f48e1e569e0ffcab66ff7ccc91d4a49514
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093558"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="0cd1f-102">Таблица неявных числовых преобразований (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0cd1f-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="0cd1f-103">В следующей таблице приведены предопределенные неявные преобразования между числовыми типами .NET.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="0cd1f-104">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="0cd1f-104">From</span></span>|<span data-ttu-id="0cd1f-105">Кому</span><span class="sxs-lookup"><span data-stu-id="0cd1f-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="0cd1f-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="0cd1f-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="0cd1f-107">`short`, `int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-108">byte</span><span class="sxs-lookup"><span data-stu-id="0cd1f-108">byte</span></span>](byte.md)|<span data-ttu-id="0cd1f-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-110">char</span><span class="sxs-lookup"><span data-stu-id="0cd1f-110">char</span></span>](char.md)|<span data-ttu-id="0cd1f-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-112">short</span><span class="sxs-lookup"><span data-stu-id="0cd1f-112">short</span></span>](short.md)|<span data-ttu-id="0cd1f-113">`int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-113">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-114">ushort</span><span class="sxs-lookup"><span data-stu-id="0cd1f-114">ushort</span></span>](ushort.md)|<span data-ttu-id="0cd1f-115">`int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-115">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-116">int</span><span class="sxs-lookup"><span data-stu-id="0cd1f-116">int</span></span>](int.md)|<span data-ttu-id="0cd1f-117">`long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-117">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-118">uint</span><span class="sxs-lookup"><span data-stu-id="0cd1f-118">uint</span></span>](uint.md)|<span data-ttu-id="0cd1f-119">`long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-119">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-120">long</span><span class="sxs-lookup"><span data-stu-id="0cd1f-120">long</span></span>](long.md)|<span data-ttu-id="0cd1f-121">`float`, `double`или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-121">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-122">ulong</span><span class="sxs-lookup"><span data-stu-id="0cd1f-122">ulong</span></span>](ulong.md)|<span data-ttu-id="0cd1f-123">`float`, `double`или `decimal`</span><span class="sxs-lookup"><span data-stu-id="0cd1f-123">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0cd1f-124">float</span><span class="sxs-lookup"><span data-stu-id="0cd1f-124">float</span></span>](float.md)|`double`|  
  
## <a name="remarks"></a><span data-ttu-id="0cd1f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="0cd1f-125">Remarks</span></span>  

- <span data-ttu-id="0cd1f-126">Любой [целочисленный тип](integral-types-table.md) неявно преобразуется к любому [типу с плавающей запятой](floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="0cd1f-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="0cd1f-127">При преобразовании из `int`, `uint`, `long` или `ulong` в `float` и из `long` или `ulong` в `double` может быть потеряна точность, но не величина.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="0cd1f-128">Не поддерживается неявное преобразование в типы `char`, `byte` и `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-128">There are no implicit conversions to the `char`, `byte`, and `sbyte` types.</span></span>  

- <span data-ttu-id="0cd1f-129">Не поддерживается неявное преобразование из типов `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-129">There are no implicit conversions from the `double` and `decimal` types.</span></span>
  
- <span data-ttu-id="0cd1f-130">Не поддерживается неявное преобразование между типом `decimal` и типами `float` или `double`.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-130">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>  
  
- <span data-ttu-id="0cd1f-131">Значение константного выражения типа `int` (например, значение, представленное целочисленным литералом) может быть преобразовано в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong`, если оно находится в диапазоне конечного типа.</span><span class="sxs-lookup"><span data-stu-id="0cd1f-131">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="0cd1f-132">Дополнительные сведения о неявных преобразованиях см. в разделе [Неявные преобразования](~/_csharplang/spec/conversions.md#implicit-conversions) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0cd1f-132">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0cd1f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0cd1f-133">See also</span></span>

- [<span data-ttu-id="0cd1f-134">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0cd1f-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0cd1f-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0cd1f-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0cd1f-136">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="0cd1f-136">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="0cd1f-137">Таблица типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="0cd1f-137">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="0cd1f-138">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="0cd1f-138">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="0cd1f-139">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="0cd1f-139">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="0cd1f-140">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="0cd1f-140">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
