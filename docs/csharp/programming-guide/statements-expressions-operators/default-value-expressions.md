---
title: Выражения значения по умолчанию (руководство по программированию на C#)
description: Выражения значения по умолчанию создают значение по умолчанию для любого ссылочного типа или типа значения
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 94866f22fb3ad921a834cffb16fe17e44cef5965
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46698405"
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="6f719-103">Выражения значения по умолчанию (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6f719-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="6f719-104">Выражение значения по умолчанию `default(T)` создает значение по умолчанию с типом `T`.</span><span class="sxs-lookup"><span data-stu-id="6f719-104">A default value expression `default(T)` produces the default value of a type `T`.</span></span> <span data-ttu-id="6f719-105">В следующей таблице показаны значения, которые создаются для различных типов.</span><span class="sxs-lookup"><span data-stu-id="6f719-105">The following table shows which values are produced for various types:</span></span>

|<span data-ttu-id="6f719-106">Тип</span><span class="sxs-lookup"><span data-stu-id="6f719-106">Type</span></span>|<span data-ttu-id="6f719-107">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6f719-107">Default value</span></span>|
|---------|---------|
|<span data-ttu-id="6f719-108">любой ссылочный тип;</span><span class="sxs-lookup"><span data-stu-id="6f719-108">Any reference type</span></span>|`null`|
|<span data-ttu-id="6f719-109">Тип числового значения</span><span class="sxs-lookup"><span data-stu-id="6f719-109">Numeric value type</span></span>|<span data-ttu-id="6f719-110">Нуль</span><span class="sxs-lookup"><span data-stu-id="6f719-110">Zero</span></span>|
|[<span data-ttu-id="6f719-111">bool</span><span class="sxs-lookup"><span data-stu-id="6f719-111">bool</span></span>](../../language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="6f719-112">char</span><span class="sxs-lookup"><span data-stu-id="6f719-112">char</span></span>](../../language-reference/keywords/char.md)|`'\0'`|
|[<span data-ttu-id="6f719-113">enum</span><span class="sxs-lookup"><span data-stu-id="6f719-113">enum</span></span>](../../language-reference/keywords/enum.md)|<span data-ttu-id="6f719-114">Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.</span><span class="sxs-lookup"><span data-stu-id="6f719-114">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="6f719-115">struct</span><span class="sxs-lookup"><span data-stu-id="6f719-115">struct</span></span>](../../language-reference/keywords/struct.md)|<span data-ttu-id="6f719-116">Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="6f719-116">The value produced by setting all value type fields to their default value and all reference type fields to `null`.</span></span>|
|<span data-ttu-id="6f719-117">Тип, допускающий значение NULL</span><span class="sxs-lookup"><span data-stu-id="6f719-117">Nullable type</span></span>|<span data-ttu-id="6f719-118">Экземпляр, свойство `false` которого имеет значение <xref:System.Nullable%601.HasValue%2A>, а свойство <xref:System.Nullable%601.Value%2A> не определено.</span><span class="sxs-lookup"><span data-stu-id="6f719-118">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>|

<span data-ttu-id="6f719-119">Выражения значения по умолчанию особенно полезны в универсальных классах и методах.</span><span class="sxs-lookup"><span data-stu-id="6f719-119">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="6f719-120">Одна из проблем при использовании универсальных шаблонов связана с присваиванием значения по умолчанию параметризованного типа `T`, для которого заранее неизвестны следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="6f719-120">One issue that arises using generics is how to assign a default value of a parameterized type `T` when you don't know the following in advance:</span></span>

- <span data-ttu-id="6f719-121">Будет ли тип `T` ссылочным типом или типом значения.</span><span class="sxs-lookup"><span data-stu-id="6f719-121">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="6f719-122">Если тип `T` является типом значения, будет ли это числовое значение или структура.</span><span class="sxs-lookup"><span data-stu-id="6f719-122">If `T` is a value type, whether it's a numeric value or a struct.</span></span>

 <span data-ttu-id="6f719-123">При заданной переменной `t` параметризованного типа `T` оператор `t = null` действителен, только если `T` является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="6f719-123">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="6f719-124">Присваивание `t = 0` работает только для типов числовых значений, но не для структур.</span><span class="sxs-lookup"><span data-stu-id="6f719-124">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="6f719-125">Чтобы решить этот вопрос, используйте выражение значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="6f719-125">To solve that, use a default value expression:</span></span>

```csharp
T t = default(T);
```

<span data-ttu-id="6f719-126">Выражение `default(T)` не ограничивается универсальными классами и методами.</span><span class="sxs-lookup"><span data-stu-id="6f719-126">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="6f719-127">Выражения значения по умолчанию можно использовать с любым управляемым типом.</span><span class="sxs-lookup"><span data-stu-id="6f719-127">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="6f719-128">Любые из следующих выражений допустимы.</span><span class="sxs-lookup"><span data-stu-id="6f719-128">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="6f719-129">В следующем примере из класса `GenericList<T>` показано, как использовать оператор `default(T)` в универсальном классе.</span><span class="sxs-lookup"><span data-stu-id="6f719-129">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="6f719-130">Дополнительные сведения см. в разделе [Введение в универсальные шаблоны](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="6f719-130">For more information, see [Introduction to Generics](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="6f719-131">Литерал по умолчанию и определение типа</span><span class="sxs-lookup"><span data-stu-id="6f719-131">default literal and type inference</span></span>

<span data-ttu-id="6f719-132">Начиная с C# 7.1, литерал `default` может использоваться для выражений значения по умолчанию, если компилятор может вывести тип выражения.</span><span class="sxs-lookup"><span data-stu-id="6f719-132">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="6f719-133">Литерал `default` создает то же значение, что и эквивалент `default(T)`, где `T` является выведенным типом.</span><span class="sxs-lookup"><span data-stu-id="6f719-133">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="6f719-134">Это может сделать код более компактным за счет сокращения избыточности в случае неоднократного объявления типа.</span><span class="sxs-lookup"><span data-stu-id="6f719-134">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="6f719-135">Литерал `default` может использоваться в любом из следующих расположений.</span><span class="sxs-lookup"><span data-stu-id="6f719-135">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="6f719-136">инициализатор переменной</span><span class="sxs-lookup"><span data-stu-id="6f719-136">variable initializer</span></span>
- <span data-ttu-id="6f719-137">назначение переменных</span><span class="sxs-lookup"><span data-stu-id="6f719-137">variable assignment</span></span>
- <span data-ttu-id="6f719-138">объявление значения по умолчанию для необязательного параметра</span><span class="sxs-lookup"><span data-stu-id="6f719-138">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="6f719-139">предоставление значения для аргумента вызова метода</span><span class="sxs-lookup"><span data-stu-id="6f719-139">providing the value for a method call argument</span></span>
- <span data-ttu-id="6f719-140">оператор return (или выражение в элементе в тексте выражения)</span><span class="sxs-lookup"><span data-stu-id="6f719-140">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="6f719-141">В следующем примере показано множество вариантов использования литерала `default` в выражении значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="6f719-141">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="6f719-142">См. также</span><span class="sxs-lookup"><span data-stu-id="6f719-142">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="6f719-143">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6f719-143">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="6f719-144">Универсальные шаблоны (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6f719-144">Generics (C# Programming Guide)</span></span>](../generics/index.md)  
- [<span data-ttu-id="6f719-145">Универсальные методы</span><span class="sxs-lookup"><span data-stu-id="6f719-145">Generic Methods</span></span>](../generics/generic-methods.md)  
- [<span data-ttu-id="6f719-146">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="6f719-146">Generics in .NET</span></span>](~/docs/standard/generics/index.md)  
- [<span data-ttu-id="6f719-147">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6f719-147">Default values table</span></span>](../../language-reference/keywords/default-values-table.md)
