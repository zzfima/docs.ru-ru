---
title: Оператор = — справочник по C#
ms.custom: seodec18
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: a450a55524f33f4f06ed077aba864e8f641a458d
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70924656"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="219fb-102">Оператор = (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="219fb-102">= operator (C# reference)</span></span>

<span data-ttu-id="219fb-103">Оператор присваивания `=` назначает значение расположенного в правой части операнда переменной, [свойству](../../programming-guide/classes-and-structs/properties.md) или элементу [индексатора](../../programming-guide/indexers/index.md), которые указаны в операнде слева.</span><span class="sxs-lookup"><span data-stu-id="219fb-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="219fb-104">Результатом выражения присваивания является значение, назначенное расположенному слева операнду.</span><span class="sxs-lookup"><span data-stu-id="219fb-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="219fb-105">Расположенный справа операнд должен иметь тот же тип, что и операнд слева, либо же допускать неявное преобразование в этот тип.</span><span class="sxs-lookup"><span data-stu-id="219fb-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="219fb-106">Оператор присваивания имеет правую ассоциативность, то есть выражение формы:</span><span class="sxs-lookup"><span data-stu-id="219fb-106">The assignment operator is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="219fb-107">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="219fb-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="219fb-108">В следующем примере показано использование оператора присваивания с локальной переменной, свойством и элементом индексатора в качестве левого операнда:</span><span class="sxs-lookup"><span data-stu-id="219fb-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="219fb-109">Ссылочный оператор присваивания</span><span class="sxs-lookup"><span data-stu-id="219fb-109">ref assignment operator</span></span>

<span data-ttu-id="219fb-110">Начиная с C# 7.3, вы можете использовать ссылочный оператор присваивания `= ref`, чтобы переназначить [ссылочную локальную переменную](../keywords/ref.md#ref-locals) или [ссылочную локальную переменную только для чтения](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="219fb-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="219fb-111">В следующем примере иллюстрируется использование ссылочного оператора присваивания:</span><span class="sxs-lookup"><span data-stu-id="219fb-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="219fb-112">В случае ссылочного оператора присваивания тип левого и правого операндов должен быть одинаковым.</span><span class="sxs-lookup"><span data-stu-id="219fb-112">In the case of the ref assignment operator, the type of both its operands must be the same.</span></span>

<span data-ttu-id="219fb-113">Дополнительные сведения см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="219fb-113">For more information, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="219fb-114">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="219fb-114">Compound assignment</span></span>

<span data-ttu-id="219fb-115">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="219fb-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="219fb-116">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="219fb-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="219fb-117">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="219fb-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="219fb-118">Составное присваивание поддерживается [арифметическими](arithmetic-operators.md#compound-assignment), [логическими](boolean-logical-operators.md#compound-assignment), [побитовыми логическими операторами и операторами смещения](bitwise-and-shift-operators.md#compound-assignment).</span><span class="sxs-lookup"><span data-stu-id="219fb-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="219fb-119">Присваивание объединения со значением NULL</span><span class="sxs-lookup"><span data-stu-id="219fb-119">Null-coalescing assignment</span></span>

<span data-ttu-id="219fb-120">Начиная с C# 8.0 вы можете использовать оператор присваивания объединения со значением NULL `??=` для присваивания значения правого операнда левому операнду только в том случае, если левый операнд принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="219fb-120">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="219fb-121">Дополнительные сведения см. в статье [Операторы ?? и ??=](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="219fb-121">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="219fb-122">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="219fb-122">Operator overloadability</span></span>

<span data-ttu-id="219fb-123">Пользовательский тип не может перегружать оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="219fb-123">A user-defined type cannot overload the assignment operator.</span></span> <span data-ttu-id="219fb-124">Однако пользовательский тип может определять неявное преобразование в другой тип.</span><span class="sxs-lookup"><span data-stu-id="219fb-124">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="219fb-125">Таким образом, значение пользовательского типа может быть присвоено переменной, свойству или элементу индексатора другого типа.</span><span class="sxs-lookup"><span data-stu-id="219fb-125">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="219fb-126">Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="219fb-126">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="219fb-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="219fb-127">C# language specification</span></span>

<span data-ttu-id="219fb-128">Подробные сведения см. в разделе [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) (Операторы присваивания) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="219fb-128">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="219fb-129">См. также</span><span class="sxs-lookup"><span data-stu-id="219fb-129">See also</span></span>

- [<span data-ttu-id="219fb-130">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="219fb-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="219fb-131">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="219fb-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="219fb-132">Ключевое слово ref</span><span class="sxs-lookup"><span data-stu-id="219fb-132">ref keyword</span></span>](../keywords/ref.md)
