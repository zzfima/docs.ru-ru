---
title: Справочник по C#. Типы значений
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 390b2226cc2f345d2f42659bd092e36a4bd0c4fc
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632931"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="dad82-102">Типы значений (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="dad82-102">Value types (C# Reference)</span></span>

<span data-ttu-id="dad82-103">Существует два типа значений:</span><span class="sxs-lookup"><span data-stu-id="dad82-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="dad82-104">Структуры</span><span class="sxs-lookup"><span data-stu-id="dad82-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="dad82-105">Перечисления</span><span class="sxs-lookup"><span data-stu-id="dad82-105">Enumerations</span></span>](enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="dad82-106">Основные возможности типов значений</span><span class="sxs-lookup"><span data-stu-id="dad82-106">Main features of value types</span></span>

<span data-ttu-id="dad82-107">Переменная типа значения содержит значение типа.</span><span class="sxs-lookup"><span data-stu-id="dad82-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="dad82-108">Например, переменная типа `int` может содержать значение `42`.</span><span class="sxs-lookup"><span data-stu-id="dad82-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="dad82-109">Это отличается от переменной ссылочного типа, которая содержит ссылку на экземпляр типа, также известный как объект.</span><span class="sxs-lookup"><span data-stu-id="dad82-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="dad82-110">Когда вы присваиваете новое значение переменной типа значения, это значение копируется.</span><span class="sxs-lookup"><span data-stu-id="dad82-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="dad82-111">Когда вы присваиваете новое значение переменной ссылочного типа, копируется не сам объект, а ссылка на него.</span><span class="sxs-lookup"><span data-stu-id="dad82-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="dad82-112">Все типы значения являются неявными производными от <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dad82-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="dad82-113">В отличие от ссылочных типов, создать новый производный от типа значения тип нельзя.</span><span class="sxs-lookup"><span data-stu-id="dad82-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="dad82-114">Тем не менее, как и ссылочные типы, структуры могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="dad82-114">However, like reference types, structs can implement interfaces.</span></span>

<span data-ttu-id="dad82-115">Переменные типа значения не могут иметь значение `null` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dad82-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="dad82-116">Однако переменные соответствующих [типов, допускающих значение null](../../../csharp/programming-guide/nullable-types/index.md), могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="dad82-116">However, variables of the corresponding [nullable types](../../../csharp/programming-guide/nullable-types/index.md) can be `null`.</span></span>

<span data-ttu-id="dad82-117">Каждый тип значения имеет неявный конструктор без параметров, который инициализирует значение по умолчанию этого типа.</span><span class="sxs-lookup"><span data-stu-id="dad82-117">Each value type has an implicit parameterless constructor that initializes the default value of that type.</span></span> <span data-ttu-id="dad82-118">Дополнительные сведения о значениях по умолчанию для типов значений см. в разделе [Таблица значений по умолчанию (справочник по C#)](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>

## <a name="simple-types"></a><span data-ttu-id="dad82-119">Простые типы</span><span class="sxs-lookup"><span data-stu-id="dad82-119">Simple types</span></span>

<span data-ttu-id="dad82-120">*Простые типы* — это набор предопределенных типов структур, предоставленных C#, который содержит следующие типы:</span><span class="sxs-lookup"><span data-stu-id="dad82-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="dad82-121">[Целочисленные типы](integral-types-table.md): типы целого числа и тип [char](char.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-121">[Integral types](integral-types-table.md): integer numeric types and the [char](char.md) type</span></span>
- [<span data-ttu-id="dad82-122">Типы с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="dad82-122">Floating-point types</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="dad82-123">bool</span><span class="sxs-lookup"><span data-stu-id="dad82-123">bool</span></span>](bool.md)

<span data-ttu-id="dad82-124">Простые типы определяются с помощью ключевых слов, но эти ключевые слова являются просто псевдонимами для предопределенных типов структур в пространстве имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="dad82-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="dad82-125">Например, [int](int.md) является псевдонимом типа <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dad82-125">For example, [int](int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dad82-126">Полный список псевдонимов см. в разделе [Таблица встроенных типов (Справочник по C#)](built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="dad82-127">Простые типы отличаются от других типов структур тем, что они разрешают некоторые дополнительные операции:</span><span class="sxs-lookup"><span data-stu-id="dad82-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="dad82-128">Простые типы можно инициализировать с помощью литералов.</span><span class="sxs-lookup"><span data-stu-id="dad82-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="dad82-129">Например, `'A'` — это литерал типа `char`, а `2001` — литерал типа `int`.</span><span class="sxs-lookup"><span data-stu-id="dad82-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="dad82-130">Константы простых типов можно объявить с помощью ключевого слова [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="dad82-131">Невозможно иметь константы других типов структур.</span><span class="sxs-lookup"><span data-stu-id="dad82-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="dad82-132">Константные выражения, операнды которых являются константами простого типа, вычисляются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="dad82-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="dad82-133">Дополнительные сведения см. в разделе [Простые типы](~/_csharplang/spec/types.md#simple-types) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="initializing-value-types"></a><span data-ttu-id="dad82-134">Инициализация типов значений</span><span class="sxs-lookup"><span data-stu-id="dad82-134">Initializing value types</span></span>

<span data-ttu-id="dad82-135">В языке C# локальные переменные необходимо инициализировать перед использованием.</span><span class="sxs-lookup"><span data-stu-id="dad82-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="dad82-136">Например, можно объявить локальную переменную без инициализации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="dad82-136">For example, you might declare a local variable without initialization as in the following example:</span></span>

```csharp
int myInt;
```

<span data-ttu-id="dad82-137">Тем не менее использовать ее до инициализации нельзя.</span><span class="sxs-lookup"><span data-stu-id="dad82-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="dad82-138">Для инициализации локальной переменной можно использовать следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="dad82-138">You can initialize it using the following statement:</span></span>

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

<span data-ttu-id="dad82-139">Эта инструкция эквивалентна следующей:</span><span class="sxs-lookup"><span data-stu-id="dad82-139">This statement is equivalent to the following statement:</span></span>

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

<span data-ttu-id="dad82-140">При необходимости объявление и инициализация могут быть выполнены в одной инструкции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="dad82-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="dad82-141">– или –</span><span class="sxs-lookup"><span data-stu-id="dad82-141">–or–</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="dad82-142">Оператор [new](new.md) вызывает конструктор без параметров конкретного типа и присваивает переменной значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dad82-142">Using the [new](new.md) operator calls the parameterless constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="dad82-143">В приведенном выше примере конструктору без параметров присвоено значение `0` для `myInt`.</span><span class="sxs-lookup"><span data-stu-id="dad82-143">In the preceding example, the parameterless constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="dad82-144">Дополнительные сведения о значениях, присваиваемых путем вызова конструктора по умолчанию, см. в разделе [Таблица значений по умолчанию (справочник по C#)](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-144">For more information about values assigned by calling default constructors, see [Default values table](default-values-table.md).</span></span>

<span data-ttu-id="dad82-145">С определяемыми пользователем типами используйте [new](new.md) для вызова конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="dad82-145">With user-defined types, use [new](new.md) to invoke the parameterless constructor.</span></span> <span data-ttu-id="dad82-146">Например, следующая инструкция вызывает конструктор без параметров структуры `Point`:</span><span class="sxs-lookup"><span data-stu-id="dad82-146">For example, the following statement invokes the parameterless constructor of the `Point` struct:</span></span>

```csharp
Point p = new Point(); // Invoke parameterless constructor for the struct.
```

<span data-ttu-id="dad82-147">После этого вызова структура считается определенно присвоенной, то есть все ее элементы будут инициализированы и получат значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dad82-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>

<span data-ttu-id="dad82-148">Дополнительные сведения об операторе `new` см. в разделе [new (справочник по C#)](new.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-148">For more information about the `new` operator, see [new](new.md).</span></span>

<span data-ttu-id="dad82-149">Дополнительные сведения о форматировании выходных данных числовых типов см. в разделе [Таблица форматирования числовых результатов (справочник по C#)](formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="dad82-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dad82-150">См. также</span><span class="sxs-lookup"><span data-stu-id="dad82-150">See also</span></span>

- [<span data-ttu-id="dad82-151">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="dad82-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dad82-152">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dad82-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dad82-153">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="dad82-153">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dad82-154">Типы</span><span class="sxs-lookup"><span data-stu-id="dad82-154">Types</span></span>](types.md)
- [<span data-ttu-id="dad82-155">Справочные таблицы по типам</span><span class="sxs-lookup"><span data-stu-id="dad82-155">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="dad82-156">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="dad82-156">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="dad82-157">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="dad82-157">Nullable types</span></span>](../../programming-guide/nullable-types/index.md)
