---
title: Справочник по C#. Оператор =
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 40dc844f2a4b6411ea82aa2f029b36d7dd8f6e5a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716328"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6b617-102">Оператор = (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6b617-102">= Operator (C# Reference)</span></span>

<span data-ttu-id="6b617-103">Оператор присваивания `=` назначает значение расположенного в правой части операнда переменной, [свойству](../../programming-guide/classes-and-structs/properties.md) или элементу [индексатора](../../../csharp/programming-guide/indexers/index.md), которые указаны в операнде слева.</span><span class="sxs-lookup"><span data-stu-id="6b617-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="6b617-104">Результатом выражения присваивания является значение, назначенное расположенному слева операнду.</span><span class="sxs-lookup"><span data-stu-id="6b617-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="6b617-105">Расположенный справа операнд должен иметь тот же тип, что и операнд слева, либо же допускать неявное преобразование в этот тип.</span><span class="sxs-lookup"><span data-stu-id="6b617-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="6b617-106">Оператор присваивания имеет правую ассоциативность, то есть выражение формы:</span><span class="sxs-lookup"><span data-stu-id="6b617-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="6b617-107">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="6b617-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="6b617-108">В следующем примере показано использование оператора присваивания для назначения значений локальной переменной, свойству и элементу индексатора:</span><span class="sxs-lookup"><span data-stu-id="6b617-108">The following example demonstrates the usage of the assignment operator to assign values to a local variable, a property, and an indexer element:</span></span>

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="6b617-109">Ссылочный оператор присваивания</span><span class="sxs-lookup"><span data-stu-id="6b617-109">ref assignment operator</span></span>

<span data-ttu-id="6b617-110">Начиная с C# 7.3, вы можете использовать ссылочный оператор присваивания `= ref`, чтобы переназначить [ссылочную локальную переменную](../keywords/ref.md#ref-locals) или [ссылочную локальную переменную только для чтения](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="6b617-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="6b617-111">В следующем примере иллюстрируется использование ссылочного оператора присваивания:</span><span class="sxs-lookup"><span data-stu-id="6b617-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

<span data-ttu-id="6b617-112">В случае ссылочного оператора присваивания тип левого и правого операнда должен быть одинаковым.</span><span class="sxs-lookup"><span data-stu-id="6b617-112">In the case of the ref assignment operator, the type of the left operand and the right operand must be the same.</span></span>

<span data-ttu-id="6b617-113">Дополнительные сведения см. в [примечании к предлагаемой функции](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="6b617-113">For more information, see the [feature proposal note](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="6b617-114">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="6b617-114">Operator overloadability</span></span>

<span data-ttu-id="6b617-115">Пользовательский тип не может перегружать оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="6b617-115">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="6b617-116">Однако пользовательский тип может определять неявное преобразование в другой тип.</span><span class="sxs-lookup"><span data-stu-id="6b617-116">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="6b617-117">Таким образом, значение пользовательского типа может быть присвоено переменной, свойству или элементу индексатора другого типа.</span><span class="sxs-lookup"><span data-stu-id="6b617-117">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="6b617-118">Дополнительные сведения см. в статье [implicit (Справочник по C#)](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="6b617-118">For more information, see the [implicit](../keywords/implicit.md) keyword article.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6b617-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6b617-119">C# language specification</span></span>

<span data-ttu-id="6b617-120">Дополнительные сведения см. в разделе [Простое присваивание](~/_csharplang/spec/expressions.md#simple-assignment) в статье о [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6b617-120">For more information, see the [Simple assignment](~/_csharplang/spec/expressions.md#simple-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b617-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6b617-121">See also</span></span>

- [<span data-ttu-id="6b617-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6b617-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6b617-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6b617-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6b617-124">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="6b617-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="6b617-125">Ключевое слово ref</span><span class="sxs-lookup"><span data-stu-id="6b617-125">ref keyword</span></span>](../keywords/ref.md)
