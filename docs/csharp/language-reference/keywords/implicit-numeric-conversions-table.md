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
ms.openlocfilehash: 516505ccacfd2a8a5c275b0de033e1316fa06d3a
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661347"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="327c3-102">Таблица неявных числовых преобразований (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="327c3-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="327c3-103">В следующей таблице приведены предопределенные неявные преобразования между числовыми типами .NET.</span><span class="sxs-lookup"><span data-stu-id="327c3-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="327c3-104">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="327c3-104">From</span></span>|<span data-ttu-id="327c3-105">Кому</span><span class="sxs-lookup"><span data-stu-id="327c3-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="327c3-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="327c3-106">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-107">`short`, `int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-108">byte</span><span class="sxs-lookup"><span data-stu-id="327c3-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-110">char</span><span class="sxs-lookup"><span data-stu-id="327c3-110">char</span></span>](char.md)|<span data-ttu-id="327c3-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-112">short</span><span class="sxs-lookup"><span data-stu-id="327c3-112">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-113">`int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-113">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-114">ushort</span><span class="sxs-lookup"><span data-stu-id="327c3-114">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-115">`int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-115">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-116">int</span><span class="sxs-lookup"><span data-stu-id="327c3-116">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-117">`long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-117">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-118">uint</span><span class="sxs-lookup"><span data-stu-id="327c3-118">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-119">`long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-119">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-120">long</span><span class="sxs-lookup"><span data-stu-id="327c3-120">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-121">`float`, `double`или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-121">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-122">ulong</span><span class="sxs-lookup"><span data-stu-id="327c3-122">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="327c3-123">`float`, `double`или `decimal`</span><span class="sxs-lookup"><span data-stu-id="327c3-123">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="327c3-124">float</span><span class="sxs-lookup"><span data-stu-id="327c3-124">float</span></span>](../builtin-types/floating-point-numeric-types.md)|`double`|  
  
## <a name="remarks"></a><span data-ttu-id="327c3-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="327c3-125">Remarks</span></span>  

- <span data-ttu-id="327c3-126">Любой [целочисленный тип](../builtin-types/integral-numeric-types.md) неявно преобразуется к любому [типу с плавающей запятой](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="327c3-126">Any [integral type](../builtin-types/integral-numeric-types.md) is implicitly convertible to any [floating-point type](../builtin-types/floating-point-numeric-types.md).</span></span>

- <span data-ttu-id="327c3-127">При преобразовании из `int`, `uint`, `long` или `ulong` в `float` и из `long` или `ulong` в `double` может быть потеряна точность, но не величина.</span><span class="sxs-lookup"><span data-stu-id="327c3-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="327c3-128">Не поддерживается неявное преобразование в типы `char`, `byte` и `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="327c3-128">There are no implicit conversions to the `char`, `byte`, and `sbyte` types.</span></span>  

- <span data-ttu-id="327c3-129">Не поддерживается неявное преобразование из типов `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="327c3-129">There are no implicit conversions from the `double` and `decimal` types.</span></span>
  
- <span data-ttu-id="327c3-130">Не поддерживается неявное преобразование между типом `decimal` и типами `float` или `double`.</span><span class="sxs-lookup"><span data-stu-id="327c3-130">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>  
  
- <span data-ttu-id="327c3-131">Значение константного выражения типа `int` (например, значение, представленное целочисленным литералом) может быть преобразовано в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong`, если оно находится в диапазоне конечного типа.</span><span class="sxs-lookup"><span data-stu-id="327c3-131">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="327c3-132">Дополнительные сведения о неявных преобразованиях см. в разделе [Неявные преобразования](~/_csharplang/spec/conversions.md#implicit-conversions) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="327c3-132">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="327c3-133">См. также</span><span class="sxs-lookup"><span data-stu-id="327c3-133">See also</span></span>

- [<span data-ttu-id="327c3-134">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="327c3-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="327c3-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="327c3-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="327c3-136">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="327c3-136">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="327c3-137">Таблица типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="327c3-137">Floating-point types table</span></span>](../builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="327c3-138">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="327c3-138">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="327c3-139">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="327c3-139">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="327c3-140">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="327c3-140">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
