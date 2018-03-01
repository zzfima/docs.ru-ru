---
title: "Типы значений (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 281b811f2a8a1f2c364405b563f9f103899b492c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-c-reference"></a><span data-ttu-id="e9033-102">Типы значений (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e9033-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="e9033-103">Типы значений относятся к двум основным категориям:</span><span class="sxs-lookup"><span data-stu-id="e9033-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="e9033-104">Структуры</span><span class="sxs-lookup"><span data-stu-id="e9033-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="e9033-105">Перечисления</span><span class="sxs-lookup"><span data-stu-id="e9033-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="e9033-106">Структуры делятся на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="e9033-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="e9033-107">Числовые типы</span><span class="sxs-lookup"><span data-stu-id="e9033-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="e9033-108">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="e9033-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="e9033-109">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="e9033-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [<span data-ttu-id="e9033-110">decimal</span><span class="sxs-lookup"><span data-stu-id="e9033-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [<span data-ttu-id="e9033-111">bool</span><span class="sxs-lookup"><span data-stu-id="e9033-111">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="e9033-112">Определяемые пользователем структуры.</span><span class="sxs-lookup"><span data-stu-id="e9033-112">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="e9033-113">Основные возможности типов значений</span><span class="sxs-lookup"><span data-stu-id="e9033-113">Main Features of Value Types</span></span>  
 <span data-ttu-id="e9033-114">Переменные, основанные на типах значений, непосредственно содержат значения.</span><span class="sxs-lookup"><span data-stu-id="e9033-114">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="e9033-115">Если присвоить одну переменную типа значения другой, в нее будет скопировано содержащееся в исходной переменной значение.</span><span class="sxs-lookup"><span data-stu-id="e9033-115">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="e9033-116">В этом заключается отличие от присвоения переменных ссылочного типа, при котором копируется не сам объект, а ссылка на него.</span><span class="sxs-lookup"><span data-stu-id="e9033-116">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="e9033-117">Все типы значения являются неявными производными от <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9033-117">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="e9033-118">В отличие от ссылочных типов, создать новый производный от типа значения тип нельзя.</span><span class="sxs-lookup"><span data-stu-id="e9033-118">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="e9033-119">Тем не менее, как и ссылочные типы, структуры могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="e9033-119">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="e9033-120">В отличие от ссылочных типов, тип значения не может содержать значение `null`.</span><span class="sxs-lookup"><span data-stu-id="e9033-120">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="e9033-121">Тем не менее с помощью [типов, допускающих значение null](../../../csharp/programming-guide/nullable-types/index.md), можно присваивать типы значений значениям `null`.</span><span class="sxs-lookup"><span data-stu-id="e9033-121">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="e9033-122">Каждый тип значения имеет неявный конструктор по умолчанию, который инициализирует значение по умолчанию для этого типа.</span><span class="sxs-lookup"><span data-stu-id="e9033-122">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="e9033-123">Дополнительные сведения о значениях по умолчанию для типов значений см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e9033-123">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="e9033-124">Основные возможности простых типов</span><span class="sxs-lookup"><span data-stu-id="e9033-124">Main Features of Simple Types</span></span>  
 <span data-ttu-id="e9033-125">Все простые типы, реализованные в языке C#, являются псевдонимами системных типов платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="e9033-125">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="e9033-126">Например, [int](../../../csharp/language-reference/keywords/int.md) является псевдонимом типа <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9033-126">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9033-127">Полный список псевдонимов см. в разделе [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="e9033-127">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="e9033-128">Константные выражения, операнды которых являются константами простого типа, вычисляются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="e9033-128">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="e9033-129">Простые типы можно инициализировать с помощью литералов.</span><span class="sxs-lookup"><span data-stu-id="e9033-129">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="e9033-130">Например, "A" — это литерал типа `char`, а "2001" — литерал типа `int`.</span><span class="sxs-lookup"><span data-stu-id="e9033-130">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="e9033-131">Инициализация типов значений</span><span class="sxs-lookup"><span data-stu-id="e9033-131">Initializing Value Types</span></span>  
 <span data-ttu-id="e9033-132">В языке C# локальные переменные необходимо инициализировать перед использованием.</span><span class="sxs-lookup"><span data-stu-id="e9033-132">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="e9033-133">Например, можно объявить локальную переменную без инициализации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e9033-133">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```  
int myInt;  
```  
  
 <span data-ttu-id="e9033-134">Тем не менее использовать ее до инициализации нельзя.</span><span class="sxs-lookup"><span data-stu-id="e9033-134">You cannot use it before you initialize it.</span></span> <span data-ttu-id="e9033-135">Для инициализации локальной переменной можно использовать следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="e9033-135">You can initialize it using the following statement:</span></span>  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="e9033-136">Эта инструкция эквивалентна следующей:</span><span class="sxs-lookup"><span data-stu-id="e9033-136">This statement is equivalent to the following statement:</span></span>  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="e9033-137">При необходимости объявление и инициализация могут быть выполнены в одной инструкции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e9033-137">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```  
int myInt = new int();  
```  
  
 <span data-ttu-id="e9033-138">– или –</span><span class="sxs-lookup"><span data-stu-id="e9033-138">–or–</span></span>  
  
```  
int myInt = 0;  
```  
  
 <span data-ttu-id="e9033-139">Инструкция [new](../../../csharp/language-reference/keywords/new.md) вызывает конструктор по умолчанию для конкретного типа и присваивает переменной значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9033-139">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="e9033-140">В предыдущем примере конструктор по умолчанию присваивает значение `0` переменной `myInt`.</span><span class="sxs-lookup"><span data-stu-id="e9033-140">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="e9033-141">Дополнительные сведения о значениях, присваиваемых путем вызова конструктора по умолчанию, см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e9033-141">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="e9033-142">Для определяемых пользователем типов инструкция [new](../../../csharp/language-reference/keywords/new.md) вызывает конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9033-142">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="e9033-143">Например, следующая инструкция вызывает конструктор по умолчанию для структуры `Point`:</span><span class="sxs-lookup"><span data-stu-id="e9033-143">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="e9033-144">После этого вызова структура считается определенно присвоенной, то есть все ее элементы будут инициализированы и получат значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9033-144">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="e9033-145">Дополнительные сведения об операторе new см. в [этом разделе](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="e9033-145">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="e9033-146">Дополнительные сведения о форматировании выходных данных числовых типов см. в разделе [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="e9033-146">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9033-147">См. также</span><span class="sxs-lookup"><span data-stu-id="e9033-147">See Also</span></span>  
 [<span data-ttu-id="e9033-148">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e9033-148">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e9033-149">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e9033-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e9033-150">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e9033-150">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e9033-151">Типы</span><span class="sxs-lookup"><span data-stu-id="e9033-151">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="e9033-152">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="e9033-152">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [<span data-ttu-id="e9033-153">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="e9033-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
