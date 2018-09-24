---
title: Оператор false (справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "46578730"
---
# <a name="false-operator-c-reference"></a><span data-ttu-id="31311-102">Оператор false (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="31311-102">false operator (C# Reference)</span></span>

<span data-ttu-id="31311-103">Возвращает [логическое](bool.md) значение `true`, чтобы указать, что операнд является `false`, и возвращает значение `false` в противном случае.</span><span class="sxs-lookup"><span data-stu-id="31311-103">Returns the [bool](bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>

<span data-ttu-id="31311-104">До версии C# 2.0 операторы `true` и `false` использовались для создания пользовательских типов значений, допускающих значение NULL, которые были совместимы с такими типами, как `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="31311-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="31311-105">Однако теперь язык предоставляет встроенную поддержку для типов, допускающих значение NULL, и по возможности следует использовать их вместо перегрузки операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="31311-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="31311-106">Дополнительные сведения см. в разделе [Типы, допускающие значение NULL](../../programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="31311-106">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="31311-107">С логическими значениями, допускающими значение NULL, выражение `a != b` не обязательно равно `!(a == b)`, так как одно или оба значений могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="31311-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="31311-108">Необходимо перегрузить оба оператора `true` и `false` отдельно, чтобы правильно обработать значения NULL в выражении.</span><span class="sxs-lookup"><span data-stu-id="31311-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="31311-109">В следующем примере демонстрируется перегрузка и использование операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="31311-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

<span data-ttu-id="31311-110">Тип, который перегружает операторы `true` и `false`, может использоваться для выражений управления в операторах [if](if-else.md), [do](do.md), [while](while.md) и [for](for.md) и в [условных выражениях](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="31311-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in [conditional expressions](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="31311-111">Если тип определяет оператор `false`, он должен также определять оператор [true](true.md).</span><span class="sxs-lookup"><span data-stu-id="31311-111">If a type defines operator `false`, it must also define operator [true](true.md).</span></span>

<span data-ttu-id="31311-112">Тип не может непосредственно перегрузить условные логические операторы [&&](../operators/conditional-and-operator.md) и [||](../operators/conditional-or-operator.md), однако такой же результат может быть достигнут путем перегрузки обычных логических операторов и операторов `true` и `false`.</span><span class="sxs-lookup"><span data-stu-id="31311-112">A type cannot directly overload the conditional logical operators [&&](../operators/conditional-and-operator.md) and [&#124;&#124;](../operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="31311-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="31311-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="31311-114">См. также</span><span class="sxs-lookup"><span data-stu-id="31311-114">See also</span></span>

- [<span data-ttu-id="31311-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="31311-115">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="31311-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="31311-116">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="31311-117">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="31311-117">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="31311-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="31311-118">C# Operators</span></span>](../operators/index.md)  
- [<span data-ttu-id="31311-119">true</span><span class="sxs-lookup"><span data-stu-id="31311-119">true</span></span>](true.md)  