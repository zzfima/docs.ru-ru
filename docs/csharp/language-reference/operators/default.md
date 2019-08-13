---
title: Справочник по C#. Оператор default
ms.custom: seodec18
description: Использование оператора default для создания значения по умолчанию для типа
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 5623cb9dc3790b5bb99635c41cb3f122f4c71d8e
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796943"
---
# <a name="default-operator-c-reference"></a><span data-ttu-id="b6079-103">Оператор default (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b6079-103">default operator (C# reference)</span></span>

<span data-ttu-id="b6079-104">Оператор `default` создает значение [по умолчанию](../keywords/default-values-table.md) для типа.</span><span class="sxs-lookup"><span data-stu-id="b6079-104">The `default` operator produces the [default value](../keywords/default-values-table.md) of a type.</span></span> <span data-ttu-id="b6079-105">Оператор `default` принимает в качестве аргумента имя типа или параметр типа.</span><span class="sxs-lookup"><span data-stu-id="b6079-105">The argument to the `default` operator must be the name of a type or a type parameter.</span></span>

<span data-ttu-id="b6079-106">В следующем примере показано применение оператора `default`.</span><span class="sxs-lookup"><span data-stu-id="b6079-106">The following example shows the usage of the `default` operator:</span></span>

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

<span data-ttu-id="b6079-107">Также используется ключевое слово `default` в качестве метки варианта по умолчанию в [инструкции `switch`](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="b6079-107">You also use the `default` keyword as the default case label within the [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-literal"></a><span data-ttu-id="b6079-108">Литерал default</span><span class="sxs-lookup"><span data-stu-id="b6079-108">default literal</span></span>

<span data-ttu-id="b6079-109">Начиная с C# 7.1, можно использовать литерал `default` для создания значения по умолчанию для типа, если компилятор может вывести тип выражения.</span><span class="sxs-lookup"><span data-stu-id="b6079-109">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="b6079-110">Литеральное выражение `default` создает то же значение, что и выражение `default(T)`, где `T` является выведенным типом.</span><span class="sxs-lookup"><span data-stu-id="b6079-110">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="b6079-111">Литерал `default` можно использовать в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="b6079-111">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="b6079-112">при назначении или инициализации переменной;</span><span class="sxs-lookup"><span data-stu-id="b6079-112">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="b6079-113">в объявлении значения по умолчанию для необязательного параметра метода;</span><span class="sxs-lookup"><span data-stu-id="b6079-113">In the declaration of the default value for an optional method parameter.</span></span>
- <span data-ttu-id="b6079-114">в вызове метода для предоставления значения аргумента;</span><span class="sxs-lookup"><span data-stu-id="b6079-114">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="b6079-115">в инструкции `return` или в качестве выражения в элементе в тексте выражения.</span><span class="sxs-lookup"><span data-stu-id="b6079-115">In a `return` statement or as an expression in an expression-bodied member.</span></span>

<span data-ttu-id="b6079-116">Ниже приведен пример применения литерала `default`.</span><span class="sxs-lookup"><span data-stu-id="b6079-116">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="b6079-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b6079-117">C# language specification</span></span>

<span data-ttu-id="b6079-118">Дополнительные сведения см. в разделе о [выражениях значения по умолчанию](~/_csharplang/spec/expressions.md#default-value-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b6079-118">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="b6079-119">Дополнительные сведения о литерале `default` см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span><span class="sxs-lookup"><span data-stu-id="b6079-119">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6079-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b6079-120">See also</span></span>

- [<span data-ttu-id="b6079-121">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b6079-121">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b6079-122">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b6079-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="b6079-123">Таблица значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b6079-123">Default values table</span></span>](../keywords/default-values-table.md)
