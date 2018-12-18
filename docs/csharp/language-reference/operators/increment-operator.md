---
title: Справочник по C#. Оператор ++
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: db716f0d8cfe252462abeee9c80baaab880e212b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235648"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6c301-102">Оператор ++ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6c301-102">++ Operator (C# Reference)</span></span>

<span data-ttu-id="6c301-103">Оператор инкремента `++` увеличивает операнд на 1.</span><span class="sxs-lookup"><span data-stu-id="6c301-103">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="6c301-104">Он поддерживается в двух формах: постфиксный оператор инкремента и `x++` префиксный оператор инкремента `++x`.</span><span class="sxs-lookup"><span data-stu-id="6c301-104">It's supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

## <a name="postfix-increment-operator"></a><span data-ttu-id="6c301-105">Постфиксный оператор приращения</span><span class="sxs-lookup"><span data-stu-id="6c301-105">Postfix increment operator</span></span>

<span data-ttu-id="6c301-106">Результатом `x++` является значение `x` *перед* выполнением операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6c301-106">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a><span data-ttu-id="6c301-107">Префиксный оператор инкремента</span><span class="sxs-lookup"><span data-stu-id="6c301-107">Prefix increment operator</span></span>

<span data-ttu-id="6c301-108">Результатом `++x` является значение `x` *после* выполнения операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6c301-108">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a><span data-ttu-id="6c301-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c301-109">Remarks</span></span>

<span data-ttu-id="6c301-110">Оператор инкремента является стандартным для всех [целочисленных типов](../keywords/integral-types-table.md) (включая тип [char](../keywords/char.md)), [типы с плавающей запятой](../keywords/floating-point-types-table.md) и любой тип [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="6c301-110">The increment operator is predefined for all [integral types](../keywords/integral-types-table.md) (including the [char](../keywords/char.md) type), [floating-point types](../keywords/floating-point-types-table.md), and any [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="6c301-111">Операндом оператора инкремента должна быть переменная, [свойство](../../programming-guide/classes-and-structs/properties.md) или [индексатор](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6c301-111">An operand of the increment operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="6c301-112">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="6c301-112">Operator overloadability</span></span>

<span data-ttu-id="6c301-113">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `++`.</span><span class="sxs-lookup"><span data-stu-id="6c301-113">User-defined types can [overload](../keywords/operator.md) the `++` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6c301-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6c301-114">C# language specification</span></span>

<span data-ttu-id="6c301-115">Дополнительные сведения см. в разделе о [постфиксных](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) и [префиксных](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) операторах инкремента и декремента в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6c301-115">For more information, see the [Postfix increment and decrement operators](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) and [Prefix increment and decrement operators](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c301-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6c301-116">See also</span></span>

- [<span data-ttu-id="6c301-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6c301-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6c301-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6c301-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6c301-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="6c301-119">C# Operators</span></span>](index.md)
- [<span data-ttu-id="6c301-120">Оператор --</span><span class="sxs-lookup"><span data-stu-id="6c301-120">-- Operator</span></span>](decrement-operator.md)
- [<span data-ttu-id="6c301-121">Практическое руководство. Увеличение и уменьшение указателей</span><span class="sxs-lookup"><span data-stu-id="6c301-121">How to: increment and decrement pointers</span></span>](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
