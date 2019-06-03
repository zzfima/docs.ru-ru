---
title: Справочник по C#. Таблица целочисленных типов
ms.custom: seodec18
description: Общие сведения о встроенных целочисленных типах в C#
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: b4a3a46ba98c0c621b747284ce39e03d68a5b62d
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421732"
---
# <a name="integral-types-table-c-reference"></a><span data-ttu-id="85cc7-103">Таблица целочисленных типов (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="85cc7-103">Integral types table (C# Reference)</span></span>

<span data-ttu-id="85cc7-104">В следующей таблице приводятся сведения о размерах и диапазонах для целочисленных типов, которые составляют подмножество простых типов.</span><span class="sxs-lookup"><span data-stu-id="85cc7-104">The following table shows the sizes and ranges of the integral types, which constitute a subset of simple types.</span></span>  
  
|<span data-ttu-id="85cc7-105">Тип</span><span class="sxs-lookup"><span data-stu-id="85cc7-105">Type</span></span>|<span data-ttu-id="85cc7-106">Диапазон</span><span class="sxs-lookup"><span data-stu-id="85cc7-106">Range</span></span>|<span data-ttu-id="85cc7-107">Размер</span><span class="sxs-lookup"><span data-stu-id="85cc7-107">Size</span></span>|  
|----------|-----------|----------|  
|[<span data-ttu-id="85cc7-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="85cc7-108">sbyte</span></span>](sbyte.md)|<span data-ttu-id="85cc7-109">От -128 до 127</span><span class="sxs-lookup"><span data-stu-id="85cc7-109">-128 to 127</span></span>|<span data-ttu-id="85cc7-110">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="85cc7-110">Signed 8-bit integer</span></span>|  
|[<span data-ttu-id="85cc7-111">byte</span><span class="sxs-lookup"><span data-stu-id="85cc7-111">byte</span></span>](byte.md)|<span data-ttu-id="85cc7-112">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="85cc7-112">0 to 255</span></span>|<span data-ttu-id="85cc7-113">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="85cc7-113">Unsigned 8-bit integer</span></span>|  
|[<span data-ttu-id="85cc7-114">char</span><span class="sxs-lookup"><span data-stu-id="85cc7-114">char</span></span>](char.md)|<span data-ttu-id="85cc7-115">От U+0000 до U+ffff</span><span class="sxs-lookup"><span data-stu-id="85cc7-115">U+0000 to U+ffff</span></span>|<span data-ttu-id="85cc7-116">Символ Юникода (16-разрядный)</span><span class="sxs-lookup"><span data-stu-id="85cc7-116">Unicode 16-bit character</span></span>|  
|[<span data-ttu-id="85cc7-117">short</span><span class="sxs-lookup"><span data-stu-id="85cc7-117">short</span></span>](short.md)|<span data-ttu-id="85cc7-118">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="85cc7-118">-32,768 to 32,767</span></span>|<span data-ttu-id="85cc7-119">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="85cc7-119">Signed 16-bit integer</span></span>|  
|[<span data-ttu-id="85cc7-120">ushort</span><span class="sxs-lookup"><span data-stu-id="85cc7-120">ushort</span></span>](ushort.md)|<span data-ttu-id="85cc7-121">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="85cc7-121">0 to 65,535</span></span>|<span data-ttu-id="85cc7-122">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="85cc7-122">Unsigned 16-bit integer</span></span>|  
|[<span data-ttu-id="85cc7-123">int</span><span class="sxs-lookup"><span data-stu-id="85cc7-123">int</span></span>](int.md)|<span data-ttu-id="85cc7-124">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="85cc7-124">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="85cc7-125">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="85cc7-125">Signed 32-bit integer</span></span>|  
|[<span data-ttu-id="85cc7-126">uint</span><span class="sxs-lookup"><span data-stu-id="85cc7-126">uint</span></span>](uint.md)|<span data-ttu-id="85cc7-127">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="85cc7-127">0 to 4,294,967,295</span></span>|<span data-ttu-id="85cc7-128">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="85cc7-128">Unsigned 32-bit integer</span></span>|  
|[<span data-ttu-id="85cc7-129">long</span><span class="sxs-lookup"><span data-stu-id="85cc7-129">long</span></span>](long.md)|<span data-ttu-id="85cc7-130">От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807</span><span class="sxs-lookup"><span data-stu-id="85cc7-130">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="85cc7-131">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="85cc7-131">Signed 64-bit integer</span></span>|  
|[<span data-ttu-id="85cc7-132">ulong</span><span class="sxs-lookup"><span data-stu-id="85cc7-132">ulong</span></span>](ulong.md)|<span data-ttu-id="85cc7-133">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="85cc7-133">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="85cc7-134">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="85cc7-134">Unsigned 64-bit integer</span></span>|  

## <a name="remarks"></a><span data-ttu-id="85cc7-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="85cc7-135">Remarks</span></span>
  
<span data-ttu-id="85cc7-136">Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="85cc7-136">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="85cc7-137">Используйте структуру <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить произвольно большое целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="85cc7-137">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent an arbitrarily large signed integer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85cc7-138">См. также</span><span class="sxs-lookup"><span data-stu-id="85cc7-138">See also</span></span>

- [<span data-ttu-id="85cc7-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="85cc7-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="85cc7-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="85cc7-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="85cc7-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="85cc7-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="85cc7-142">Таблица типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="85cc7-142">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="85cc7-143">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="85cc7-143">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="85cc7-144">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="85cc7-144">Formatting numeric results table</span></span>](formatting-numeric-results-table.md)
- [<span data-ttu-id="85cc7-145">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="85cc7-145">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="85cc7-146">Числовые значения в .NET</span><span class="sxs-lookup"><span data-stu-id="85cc7-146">Numerics in .NET</span></span>](../../../standard/numerics.md)
