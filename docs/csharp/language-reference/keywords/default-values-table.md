---
title: "Таблица значений по умолчанию (справочник по C#)"
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
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
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: f8cf12317f1f0163028db003ff31604480da5d1c
ms.openlocfilehash: 975d416259778e0741347829d8a9c79aaa6cfc8c
ms.contentlocale: ru-ru
ms.lasthandoff: 08/12/2017

---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="02776-102">Таблица значений по умолчанию (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="02776-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="02776-103">В следующей таблице показаны значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="02776-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="02776-104">Конструкторы по умолчанию вызываются с помощью оператора `new`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="02776-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="02776-105">Приведенная выше инструкция приводит к тому же результату, что и следующая:</span><span class="sxs-lookup"><span data-stu-id="02776-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="02776-106">Обратите внимание, что в C# не допускается использование неинициализированных переменных.</span><span class="sxs-lookup"><span data-stu-id="02776-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="02776-107">Тип значения</span><span class="sxs-lookup"><span data-stu-id="02776-107">Value type</span></span>|<span data-ttu-id="02776-108">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="02776-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="02776-109">bool</span><span class="sxs-lookup"><span data-stu-id="02776-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="02776-110">byte</span><span class="sxs-lookup"><span data-stu-id="02776-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="02776-111">0</span><span class="sxs-lookup"><span data-stu-id="02776-111">0</span></span>|
|[<span data-ttu-id="02776-112">char</span><span class="sxs-lookup"><span data-stu-id="02776-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="02776-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="02776-113">'\0'</span></span>|
|[<span data-ttu-id="02776-114">decimal</span><span class="sxs-lookup"><span data-stu-id="02776-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="02776-115">0,0M</span><span class="sxs-lookup"><span data-stu-id="02776-115">0.0M</span></span>|
|[<span data-ttu-id="02776-116">double</span><span class="sxs-lookup"><span data-stu-id="02776-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="02776-117">0,0D</span><span class="sxs-lookup"><span data-stu-id="02776-117">0.0D</span></span>|
|[<span data-ttu-id="02776-118">enum</span><span class="sxs-lookup"><span data-stu-id="02776-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="02776-119">Значение, создаваемое выражением (E)0, где E — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="02776-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="02776-120">float</span><span class="sxs-lookup"><span data-stu-id="02776-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="02776-121">0,0F</span><span class="sxs-lookup"><span data-stu-id="02776-121">0.0F</span></span>|
|[<span data-ttu-id="02776-122">int</span><span class="sxs-lookup"><span data-stu-id="02776-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="02776-123">0</span><span class="sxs-lookup"><span data-stu-id="02776-123">0</span></span>|
|[<span data-ttu-id="02776-124">long</span><span class="sxs-lookup"><span data-stu-id="02776-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="02776-125">0L</span><span class="sxs-lookup"><span data-stu-id="02776-125">0L</span></span>|
|[<span data-ttu-id="02776-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="02776-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="02776-127">0</span><span class="sxs-lookup"><span data-stu-id="02776-127">0</span></span>|
|[<span data-ttu-id="02776-128">short</span><span class="sxs-lookup"><span data-stu-id="02776-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="02776-129">0</span><span class="sxs-lookup"><span data-stu-id="02776-129">0</span></span>|
|[<span data-ttu-id="02776-130">struct</span><span class="sxs-lookup"><span data-stu-id="02776-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="02776-131">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="02776-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="02776-132">uint</span><span class="sxs-lookup"><span data-stu-id="02776-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="02776-133">0</span><span class="sxs-lookup"><span data-stu-id="02776-133">0</span></span>|
|[<span data-ttu-id="02776-134">ulong</span><span class="sxs-lookup"><span data-stu-id="02776-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="02776-135">0</span><span class="sxs-lookup"><span data-stu-id="02776-135">0</span></span>|
|[<span data-ttu-id="02776-136">ushort</span><span class="sxs-lookup"><span data-stu-id="02776-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="02776-137">0</span><span class="sxs-lookup"><span data-stu-id="02776-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="02776-138">См. также</span><span class="sxs-lookup"><span data-stu-id="02776-138">See also</span></span>
 <span data-ttu-id="02776-139">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="02776-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="02776-140">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="02776-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="02776-141">[Таблица типов значений](../../../csharp/language-reference/keywords/value-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="02776-141">[Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md) </span></span>  
 <span data-ttu-id="02776-142">[Типы значений](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="02776-142">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="02776-143">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="02776-143">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="02776-144">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="02776-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

