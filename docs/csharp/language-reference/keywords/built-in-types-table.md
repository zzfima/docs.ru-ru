---
title: Справочник по C#. Таблица встроенных типов
ms.custom: seodec18
description: Ключевые слова для встроенных типов C#
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 687990cc86b3303bdef96af26be63af47410f8c0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698797"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="514cc-103">Таблица встроенных типов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="514cc-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="514cc-104">В следующей таблице показаны ключевые слова для встроенных типов C#, которые являются псевдонимами предопределенных типов в пространстве имен <xref:System>:</span><span class="sxs-lookup"><span data-stu-id="514cc-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace:</span></span>

|<span data-ttu-id="514cc-105">Тип C#</span><span class="sxs-lookup"><span data-stu-id="514cc-105">C# type</span></span>|<span data-ttu-id="514cc-106">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="514cc-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="514cc-107">bool</span><span class="sxs-lookup"><span data-stu-id="514cc-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-108">byte</span><span class="sxs-lookup"><span data-stu-id="514cc-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="514cc-109">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-110">char</span><span class="sxs-lookup"><span data-stu-id="514cc-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-111">decimal</span><span class="sxs-lookup"><span data-stu-id="514cc-111">decimal</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-112">double</span><span class="sxs-lookup"><span data-stu-id="514cc-112">double</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-113">float</span><span class="sxs-lookup"><span data-stu-id="514cc-113">float</span></span>](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-114">int</span><span class="sxs-lookup"><span data-stu-id="514cc-114">int</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-115">uint</span><span class="sxs-lookup"><span data-stu-id="514cc-115">uint</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-116">long</span><span class="sxs-lookup"><span data-stu-id="514cc-116">long</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-117">ulong</span><span class="sxs-lookup"><span data-stu-id="514cc-117">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-118">object</span><span class="sxs-lookup"><span data-stu-id="514cc-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-119">short</span><span class="sxs-lookup"><span data-stu-id="514cc-119">short</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-120">ushort</span><span class="sxs-lookup"><span data-stu-id="514cc-120">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="514cc-121">string</span><span class="sxs-lookup"><span data-stu-id="514cc-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="514cc-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="514cc-122">Remarks</span></span>

<span data-ttu-id="514cc-123">Все типы в таблице, за исключением `object` и `string`, считаются простыми.</span><span class="sxs-lookup"><span data-stu-id="514cc-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>

<span data-ttu-id="514cc-124">Типы .NET и псевдонимы ключевых слов типов C# являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="514cc-124">The .NET types and their C# type keyword aliases are interchangeable.</span></span> <span data-ttu-id="514cc-125">Например, можно объявить целочисленную переменную с помощью любого из следующих объявлений:</span><span class="sxs-lookup"><span data-stu-id="514cc-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="514cc-126">Используйте оператор [typeof](../operators/type-testing-and-cast.md#typeof-operator), чтобы получить экземпляр <xref:System.Type?displayProperty=nameWithType>, представляющий указанный тип:</span><span class="sxs-lookup"><span data-stu-id="514cc-126">Use the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="514cc-127">См. также</span><span class="sxs-lookup"><span data-stu-id="514cc-127">See also</span></span>

- [<span data-ttu-id="514cc-128">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="514cc-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="514cc-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="514cc-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="514cc-130">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="514cc-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="514cc-131">Типы значений</span><span class="sxs-lookup"><span data-stu-id="514cc-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="514cc-132">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="514cc-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="514cc-133">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="514cc-133">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="514cc-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="514cc-134">dynamic</span></span>](dynamic.md)
