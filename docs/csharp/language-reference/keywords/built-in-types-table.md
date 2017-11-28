---
title: "Таблица встроенных типов (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9d1e4945526a862074e73e608185696328946be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="ee86f-102">Таблица встроенных типов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ee86f-102">Built-In Types Table (C# Reference)</span></span>
<span data-ttu-id="ee86f-103">В следующей таблице показаны ключевые слова для встроенных типов C#, которые являются псевдонимами предопределенных типов в пространстве имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="ee86f-103">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="ee86f-104">Тип C#</span><span class="sxs-lookup"><span data-stu-id="ee86f-104">C# Type</span></span>|<span data-ttu-id="ee86f-105">Тип .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ee86f-105">.NET Framework Type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="ee86f-106">bool</span><span class="sxs-lookup"><span data-stu-id="ee86f-106">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[<span data-ttu-id="ee86f-107">byte</span><span class="sxs-lookup"><span data-stu-id="ee86f-107">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[<span data-ttu-id="ee86f-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="ee86f-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[<span data-ttu-id="ee86f-109">char</span><span class="sxs-lookup"><span data-stu-id="ee86f-109">char</span></span>](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[<span data-ttu-id="ee86f-110">decimal</span><span class="sxs-lookup"><span data-stu-id="ee86f-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[<span data-ttu-id="ee86f-111">double</span><span class="sxs-lookup"><span data-stu-id="ee86f-111">double</span></span>](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[<span data-ttu-id="ee86f-112">float</span><span class="sxs-lookup"><span data-stu-id="ee86f-112">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[<span data-ttu-id="ee86f-113">int</span><span class="sxs-lookup"><span data-stu-id="ee86f-113">int</span></span>](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[<span data-ttu-id="ee86f-114">uint</span><span class="sxs-lookup"><span data-stu-id="ee86f-114">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[<span data-ttu-id="ee86f-115">long</span><span class="sxs-lookup"><span data-stu-id="ee86f-115">long</span></span>](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[<span data-ttu-id="ee86f-116">ulong</span><span class="sxs-lookup"><span data-stu-id="ee86f-116">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[<span data-ttu-id="ee86f-117">object</span><span class="sxs-lookup"><span data-stu-id="ee86f-117">object</span></span>](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[<span data-ttu-id="ee86f-118">short</span><span class="sxs-lookup"><span data-stu-id="ee86f-118">short</span></span>](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[<span data-ttu-id="ee86f-119">ushort</span><span class="sxs-lookup"><span data-stu-id="ee86f-119">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[<span data-ttu-id="ee86f-120">string</span><span class="sxs-lookup"><span data-stu-id="ee86f-120">string</span></span>](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a><span data-ttu-id="ee86f-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee86f-121">Remarks</span></span>  
 <span data-ttu-id="ee86f-122">Все типы в таблице, за исключением `object` и `string`, считаются простыми.</span><span class="sxs-lookup"><span data-stu-id="ee86f-122">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
 <span data-ttu-id="ee86f-123">Ключевые слова типов C# и их псевдонимы являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="ee86f-123">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="ee86f-124">Например, можно объявить целочисленную переменную с помощью любого из следующих объявлений:</span><span class="sxs-lookup"><span data-stu-id="ee86f-124">For example, you can declare an integer variable by using either of the following declarations:</span></span>  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 <span data-ttu-id="ee86f-125">Чтобы отобразить фактический тип для любого типа C#, используйте системный метод `GetType()`.</span><span class="sxs-lookup"><span data-stu-id="ee86f-125">To display the actual type for any C# type, use the system method `GetType()`.</span></span> <span data-ttu-id="ee86f-126">Например, следующий оператор выводит системный псевдоним, который представляет тип `myVariable`:</span><span class="sxs-lookup"><span data-stu-id="ee86f-126">For example, the following statement displays the system alias that represents the type of `myVariable`:</span></span>  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 <span data-ttu-id="ee86f-127">Также можно использовать оператор [typeof](../../../csharp/language-reference/keywords/typeof.md).</span><span class="sxs-lookup"><span data-stu-id="ee86f-127">You can also use the [typeof](../../../csharp/language-reference/keywords/typeof.md) operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee86f-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ee86f-128">See Also</span></span>  
 [<span data-ttu-id="ee86f-129">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ee86f-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ee86f-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ee86f-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ee86f-131">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ee86f-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ee86f-132">Типы значений</span><span class="sxs-lookup"><span data-stu-id="ee86f-132">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="ee86f-133">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ee86f-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="ee86f-134">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="ee86f-134">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [<span data-ttu-id="ee86f-135">dynamic</span><span class="sxs-lookup"><span data-stu-id="ee86f-135">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
 [<span data-ttu-id="ee86f-136">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="ee86f-136">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
