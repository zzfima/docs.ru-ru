---
title: Типы значений (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 17bbb0280c4db7d91e5d3cc3d3b6233b8db89cdc
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2018
ms.locfileid: "42754973"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="77360-102">Типы значений (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="77360-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="77360-103">Типы значений относятся к двум основным категориям:</span><span class="sxs-lookup"><span data-stu-id="77360-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="77360-104">Структуры</span><span class="sxs-lookup"><span data-stu-id="77360-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="77360-105">Перечисления</span><span class="sxs-lookup"><span data-stu-id="77360-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="77360-106">Структуры делятся на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="77360-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="77360-107">Числовые типы</span><span class="sxs-lookup"><span data-stu-id="77360-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="77360-108">Целочисленные типы</span><span class="sxs-lookup"><span data-stu-id="77360-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="77360-109">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="77360-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
-   [<span data-ttu-id="77360-110">bool</span><span class="sxs-lookup"><span data-stu-id="77360-110">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="77360-111">Определяемые пользователем структуры.</span><span class="sxs-lookup"><span data-stu-id="77360-111">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="77360-112">Основные возможности типов значений</span><span class="sxs-lookup"><span data-stu-id="77360-112">Main Features of Value Types</span></span>  
 <span data-ttu-id="77360-113">Переменные, основанные на типах значений, непосредственно содержат значения.</span><span class="sxs-lookup"><span data-stu-id="77360-113">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="77360-114">Если присвоить одну переменную типа значения другой, в нее будет скопировано содержащееся в исходной переменной значение.</span><span class="sxs-lookup"><span data-stu-id="77360-114">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="77360-115">В этом заключается отличие от присвоения переменных ссылочного типа, при котором копируется не сам объект, а ссылка на него.</span><span class="sxs-lookup"><span data-stu-id="77360-115">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="77360-116">Все типы значения являются неявными производными от <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="77360-116">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="77360-117">В отличие от ссылочных типов, создать новый производный от типа значения тип нельзя.</span><span class="sxs-lookup"><span data-stu-id="77360-117">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="77360-118">Тем не менее, как и ссылочные типы, структуры могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="77360-118">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="77360-119">В отличие от ссылочных типов, тип значения не может содержать значение `null`.</span><span class="sxs-lookup"><span data-stu-id="77360-119">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="77360-120">Тем не менее с помощью [типов, допускающих значение null](../../../csharp/programming-guide/nullable-types/index.md), можно присваивать типы значений значениям `null`.</span><span class="sxs-lookup"><span data-stu-id="77360-120">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="77360-121">Каждый тип значения имеет неявный конструктор по умолчанию, который инициализирует значение по умолчанию для этого типа.</span><span class="sxs-lookup"><span data-stu-id="77360-121">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="77360-122">Дополнительные сведения о значениях по умолчанию для типов значений см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="77360-122">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="77360-123">Основные возможности простых типов</span><span class="sxs-lookup"><span data-stu-id="77360-123">Main Features of Simple Types</span></span>  
 <span data-ttu-id="77360-124">Все простые типы, реализованные в языке C#, являются псевдонимами системных типов платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="77360-124">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="77360-125">Например, [int](../../../csharp/language-reference/keywords/int.md) является псевдонимом типа <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="77360-125">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="77360-126">Полный список псевдонимов см. в разделе [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="77360-126">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="77360-127">Константные выражения, операнды которых являются константами простого типа, вычисляются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="77360-127">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="77360-128">Простые типы можно инициализировать с помощью литералов.</span><span class="sxs-lookup"><span data-stu-id="77360-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="77360-129">Например, "A" — это литерал типа `char`, а "2001" — литерал типа `int`.</span><span class="sxs-lookup"><span data-stu-id="77360-129">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="77360-130">Инициализация типов значений</span><span class="sxs-lookup"><span data-stu-id="77360-130">Initializing Value Types</span></span>  
 <span data-ttu-id="77360-131">В языке C# локальные переменные необходимо инициализировать перед использованием.</span><span class="sxs-lookup"><span data-stu-id="77360-131">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="77360-132">Например, можно объявить локальную переменную без инициализации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="77360-132">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```csharp  
int myInt;  
```  
  
 <span data-ttu-id="77360-133">Тем не менее использовать ее до инициализации нельзя.</span><span class="sxs-lookup"><span data-stu-id="77360-133">You cannot use it before you initialize it.</span></span> <span data-ttu-id="77360-134">Для инициализации локальной переменной можно использовать следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="77360-134">You can initialize it using the following statement:</span></span>  
  
```csharp  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="77360-135">Эта инструкция эквивалентна следующей:</span><span class="sxs-lookup"><span data-stu-id="77360-135">This statement is equivalent to the following statement:</span></span>  
  
```csharp  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="77360-136">При необходимости объявление и инициализация могут быть выполнены в одной инструкции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="77360-136">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```csharp  
int myInt = new int();  
```  
  
 <span data-ttu-id="77360-137">– или –</span><span class="sxs-lookup"><span data-stu-id="77360-137">–or–</span></span>  
  
```csharp  
int myInt = 0;  
```  
  
 <span data-ttu-id="77360-138">Инструкция [new](../../../csharp/language-reference/keywords/new.md) вызывает конструктор по умолчанию для конкретного типа и присваивает переменной значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77360-138">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="77360-139">В предыдущем примере конструктор по умолчанию присваивает значение `0` переменной `myInt`.</span><span class="sxs-lookup"><span data-stu-id="77360-139">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="77360-140">Дополнительные сведения о значениях, присваиваемых путем вызова конструктора по умолчанию, см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="77360-140">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="77360-141">Для определяемых пользователем типов инструкция [new](../../../csharp/language-reference/keywords/new.md) вызывает конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77360-141">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="77360-142">Например, следующая инструкция вызывает конструктор по умолчанию для структуры `Point`:</span><span class="sxs-lookup"><span data-stu-id="77360-142">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```csharp  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="77360-143">После этого вызова структура считается определенно присвоенной, то есть все ее элементы будут инициализированы и получат значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77360-143">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="77360-144">Дополнительные сведения об операторе new см. в [этом разделе](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="77360-144">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="77360-145">Дополнительные сведения о форматировании выходных данных числовых типов см. в разделе [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="77360-145">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77360-146">См. также</span><span class="sxs-lookup"><span data-stu-id="77360-146">See Also</span></span>  
 [<span data-ttu-id="77360-147">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="77360-147">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="77360-148">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="77360-148">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="77360-149">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="77360-149">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="77360-150">Типы</span><span class="sxs-lookup"><span data-stu-id="77360-150">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="77360-151">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="77360-151">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [<span data-ttu-id="77360-152">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="77360-152">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="77360-153">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="77360-153">Nullable types</span></span>](../../programming-guide/nullable-types/index.md)  
