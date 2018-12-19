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
ms.openlocfilehash: 1815f057e5cf26d64e5ff151f161cc56214efc1b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237991"
---
# <a name="integral-types-table-c-reference"></a><span data-ttu-id="f6d74-103">Таблица целочисленных типов (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f6d74-103">Integral types table (C# Reference)</span></span>

<span data-ttu-id="f6d74-104">В следующей таблице приводятся сведения о размерах и диапазонах для целочисленных типов, которые составляют подмножество простых типов.</span><span class="sxs-lookup"><span data-stu-id="f6d74-104">The following table shows the sizes and ranges of the integral types, which constitute a subset of simple types.</span></span>  
  
|<span data-ttu-id="f6d74-105">Тип</span><span class="sxs-lookup"><span data-stu-id="f6d74-105">Type</span></span>|<span data-ttu-id="f6d74-106">Диапазон</span><span class="sxs-lookup"><span data-stu-id="f6d74-106">Range</span></span>|<span data-ttu-id="f6d74-107">Размер</span><span class="sxs-lookup"><span data-stu-id="f6d74-107">Size</span></span>|  
|----------|-----------|----------|  
|[<span data-ttu-id="f6d74-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="f6d74-108">sbyte</span></span>](sbyte.md)|<span data-ttu-id="f6d74-109">От -128 до 127</span><span class="sxs-lookup"><span data-stu-id="f6d74-109">-128 to 127</span></span>|<span data-ttu-id="f6d74-110">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="f6d74-110">Signed 8-bit integer</span></span>|  
|[<span data-ttu-id="f6d74-111">byte</span><span class="sxs-lookup"><span data-stu-id="f6d74-111">byte</span></span>](byte.md)|<span data-ttu-id="f6d74-112">От 0 до 255</span><span class="sxs-lookup"><span data-stu-id="f6d74-112">0 to 255</span></span>|<span data-ttu-id="f6d74-113">8-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="f6d74-113">Unsigned 8-bit integer</span></span>|  
|[<span data-ttu-id="f6d74-114">char</span><span class="sxs-lookup"><span data-stu-id="f6d74-114">char</span></span>](char.md)|<span data-ttu-id="f6d74-115">От U+0000 до U+ffff</span><span class="sxs-lookup"><span data-stu-id="f6d74-115">U+0000 to U+ffff</span></span>|<span data-ttu-id="f6d74-116">Символ Юникода (16-разрядный)</span><span class="sxs-lookup"><span data-stu-id="f6d74-116">Unicode 16-bit character</span></span>|  
|[<span data-ttu-id="f6d74-117">short</span><span class="sxs-lookup"><span data-stu-id="f6d74-117">short</span></span>](short.md)|<span data-ttu-id="f6d74-118">От -32 768 до 32 767</span><span class="sxs-lookup"><span data-stu-id="f6d74-118">-32,768 to 32,767</span></span>|<span data-ttu-id="f6d74-119">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="f6d74-119">Signed 16-bit integer</span></span>|  
|[<span data-ttu-id="f6d74-120">ushort</span><span class="sxs-lookup"><span data-stu-id="f6d74-120">ushort</span></span>](ushort.md)|<span data-ttu-id="f6d74-121">От 0 до 65 535</span><span class="sxs-lookup"><span data-stu-id="f6d74-121">0 to 65,535</span></span>|<span data-ttu-id="f6d74-122">16-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="f6d74-122">Unsigned 16-bit integer</span></span>|  
|[<span data-ttu-id="f6d74-123">int</span><span class="sxs-lookup"><span data-stu-id="f6d74-123">int</span></span>](int.md)|<span data-ttu-id="f6d74-124">От -2 147 483 648 до 2 147 483 647</span><span class="sxs-lookup"><span data-stu-id="f6d74-124">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="f6d74-125">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="f6d74-125">Signed 32-bit integer</span></span>|  
|[<span data-ttu-id="f6d74-126">uint</span><span class="sxs-lookup"><span data-stu-id="f6d74-126">uint</span></span>](uint.md)|<span data-ttu-id="f6d74-127">От 0 до 4 294 967 295</span><span class="sxs-lookup"><span data-stu-id="f6d74-127">0 to 4,294,967,295</span></span>|<span data-ttu-id="f6d74-128">32-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="f6d74-128">Unsigned 32-bit integer</span></span>|  
|[<span data-ttu-id="f6d74-129">long</span><span class="sxs-lookup"><span data-stu-id="f6d74-129">long</span></span>](long.md)|<span data-ttu-id="f6d74-130">От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807</span><span class="sxs-lookup"><span data-stu-id="f6d74-130">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="f6d74-131">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="f6d74-131">Signed 64-bit integer</span></span>|  
|[<span data-ttu-id="f6d74-132">ulong</span><span class="sxs-lookup"><span data-stu-id="f6d74-132">ulong</span></span>](ulong.md)|<span data-ttu-id="f6d74-133">От 0 до 18 446 744 073 709 551 615</span><span class="sxs-lookup"><span data-stu-id="f6d74-133">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="f6d74-134">64-разрядное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="f6d74-134">Unsigned 64-bit integer</span></span>|  

## <a name="remarks"></a><span data-ttu-id="f6d74-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6d74-135">Remarks</span></span>
  
<span data-ttu-id="f6d74-136">Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).</span><span class="sxs-lookup"><span data-stu-id="f6d74-136">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="f6d74-137">Используйте класс <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить произвольно большое целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="f6d74-137">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> class to represent an arbitrarily large signed integer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6d74-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f6d74-138">See also</span></span>

- [<span data-ttu-id="f6d74-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f6d74-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f6d74-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f6d74-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f6d74-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f6d74-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f6d74-142">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="f6d74-142">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="f6d74-143">Таблица типов с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f6d74-143">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="f6d74-144">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f6d74-144">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="f6d74-145">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="f6d74-145">Formatting numeric results table</span></span>](formatting-numeric-results-table.md)
- [<span data-ttu-id="f6d74-146">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="f6d74-146">Built-in types table</span></span>](built-in-types-table.md)
