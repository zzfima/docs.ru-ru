---
title: "Выражения значения по умолчанию (руководство по программированию на C#)"
description: "Выражения значения по умолчанию создают значение по умолчанию для любого ссылочного типа или типа значения"
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: ru-ru
ms.lasthandoff: 08/29/2017

---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="5ed08-103">Выражения значения по умолчанию (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5ed08-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="5ed08-104">Выражение значения по умолчанию создает значение по умолчанию для типа.</span><span class="sxs-lookup"><span data-stu-id="5ed08-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="5ed08-105">Выражения значения по умолчанию особенно полезны в универсальных классах и методах.</span><span class="sxs-lookup"><span data-stu-id="5ed08-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="5ed08-106">Одна из проблем при использовании универсальных шаблонов связана с присваиванием значения по умолчанию параметризованному типу `T`, для которого заранее неизвестны следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="5ed08-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="5ed08-107">Будет ли тип `T` ссылочным типом или типом значения.</span><span class="sxs-lookup"><span data-stu-id="5ed08-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="5ed08-108">Если тип `T` является типом значения, будет ли это числовое значение или пользовательская структура.</span><span class="sxs-lookup"><span data-stu-id="5ed08-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="5ed08-109">При заданной переменной `t` параметризованного типа `T` оператор `t = null` действителен, только если `T` является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="5ed08-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="5ed08-110">Присваивание `t = 0` работает только для типов числовых значений, но не для структур.</span><span class="sxs-lookup"><span data-stu-id="5ed08-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="5ed08-111">В качестве решения используйте выражение значения по умолчанию, которое возвращает `null` для ссылочных типов (типы классов и интерфейсов), а также нуль для типов числовых значений.</span><span class="sxs-lookup"><span data-stu-id="5ed08-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="5ed08-112">Для пользовательских структур оно возвращает структуру, инициализированную шаблоном нулевых бит, который создает 0 или `null` для каждого элемента в зависимости от того, является ли элемент значением или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="5ed08-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="5ed08-113">Для типов значений, допускающих значения NULL, ключевое слово `default` возвращает <xref:System.Nullable%601?displayProperty=fullName>, которое инициализируется как любая другая структура.</span><span class="sxs-lookup"><span data-stu-id="5ed08-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=fullName>, which is initialized like any struct.</span></span>

<span data-ttu-id="5ed08-114">Выражение `default(T)` не ограничивается универсальными классами и методами.</span><span class="sxs-lookup"><span data-stu-id="5ed08-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="5ed08-115">Выражения значения по умолчанию можно использовать с любым управляемым типом.</span><span class="sxs-lookup"><span data-stu-id="5ed08-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="5ed08-116">Любые из следующих выражений допустимы.</span><span class="sxs-lookup"><span data-stu-id="5ed08-116">Any of these expressions are valid:</span></span>

 <span data-ttu-id="5ed08-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span><span class="sxs-lookup"><span data-stu-id="5ed08-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span></span>

 <span data-ttu-id="5ed08-118">В следующем примере из класса `GenericList<T>` показано, как использовать оператор `default(T)` в универсальном классе.</span><span class="sxs-lookup"><span data-stu-id="5ed08-118">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="5ed08-119">Дополнительные сведения см. в разделе [Общие сведения об универсальных шаблонах](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="5ed08-119">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 <span data-ttu-id="5ed08-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span><span class="sxs-lookup"><span data-stu-id="5ed08-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span></span>

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="5ed08-121">Литерал по умолчанию и определение типа</span><span class="sxs-lookup"><span data-stu-id="5ed08-121">default literal and type inference</span></span>

<span data-ttu-id="5ed08-122">Начиная с C# 7.1, литерал `default` может использоваться для выражений значения по умолчанию, если компилятор может вывести тип выражения.</span><span class="sxs-lookup"><span data-stu-id="5ed08-122">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="5ed08-123">Литерал `default` создает то же значение, что и эквивалент `default(T)`, где `T` является выведенным типом.</span><span class="sxs-lookup"><span data-stu-id="5ed08-123">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="5ed08-124">Это может сделать код более компактным за счет сокращения избыточности в случае неоднократного объявления типа.</span><span class="sxs-lookup"><span data-stu-id="5ed08-124">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="5ed08-125">Литерал `default` может использоваться в любом из следующих расположений.</span><span class="sxs-lookup"><span data-stu-id="5ed08-125">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="5ed08-126">инициализатор переменной</span><span class="sxs-lookup"><span data-stu-id="5ed08-126">variable initializer</span></span>
- <span data-ttu-id="5ed08-127">назначение переменных</span><span class="sxs-lookup"><span data-stu-id="5ed08-127">variable assignment</span></span>
- <span data-ttu-id="5ed08-128">объявление значения по умолчанию для необязательного параметра</span><span class="sxs-lookup"><span data-stu-id="5ed08-128">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="5ed08-129">предоставление значения для аргумента вызова метода</span><span class="sxs-lookup"><span data-stu-id="5ed08-129">providing the value for a method call argument</span></span>
- <span data-ttu-id="5ed08-130">оператор return (или выражение в элементе в тексте выражения)</span><span class="sxs-lookup"><span data-stu-id="5ed08-130">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="5ed08-131">В следующем примере показано множество вариантов использования литерала `default` в выражении значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="5ed08-131">The following example shows many usages of the `default` literal in a default value expression:</span></span>

<span data-ttu-id="5ed08-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span><span class="sxs-lookup"><span data-stu-id="5ed08-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5ed08-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5ed08-133">See also</span></span>

 <span data-ttu-id="5ed08-134"><xref:System.Collections.Generic> [Руководство по программированию на C#](../index.md) </span><span class="sxs-lookup"><span data-stu-id="5ed08-134"><xref:System.Collections.Generic> [C# Programming Guide](../index.md) </span></span>  
 <span data-ttu-id="5ed08-135">[Универсальные шаблоны](../generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ed08-135">[Generics](../generics/index.md) </span></span>  
 <span data-ttu-id="5ed08-136">[Универсальные методы](../generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="5ed08-136">[Generic Methods](../generics/generic-methods.md) </span></span>  
 [<span data-ttu-id="5ed08-137">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="5ed08-137">Generics</span></span>](~/docs/standard/generics/index.md)   

