---
title: Справочник по C#. Оператор default
description: Создания значения по умолчанию для типа с помощью оператора default
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 744bdf1ec683ef32bba508c260590c0ed4c6e987
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712719"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="7b0ef-103">Оператор default (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7b0ef-103">default operator (C# reference)</span></span>

<span data-ttu-id="7b0ef-104">Оператор `default` создает значение [по умолчанию](../keywords/default-values-table.md) для типа.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-104">The `default` operator produces the [default value](../keywords/default-values-table.md) of a type.</span></span> <span data-ttu-id="7b0ef-105">Оператор `default` принимает в качестве аргумента имя типа или параметр типа.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="7b0ef-106">В следующем примере показано применение оператора `default`.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="7b0ef-107">Также используется ключевое слово `default` в качестве метки варианта по умолчанию в [инструкции `switch`](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-107">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="7b0ef-108">Литерал default</span><span class="sxs-lookup"><span data-stu-id="7b0ef-108">default literal</span></span>

<span data-ttu-id="7b0ef-109">Начиная с C# 7.1, можно использовать литерал `default` для создания значения по умолчанию для типа, если компилятор может вывести тип выражения.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="7b0ef-110">Литеральное выражение `default` создает то же значение, что и выражение `default(T)`, где `T` является выведенным типом.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="7b0ef-111">Литерал `default` можно использовать в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="7b0ef-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="7b0ef-112">при назначении или инициализации переменной;</span><span class="sxs-lookup"><span data-stu-id="7b0ef-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="7b0ef-113">в объявлении значения по умолчанию для [необязательного параметра метода](../../methods.md#optional-parameters-and-arguments);</span><span class="sxs-lookup"><span data-stu-id="7b0ef-113">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="7b0ef-114">в вызове метода для предоставления значения аргумента;</span><span class="sxs-lookup"><span data-stu-id="7b0ef-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="7b0ef-115">в [инструкции `return`](../keywords/return.md) или в качестве выражения в [элементе в тексте выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-115">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="7b0ef-116">Ниже приведен пример применения литерала `default`.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="7b0ef-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7b0ef-117">C# language specification</span></span>

<span data-ttu-id="7b0ef-118">Дополнительные сведения см. в разделе о [выражениях значения по умолчанию](~/_csharplang/spec/expressions.md#default-value-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="7b0ef-119">Дополнительные сведения о литерале `default` см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b0ef-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7b0ef-120">See also</span></span>

- [<span data-ttu-id="7b0ef-121">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7b0ef-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7b0ef-122">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="7b0ef-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="7b0ef-123">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7b0ef-123">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="7b0ef-124">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="7b0ef-124">Generics in .NET</span></span>](../../../standard/generics/index.md)
