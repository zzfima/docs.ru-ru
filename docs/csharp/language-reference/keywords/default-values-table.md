---
title: Таблица значений по умолчанию (справочник по C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
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
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="bbae0-102">Таблица значений по умолчанию (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bbae0-102">Default values table (C# Reference)</span></span>

<span data-ttu-id="bbae0-103">В следующей таблице показаны значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbae0-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="bbae0-104">Конструкторы по умолчанию вызываются с помощью оператора `new`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="bbae0-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="bbae0-105">Приведенная выше инструкция приводит к тому же результату, что и следующая:</span><span class="sxs-lookup"><span data-stu-id="bbae0-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="bbae0-106">Обратите внимание, что в C# не допускается использование неинициализированных переменных.</span><span class="sxs-lookup"><span data-stu-id="bbae0-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="bbae0-107">Тип значения</span><span class="sxs-lookup"><span data-stu-id="bbae0-107">Value type</span></span>|<span data-ttu-id="bbae0-108">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bbae0-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="bbae0-109">bool</span><span class="sxs-lookup"><span data-stu-id="bbae0-109">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="bbae0-110">byte</span><span class="sxs-lookup"><span data-stu-id="bbae0-110">byte</span></span>](byte.md)|<span data-ttu-id="bbae0-111">0</span><span class="sxs-lookup"><span data-stu-id="bbae0-111">0</span></span>|
|[<span data-ttu-id="bbae0-112">char</span><span class="sxs-lookup"><span data-stu-id="bbae0-112">char</span></span>](char.md)|<span data-ttu-id="bbae0-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="bbae0-113">'\0'</span></span>|
|[<span data-ttu-id="bbae0-114">decimal</span><span class="sxs-lookup"><span data-stu-id="bbae0-114">decimal</span></span>](decimal.md)|<span data-ttu-id="bbae0-115">0M</span><span class="sxs-lookup"><span data-stu-id="bbae0-115">0M</span></span>|
|[<span data-ttu-id="bbae0-116">double</span><span class="sxs-lookup"><span data-stu-id="bbae0-116">double</span></span>](double.md)|<span data-ttu-id="bbae0-117">0,0D</span><span class="sxs-lookup"><span data-stu-id="bbae0-117">0.0D</span></span>|
|[<span data-ttu-id="bbae0-118">enum</span><span class="sxs-lookup"><span data-stu-id="bbae0-118">enum</span></span>](enum.md)|<span data-ttu-id="bbae0-119">Значение, создаваемое выражением (E)0, где E — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="bbae0-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="bbae0-120">float</span><span class="sxs-lookup"><span data-stu-id="bbae0-120">float</span></span>](float.md)|<span data-ttu-id="bbae0-121">0,0F</span><span class="sxs-lookup"><span data-stu-id="bbae0-121">0.0F</span></span>|
|[<span data-ttu-id="bbae0-122">int</span><span class="sxs-lookup"><span data-stu-id="bbae0-122">int</span></span>](int.md)|<span data-ttu-id="bbae0-123">0</span><span class="sxs-lookup"><span data-stu-id="bbae0-123">0</span></span>|
|[<span data-ttu-id="bbae0-124">long</span><span class="sxs-lookup"><span data-stu-id="bbae0-124">long</span></span>](long.md)|<span data-ttu-id="bbae0-125">0L</span><span class="sxs-lookup"><span data-stu-id="bbae0-125">0L</span></span>|
|[<span data-ttu-id="bbae0-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="bbae0-126">sbyte</span></span>](sbyte.md)|<span data-ttu-id="bbae0-127">0</span><span class="sxs-lookup"><span data-stu-id="bbae0-127">0</span></span>|
|[<span data-ttu-id="bbae0-128">short</span><span class="sxs-lookup"><span data-stu-id="bbae0-128">short</span></span>](short.md)|<span data-ttu-id="bbae0-129">0</span><span class="sxs-lookup"><span data-stu-id="bbae0-129">0</span></span>|
|[<span data-ttu-id="bbae0-130">struct</span><span class="sxs-lookup"><span data-stu-id="bbae0-130">struct</span></span>](struct.md)|<span data-ttu-id="bbae0-131">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="bbae0-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="bbae0-132">uint</span><span class="sxs-lookup"><span data-stu-id="bbae0-132">uint</span></span>](uint.md)|<span data-ttu-id="bbae0-133">0</span><span class="sxs-lookup"><span data-stu-id="bbae0-133">0</span></span>|
|[<span data-ttu-id="bbae0-134">ulong</span><span class="sxs-lookup"><span data-stu-id="bbae0-134">ulong</span></span>](ulong.md)|<span data-ttu-id="bbae0-135">0</span><span class="sxs-lookup"><span data-stu-id="bbae0-135">0</span></span>|
|[<span data-ttu-id="bbae0-136">ushort</span><span class="sxs-lookup"><span data-stu-id="bbae0-136">ushort</span></span>](ushort.md)|<span data-ttu-id="bbae0-137">0</span><span class="sxs-lookup"><span data-stu-id="bbae0-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="bbae0-138">См. также</span><span class="sxs-lookup"><span data-stu-id="bbae0-138">See also</span></span>
 [<span data-ttu-id="bbae0-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bbae0-139">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="bbae0-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bbae0-140">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="bbae0-141">Таблица типов значений</span><span class="sxs-lookup"><span data-stu-id="bbae0-141">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="bbae0-142">Типы значений</span><span class="sxs-lookup"><span data-stu-id="bbae0-142">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="bbae0-143">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="bbae0-143">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="bbae0-144">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="bbae0-144">Reference Tables for Types</span></span>](reference-tables-for-types.md)
