---
title: Таблица встроенных типов (Справочник по C#)
description: Ключевые слова для встроенных типов C#
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: fd9ba878d77bdb219542db55bb38023c60c7bec4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507316"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="6e575-103">Таблица встроенных типов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6e575-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="6e575-104">В следующей таблице показаны ключевые слова для встроенных типов C#, которые являются псевдонимами предопределенных типов в пространстве имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="6e575-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="6e575-105">Тип C#</span><span class="sxs-lookup"><span data-stu-id="6e575-105">C# type</span></span>|<span data-ttu-id="6e575-106">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="6e575-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="6e575-107">bool</span><span class="sxs-lookup"><span data-stu-id="6e575-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-108">byte</span><span class="sxs-lookup"><span data-stu-id="6e575-108">byte</span></span>](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="6e575-109">sbyte</span></span>](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-110">char</span><span class="sxs-lookup"><span data-stu-id="6e575-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-111">decimal</span><span class="sxs-lookup"><span data-stu-id="6e575-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-112">double</span><span class="sxs-lookup"><span data-stu-id="6e575-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-113">float</span><span class="sxs-lookup"><span data-stu-id="6e575-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-114">int</span><span class="sxs-lookup"><span data-stu-id="6e575-114">int</span></span>](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-115">uint</span><span class="sxs-lookup"><span data-stu-id="6e575-115">uint</span></span>](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-116">long</span><span class="sxs-lookup"><span data-stu-id="6e575-116">long</span></span>](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-117">ulong</span><span class="sxs-lookup"><span data-stu-id="6e575-117">ulong</span></span>](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-118">object</span><span class="sxs-lookup"><span data-stu-id="6e575-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-119">short</span><span class="sxs-lookup"><span data-stu-id="6e575-119">short</span></span>](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-120">ushort</span><span class="sxs-lookup"><span data-stu-id="6e575-120">ushort</span></span>](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="6e575-121">string</span><span class="sxs-lookup"><span data-stu-id="6e575-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="6e575-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e575-122">Remarks</span></span>

<span data-ttu-id="6e575-123">Все типы в таблице, за исключением `object` и `string`, считаются простыми.</span><span class="sxs-lookup"><span data-stu-id="6e575-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="6e575-124">Ключевые слова типов C# и их псевдонимы являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="6e575-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="6e575-125">Например, можно объявить целочисленную переменную с помощью любого из следующих объявлений:</span><span class="sxs-lookup"><span data-stu-id="6e575-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="6e575-126">Используйте оператор [typeof](typeof.md), чтобы получить экземпляр <xref:System.Type?displayProperty=nameWithType>, представляющий указанный тип:</span><span class="sxs-lookup"><span data-stu-id="6e575-126">Use the [typeof](typeof.md) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="6e575-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6e575-127">See also</span></span>

- [<span data-ttu-id="6e575-128">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6e575-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="6e575-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6e575-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6e575-130">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6e575-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6e575-131">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="6e575-131">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="6e575-132">Типы значений</span><span class="sxs-lookup"><span data-stu-id="6e575-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="6e575-133">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="6e575-133">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="6e575-134">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6e575-134">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="6e575-135">dynamic</span><span class="sxs-lookup"><span data-stu-id="6e575-135">dynamic</span></span>](dynamic.md)
