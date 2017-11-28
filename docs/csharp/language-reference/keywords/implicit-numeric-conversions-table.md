---
title: "Таблица неявных числовых преобразований (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6b1705dca357fd2a155fc1ea9c7fe0f65bad8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="88e49-102">Таблица неявных числовых преобразований (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="88e49-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="88e49-103">В следующей таблице приведены предопределенные неявные числовые преобразования.</span><span class="sxs-lookup"><span data-stu-id="88e49-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="88e49-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="88e49-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="88e49-105">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="88e49-105">From</span></span>|<span data-ttu-id="88e49-106">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="88e49-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="88e49-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="88e49-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="88e49-108">`short`, `int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-109">byte</span><span class="sxs-lookup"><span data-stu-id="88e49-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="88e49-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-111">short</span><span class="sxs-lookup"><span data-stu-id="88e49-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="88e49-112">`int`, `long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-113">ushort</span><span class="sxs-lookup"><span data-stu-id="88e49-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="88e49-114">`int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-115">int</span><span class="sxs-lookup"><span data-stu-id="88e49-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="88e49-116">`long`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-117">uint</span><span class="sxs-lookup"><span data-stu-id="88e49-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="88e49-118">`long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-119">long</span><span class="sxs-lookup"><span data-stu-id="88e49-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="88e49-120">`float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-121">char</span><span class="sxs-lookup"><span data-stu-id="88e49-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="88e49-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="88e49-123">float</span><span class="sxs-lookup"><span data-stu-id="88e49-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="88e49-124">ulong</span><span class="sxs-lookup"><span data-stu-id="88e49-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="88e49-125">`float`, `double` или `decimal`</span><span class="sxs-lookup"><span data-stu-id="88e49-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88e49-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="88e49-126">Remarks</span></span>  
  
-   <span data-ttu-id="88e49-127">При преобразовании из `int`, `uint`, `long` или `ulong` в `float` и из `long` или `ulong` в `double` может быть потеряна точность, но не величина.</span><span class="sxs-lookup"><span data-stu-id="88e49-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="88e49-128">Не поддерживается неявное преобразование в тип `char`.</span><span class="sxs-lookup"><span data-stu-id="88e49-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="88e49-129">Не поддерживается неявное преобразование между типами с плавающей запятой и типом `decimal`.</span><span class="sxs-lookup"><span data-stu-id="88e49-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="88e49-130">Константное выражение типа `int` можно преобразовать в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong`, если значение константного выражения находится в диапазоне конечного типа.</span><span class="sxs-lookup"><span data-stu-id="88e49-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="88e49-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="88e49-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88e49-132">См. также</span><span class="sxs-lookup"><span data-stu-id="88e49-132">See Also</span></span>  
 [<span data-ttu-id="88e49-133">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="88e49-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="88e49-134">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="88e49-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="88e49-135">Таблица целых типов</span><span class="sxs-lookup"><span data-stu-id="88e49-135">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="88e49-136">Таблица встроенных типов</span><span class="sxs-lookup"><span data-stu-id="88e49-136">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="88e49-137">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="88e49-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="88e49-138">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="88e49-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
