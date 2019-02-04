---
title: '>Справочник по C#. Оператор ='
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 821369734e64648714bf89efb0c02d12d4d816e3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256557"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="69797-102">Оператор >= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="69797-102">>= Operator (C# Reference)</span></span>

<span data-ttu-id="69797-103">Оператор отношения "больше или равно" `>=` возвращает `true`, если его первый операнд больше или равен второму. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="69797-103">The "greater than or equal" relational operator `>=` returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise.</span></span> <span data-ttu-id="69797-104">Оператор `>=` поддерживают все числовые типы и типы перечисления.</span><span class="sxs-lookup"><span data-stu-id="69797-104">All numeric and  enumeration types support the `>=` operator.</span></span> <span data-ttu-id="69797-105">Если операнды имеют одинаковый тип [enum](../keywords/enum.md), сравниваются соответствующие значения базового целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="69797-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="69797-106">Если для операторов отношения `==`, `>`, `<`, `>=` и `<=` любой из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результат операции имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="69797-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="69797-107">Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`).</span><span class="sxs-lookup"><span data-stu-id="69797-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="69797-108">Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69797-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="69797-109">В следующем примере иллюстрируется использование оператора `>=`.</span><span class="sxs-lookup"><span data-stu-id="69797-109">The following example demonstrates the usage of the `>=` operator:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="69797-110">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="69797-110">Operator overloadability</span></span>

<span data-ttu-id="69797-111">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `>=`.</span><span class="sxs-lookup"><span data-stu-id="69797-111">User-defined types can [overload](../keywords/operator.md) the `>=` operator.</span></span> <span data-ttu-id="69797-112">Если тип перегружает оператор "больше или равно" `>=`, он также должен перегружать [оператор "меньше или равно"](less-than-equal-operator.md) `<=`.</span><span class="sxs-lookup"><span data-stu-id="69797-112">If a type overloads the "greater than or equal" operator `>=`, it must also overload the ["less than or equal" operator](less-than-equal-operator.md) `<=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="69797-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="69797-113">C# language specification</span></span>

<span data-ttu-id="69797-114">Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="69797-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69797-115">См. также</span><span class="sxs-lookup"><span data-stu-id="69797-115">See also</span></span>

- [<span data-ttu-id="69797-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="69797-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="69797-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="69797-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="69797-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="69797-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="69797-119">Оператор ></span><span class="sxs-lookup"><span data-stu-id="69797-119">> Operator</span></span>](greater-than-operator.md)
- [<span data-ttu-id="69797-120">Оператор ==</span><span class="sxs-lookup"><span data-stu-id="69797-120">== Operator</span></span>](equality-comparison-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
