---
title: "Таблица значений по умолчанию (справочник по C#)"
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034c1daf495c50e299fec4c5bf399652dad08ce
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2017
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="9c473-102">Таблица значений по умолчанию (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9c473-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="9c473-103">В следующей таблице показаны значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9c473-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="9c473-104">Конструкторы по умолчанию вызываются с помощью оператора `new`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9c473-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="9c473-105">Приведенная выше инструкция приводит к тому же результату, что и следующая:</span><span class="sxs-lookup"><span data-stu-id="9c473-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="9c473-106">Обратите внимание, что в C# не допускается использование неинициализированных переменных.</span><span class="sxs-lookup"><span data-stu-id="9c473-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="9c473-107">Тип значения</span><span class="sxs-lookup"><span data-stu-id="9c473-107">Value type</span></span>|<span data-ttu-id="9c473-108">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9c473-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="9c473-109">bool</span><span class="sxs-lookup"><span data-stu-id="9c473-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="9c473-110">byte</span><span class="sxs-lookup"><span data-stu-id="9c473-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="9c473-111">0</span><span class="sxs-lookup"><span data-stu-id="9c473-111">0</span></span>|
|[<span data-ttu-id="9c473-112">char</span><span class="sxs-lookup"><span data-stu-id="9c473-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="9c473-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="9c473-113">'\0'</span></span>|
|[<span data-ttu-id="9c473-114">decimal</span><span class="sxs-lookup"><span data-stu-id="9c473-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="9c473-115">0M</span><span class="sxs-lookup"><span data-stu-id="9c473-115">0M</span></span>|
|[<span data-ttu-id="9c473-116">double</span><span class="sxs-lookup"><span data-stu-id="9c473-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="9c473-117">0,0D</span><span class="sxs-lookup"><span data-stu-id="9c473-117">0.0D</span></span>|
|[<span data-ttu-id="9c473-118">enum</span><span class="sxs-lookup"><span data-stu-id="9c473-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="9c473-119">Значение, создаваемое выражением (E)0, где E — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="9c473-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="9c473-120">float</span><span class="sxs-lookup"><span data-stu-id="9c473-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="9c473-121">0,0F</span><span class="sxs-lookup"><span data-stu-id="9c473-121">0.0F</span></span>|
|[<span data-ttu-id="9c473-122">int</span><span class="sxs-lookup"><span data-stu-id="9c473-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="9c473-123">0</span><span class="sxs-lookup"><span data-stu-id="9c473-123">0</span></span>|
|[<span data-ttu-id="9c473-124">long</span><span class="sxs-lookup"><span data-stu-id="9c473-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="9c473-125">0L</span><span class="sxs-lookup"><span data-stu-id="9c473-125">0L</span></span>|
|[<span data-ttu-id="9c473-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="9c473-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="9c473-127">0</span><span class="sxs-lookup"><span data-stu-id="9c473-127">0</span></span>|
|[<span data-ttu-id="9c473-128">short</span><span class="sxs-lookup"><span data-stu-id="9c473-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="9c473-129">0</span><span class="sxs-lookup"><span data-stu-id="9c473-129">0</span></span>|
|[<span data-ttu-id="9c473-130">struct</span><span class="sxs-lookup"><span data-stu-id="9c473-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="9c473-131">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="9c473-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="9c473-132">uint</span><span class="sxs-lookup"><span data-stu-id="9c473-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="9c473-133">0</span><span class="sxs-lookup"><span data-stu-id="9c473-133">0</span></span>|
|[<span data-ttu-id="9c473-134">ulong</span><span class="sxs-lookup"><span data-stu-id="9c473-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="9c473-135">0</span><span class="sxs-lookup"><span data-stu-id="9c473-135">0</span></span>|
|[<span data-ttu-id="9c473-136">ushort</span><span class="sxs-lookup"><span data-stu-id="9c473-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="9c473-137">0</span><span class="sxs-lookup"><span data-stu-id="9c473-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="9c473-138">См. также</span><span class="sxs-lookup"><span data-stu-id="9c473-138">See also</span></span>
 [<span data-ttu-id="9c473-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9c473-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9c473-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9c473-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9c473-141">Таблица типов значений</span><span class="sxs-lookup"><span data-stu-id="9c473-141">Value Types Table</span></span>](../../../csharp/language-reference/keywords/value-types-table.md)  
 [<span data-ttu-id="9c473-142">Типы значений</span><span class="sxs-lookup"><span data-stu-id="9c473-142">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="9c473-143">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="9c473-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="9c473-144">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="9c473-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
