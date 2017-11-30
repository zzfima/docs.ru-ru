---
title: "Выражения значения по умолчанию (руководство по программированию на C#)"
description: "Выражения значения по умолчанию создают значение по умолчанию для любого ссылочного типа или типа значения"
ms.date: 08/23/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c2bb1c269e5347d615c47ab828506aef538c4761
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="2f62f-103">Выражения значения по умолчанию (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2f62f-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="2f62f-104">Выражение значения по умолчанию создает значение по умолчанию для типа.</span><span class="sxs-lookup"><span data-stu-id="2f62f-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="2f62f-105">Выражения значения по умолчанию особенно полезны в универсальных классах и методах.</span><span class="sxs-lookup"><span data-stu-id="2f62f-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="2f62f-106">Одна из проблем при использовании универсальных шаблонов связана с присваиванием значения по умолчанию параметризованному типу `T`, для которого заранее неизвестны следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="2f62f-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="2f62f-107">Будет ли тип `T` ссылочным типом или типом значения.</span><span class="sxs-lookup"><span data-stu-id="2f62f-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="2f62f-108">Если тип `T` является типом значения, будет ли это числовое значение или пользовательская структура.</span><span class="sxs-lookup"><span data-stu-id="2f62f-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="2f62f-109">При заданной переменной `t` параметризованного типа `T` оператор `t = null` действителен, только если `T` является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="2f62f-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="2f62f-110">Присваивание `t = 0` работает только для типов числовых значений, но не для структур.</span><span class="sxs-lookup"><span data-stu-id="2f62f-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="2f62f-111">В качестве решения используйте выражение значения по умолчанию, которое возвращает `null` для ссылочных типов (типы классов и интерфейсов), а также нуль для типов числовых значений.</span><span class="sxs-lookup"><span data-stu-id="2f62f-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="2f62f-112">Для пользовательских структур оно возвращает структуру, инициализированную шаблоном нулевых бит, который создает 0 или `null` для каждого элемента в зависимости от того, является ли элемент значением или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="2f62f-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="2f62f-113">Для типов значений, допускающих значения NULL, ключевое слово `default` возвращает <xref:System.Nullable%601?displayProperty=nameWithType>, которое инициализируется как любая другая структура.</span><span class="sxs-lookup"><span data-stu-id="2f62f-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=nameWithType>, which is initialized like any struct.</span></span>

<span data-ttu-id="2f62f-114">Выражение `default(T)` не ограничивается универсальными классами и методами.</span><span class="sxs-lookup"><span data-stu-id="2f62f-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="2f62f-115">Выражения значения по умолчанию можно использовать с любым управляемым типом.</span><span class="sxs-lookup"><span data-stu-id="2f62f-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="2f62f-116">Любые из следующих выражений допустимы.</span><span class="sxs-lookup"><span data-stu-id="2f62f-116">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="2f62f-117">В следующем примере из класса `GenericList<T>` показано, как использовать оператор `default(T)` в универсальном классе.</span><span class="sxs-lookup"><span data-stu-id="2f62f-117">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="2f62f-118">Дополнительные сведения см. в разделе [Общие сведения об универсальных шаблонах](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="2f62f-118">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="2f62f-119">Литерал по умолчанию и определение типа</span><span class="sxs-lookup"><span data-stu-id="2f62f-119">default literal and type inference</span></span>

<span data-ttu-id="2f62f-120">Начиная с C# 7.1, литерал `default` может использоваться для выражений значения по умолчанию, если компилятор может вывести тип выражения.</span><span class="sxs-lookup"><span data-stu-id="2f62f-120">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="2f62f-121">Литерал `default` создает то же значение, что и эквивалент `default(T)`, где `T` является выведенным типом.</span><span class="sxs-lookup"><span data-stu-id="2f62f-121">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="2f62f-122">Это может сделать код более компактным за счет сокращения избыточности в случае неоднократного объявления типа.</span><span class="sxs-lookup"><span data-stu-id="2f62f-122">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="2f62f-123">Литерал `default` может использоваться в любом из следующих расположений.</span><span class="sxs-lookup"><span data-stu-id="2f62f-123">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="2f62f-124">инициализатор переменной</span><span class="sxs-lookup"><span data-stu-id="2f62f-124">variable initializer</span></span>
- <span data-ttu-id="2f62f-125">назначение переменных</span><span class="sxs-lookup"><span data-stu-id="2f62f-125">variable assignment</span></span>
- <span data-ttu-id="2f62f-126">объявление значения по умолчанию для необязательного параметра</span><span class="sxs-lookup"><span data-stu-id="2f62f-126">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="2f62f-127">предоставление значения для аргумента вызова метода</span><span class="sxs-lookup"><span data-stu-id="2f62f-127">providing the value for a method call argument</span></span>
- <span data-ttu-id="2f62f-128">оператор return (или выражение в элементе в тексте выражения)</span><span class="sxs-lookup"><span data-stu-id="2f62f-128">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="2f62f-129">В следующем примере показано множество вариантов использования литерала `default` в выражении значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="2f62f-129">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="2f62f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2f62f-130">See also</span></span>

 <span data-ttu-id="2f62f-131"><xref:System.Collections.Generic>[Руководство по программированию на C#](../index.md)</span><span class="sxs-lookup"><span data-stu-id="2f62f-131"><xref:System.Collections.Generic> [C# Programming Guide](../index.md)</span></span>  
 [<span data-ttu-id="2f62f-132">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="2f62f-132">Generics</span></span>](../generics/index.md)  
 [<span data-ttu-id="2f62f-133">Универсальные методы</span><span class="sxs-lookup"><span data-stu-id="2f62f-133">Generic Methods</span></span>](../generics/generic-methods.md)  
 [<span data-ttu-id="2f62f-134">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="2f62f-134">Generics</span></span>](~/docs/standard/generics/index.md)  
