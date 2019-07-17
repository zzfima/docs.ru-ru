---
title: Оператор = — справочник по C#
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 1277b35723777760deebb6606ddc90bd21e654ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744115"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="49b97-102">Оператор = (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="49b97-102">= operator (C# reference)</span></span>

<span data-ttu-id="49b97-103">Оператор присваивания `=` назначает значение расположенного в правой части операнда переменной, [свойству](../../programming-guide/classes-and-structs/properties.md) или элементу [индексатора](../../../csharp/programming-guide/indexers/index.md), которые указаны в операнде слева.</span><span class="sxs-lookup"><span data-stu-id="49b97-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../../csharp/programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="49b97-104">Результатом выражения присваивания является значение, назначенное расположенному слева операнду.</span><span class="sxs-lookup"><span data-stu-id="49b97-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="49b97-105">Расположенный справа операнд должен иметь тот же тип, что и операнд слева, либо же допускать неявное преобразование в этот тип.</span><span class="sxs-lookup"><span data-stu-id="49b97-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="49b97-106">Оператор присваивания имеет правую ассоциативность, то есть выражение формы:</span><span class="sxs-lookup"><span data-stu-id="49b97-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="49b97-107">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="49b97-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="49b97-108">В следующем примере показано использование оператора присваивания с локальной переменной, свойством и элементом индексатора в качестве левого операнда:</span><span class="sxs-lookup"><span data-stu-id="49b97-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="49b97-109">Ссылочный оператор присваивания</span><span class="sxs-lookup"><span data-stu-id="49b97-109">ref assignment operator</span></span>

<span data-ttu-id="49b97-110">Начиная с C# 7.3, вы можете использовать ссылочный оператор присваивания `= ref`, чтобы переназначить [ссылочную локальную переменную](../keywords/ref.md#ref-locals) или [ссылочную локальную переменную только для чтения](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="49b97-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="49b97-111">В следующем примере иллюстрируется использование ссылочного оператора присваивания:</span><span class="sxs-lookup"><span data-stu-id="49b97-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="49b97-112">В случае ссылочного оператора присваивания тип левого и правого операндов должен быть одинаковым.</span><span class="sxs-lookup"><span data-stu-id="49b97-112">In the case of the ref assignment operator, the type of both its operands must be the same.</span></span>

<span data-ttu-id="49b97-113">Дополнительные сведения см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="49b97-113">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="49b97-114">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="49b97-114">Compound assignment</span></span>

<span data-ttu-id="49b97-115">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="49b97-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="49b97-116">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="49b97-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="49b97-117">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="49b97-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="49b97-118">Составное присваивание поддерживается [арифметическими](arithmetic-operators.md#compound-assignment), [логическими](boolean-logical-operators.md#compound-assignment), [побитовыми логическими операторами и операторами смещения](bitwise-and-shift-operators.md#compound-assignment).</span><span class="sxs-lookup"><span data-stu-id="49b97-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="49b97-119">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="49b97-119">Operator overloadability</span></span>

<span data-ttu-id="49b97-120">Пользовательский тип не может перегружать оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="49b97-120">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="49b97-121">Однако пользовательский тип может определять неявное преобразование в другой тип.</span><span class="sxs-lookup"><span data-stu-id="49b97-121">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="49b97-122">Таким образом, значение пользовательского типа может быть присвоено переменной, свойству или элементу индексатора другого типа.</span><span class="sxs-lookup"><span data-stu-id="49b97-122">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="49b97-123">Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="49b97-123">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="49b97-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="49b97-124">C# language specification</span></span>

<span data-ttu-id="49b97-125">Подробные сведения см. в разделе [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) (Операторы присваивания) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="49b97-125">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49b97-126">См. также</span><span class="sxs-lookup"><span data-stu-id="49b97-126">See also</span></span>

- [<span data-ttu-id="49b97-127">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="49b97-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="49b97-128">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="49b97-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="49b97-129">Ключевое слово ref</span><span class="sxs-lookup"><span data-stu-id="49b97-129">ref keyword</span></span>](../keywords/ref.md)
