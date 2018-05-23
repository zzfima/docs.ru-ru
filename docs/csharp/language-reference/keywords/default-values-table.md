---
title: Таблица значений по умолчанию (справочник по C#)
description: Узнайте, что такое значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="810c4-103">Таблица значений по умолчанию (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="810c4-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="810c4-104">В следующей таблице показаны значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="810c4-104">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="810c4-105">Конструкторы по умолчанию вызываются с помощью оператора `new`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="810c4-105">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="810c4-106">Приведенная выше инструкция приводит к тому же результату, что и следующая:</span><span class="sxs-lookup"><span data-stu-id="810c4-106">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="810c4-107">Обратите внимание, что в C# не допускается использование неинициализированных переменных.</span><span class="sxs-lookup"><span data-stu-id="810c4-107">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="810c4-108">Тип значения</span><span class="sxs-lookup"><span data-stu-id="810c4-108">Value type</span></span>|<span data-ttu-id="810c4-109">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="810c4-109">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="810c4-110">bool</span><span class="sxs-lookup"><span data-stu-id="810c4-110">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="810c4-111">byte</span><span class="sxs-lookup"><span data-stu-id="810c4-111">byte</span></span>](byte.md)|<span data-ttu-id="810c4-112">0</span><span class="sxs-lookup"><span data-stu-id="810c4-112">0</span></span>|
|[<span data-ttu-id="810c4-113">char</span><span class="sxs-lookup"><span data-stu-id="810c4-113">char</span></span>](char.md)|<span data-ttu-id="810c4-114">'\0'</span><span class="sxs-lookup"><span data-stu-id="810c4-114">'\0'</span></span>|
|[<span data-ttu-id="810c4-115">decimal</span><span class="sxs-lookup"><span data-stu-id="810c4-115">decimal</span></span>](decimal.md)|<span data-ttu-id="810c4-116">0M</span><span class="sxs-lookup"><span data-stu-id="810c4-116">0M</span></span>|
|[<span data-ttu-id="810c4-117">double</span><span class="sxs-lookup"><span data-stu-id="810c4-117">double</span></span>](double.md)|<span data-ttu-id="810c4-118">0,0D</span><span class="sxs-lookup"><span data-stu-id="810c4-118">0.0D</span></span>|
|[<span data-ttu-id="810c4-119">enum</span><span class="sxs-lookup"><span data-stu-id="810c4-119">enum</span></span>](enum.md)|<span data-ttu-id="810c4-120">Значение, создаваемое выражением (E)0, где E — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="810c4-120">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="810c4-121">float</span><span class="sxs-lookup"><span data-stu-id="810c4-121">float</span></span>](float.md)|<span data-ttu-id="810c4-122">0,0F</span><span class="sxs-lookup"><span data-stu-id="810c4-122">0.0F</span></span>|
|[<span data-ttu-id="810c4-123">int</span><span class="sxs-lookup"><span data-stu-id="810c4-123">int</span></span>](int.md)|<span data-ttu-id="810c4-124">0</span><span class="sxs-lookup"><span data-stu-id="810c4-124">0</span></span>|
|[<span data-ttu-id="810c4-125">long</span><span class="sxs-lookup"><span data-stu-id="810c4-125">long</span></span>](long.md)|<span data-ttu-id="810c4-126">0L</span><span class="sxs-lookup"><span data-stu-id="810c4-126">0L</span></span>|
|[<span data-ttu-id="810c4-127">sbyte</span><span class="sxs-lookup"><span data-stu-id="810c4-127">sbyte</span></span>](sbyte.md)|<span data-ttu-id="810c4-128">0</span><span class="sxs-lookup"><span data-stu-id="810c4-128">0</span></span>|
|[<span data-ttu-id="810c4-129">short</span><span class="sxs-lookup"><span data-stu-id="810c4-129">short</span></span>](short.md)|<span data-ttu-id="810c4-130">0</span><span class="sxs-lookup"><span data-stu-id="810c4-130">0</span></span>|
|[<span data-ttu-id="810c4-131">struct</span><span class="sxs-lookup"><span data-stu-id="810c4-131">struct</span></span>](struct.md)|<span data-ttu-id="810c4-132">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="810c4-132">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="810c4-133">uint</span><span class="sxs-lookup"><span data-stu-id="810c4-133">uint</span></span>](uint.md)|<span data-ttu-id="810c4-134">0</span><span class="sxs-lookup"><span data-stu-id="810c4-134">0</span></span>|
|[<span data-ttu-id="810c4-135">ulong</span><span class="sxs-lookup"><span data-stu-id="810c4-135">ulong</span></span>](ulong.md)|<span data-ttu-id="810c4-136">0</span><span class="sxs-lookup"><span data-stu-id="810c4-136">0</span></span>|
|[<span data-ttu-id="810c4-137">ushort</span><span class="sxs-lookup"><span data-stu-id="810c4-137">ushort</span></span>](ushort.md)|<span data-ttu-id="810c4-138">0</span><span class="sxs-lookup"><span data-stu-id="810c4-138">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="810c4-139">См. также</span><span class="sxs-lookup"><span data-stu-id="810c4-139">See also</span></span>
 [<span data-ttu-id="810c4-140">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="810c4-140">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="810c4-141">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="810c4-141">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="810c4-142">Таблица типов значений</span><span class="sxs-lookup"><span data-stu-id="810c4-142">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="810c4-143">Типы значений</span><span class="sxs-lookup"><span data-stu-id="810c4-143">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="810c4-144">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="810c4-144">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="810c4-145">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="810c4-145">Reference Tables for Types</span></span>](reference-tables-for-types.md)
