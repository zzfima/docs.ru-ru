---
title: Справочник по C#. Арифметические операторы
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 19f74e6835ae555a3a38aa6ca8679948c7f290dd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712758"
---
# <a name="assignment-operators-c-reference"></a><span data-ttu-id="26b2b-102">Справочник по C#. Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="26b2b-102">Assignment operators (C# reference)</span></span>

<span data-ttu-id="26b2b-103">Оператор присваивания `=` назначает значение расположенного в правой части операнда переменной, [свойству](../../programming-guide/classes-and-structs/properties.md) или элементу [индексатора](../../programming-guide/indexers/index.md), которые указаны в операнде слева.</span><span class="sxs-lookup"><span data-stu-id="26b2b-103">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="26b2b-104">Результатом выражения присваивания является значение, назначенное расположенному слева операнду.</span><span class="sxs-lookup"><span data-stu-id="26b2b-104">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="26b2b-105">Расположенный справа операнд должен иметь тот же тип, что и операнд слева, либо же допускать неявное преобразование в этот тип.</span><span class="sxs-lookup"><span data-stu-id="26b2b-105">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="26b2b-106">Оператор присваивания `=` имеет правую ассоциативность, то есть выражение формы:</span><span class="sxs-lookup"><span data-stu-id="26b2b-106">The assignment operator `=` is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="26b2b-107">вычисляется как</span><span class="sxs-lookup"><span data-stu-id="26b2b-107">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="26b2b-108">В следующем примере показано использование оператора присваивания с локальной переменной, свойством и элементом индексатора в качестве левого операнда:</span><span class="sxs-lookup"><span data-stu-id="26b2b-108">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="26b2b-109">Ссылочный оператор присваивания</span><span class="sxs-lookup"><span data-stu-id="26b2b-109">ref assignment operator</span></span>

<span data-ttu-id="26b2b-110">Начиная с C# 7.3, вы можете использовать ссылочный оператор присваивания `= ref`, чтобы переназначить [ссылочную локальную переменную](../keywords/ref.md#ref-locals) или [ссылочную локальную переменную только для чтения](../keywords/ref.md#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="26b2b-110">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="26b2b-111">В следующем примере иллюстрируется использование ссылочного оператора присваивания:</span><span class="sxs-lookup"><span data-stu-id="26b2b-111">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="26b2b-112">При использовании ссылочного оператора присваивания тип левого и правого операндов должен быть одинаковым.</span><span class="sxs-lookup"><span data-stu-id="26b2b-112">In the case of the ref assignment operator, the both of its operands must be of the same type.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="26b2b-113">Составное присваивание</span><span class="sxs-lookup"><span data-stu-id="26b2b-113">Compound assignment</span></span>

<span data-ttu-id="26b2b-114">Для бинарного оператора `op` выражение составного присваивания в форме</span><span class="sxs-lookup"><span data-stu-id="26b2b-114">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="26b2b-115">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="26b2b-115">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="26b2b-116">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="26b2b-116">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="26b2b-117">Составное присваивание поддерживается [арифметическими](arithmetic-operators.md#compound-assignment), [логическими](boolean-logical-operators.md#compound-assignment), [побитовыми логическими операторами и операторами смещения](bitwise-and-shift-operators.md#compound-assignment).</span><span class="sxs-lookup"><span data-stu-id="26b2b-117">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="26b2b-118">Присваивание объединения со значением NULL</span><span class="sxs-lookup"><span data-stu-id="26b2b-118">Null-coalescing assignment</span></span>

<span data-ttu-id="26b2b-119">Начиная с C# 8.0 вы можете использовать оператор присваивания объединения со значением NULL `??=` для присваивания значения правого операнда левому операнду только в том случае, если левый операнд принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="26b2b-119">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="26b2b-120">Дополнительные сведения см. в статье [Операторы ?? и ??=](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="26b2b-120">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="26b2b-121">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="26b2b-121">Operator overloadability</span></span>

<span data-ttu-id="26b2b-122">Пользовательский тип не может [перегружать](operator-overloading.md) оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="26b2b-122">A user-defined type cannot [overload](operator-overloading.md) the assignment operator.</span></span> <span data-ttu-id="26b2b-123">Однако пользовательский тип может определять неявное преобразование в другой тип.</span><span class="sxs-lookup"><span data-stu-id="26b2b-123">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="26b2b-124">Таким образом, значение пользовательского типа может быть присвоено переменной, свойству или элементу индексатора другого типа.</span><span class="sxs-lookup"><span data-stu-id="26b2b-124">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="26b2b-125">Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="26b2b-125">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

<span data-ttu-id="26b2b-126">Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.</span><span class="sxs-lookup"><span data-stu-id="26b2b-126">A user-defined type cannot explicitly overload a compound assignment operator.</span></span> <span data-ttu-id="26b2b-127">Но если пользовательский тип перегружает бинарный оператор `op`, существующий оператор `op=` также будет неявно перегружен.</span><span class="sxs-lookup"><span data-stu-id="26b2b-127">However, if a user-defined type overloads a binary operator `op`, the `op=` operator, if it exists, is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="26b2b-128">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="26b2b-128">C# language specification</span></span>

<span data-ttu-id="26b2b-129">Подробные сведения см. в разделе [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) (Операторы присваивания) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="26b2b-129">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="26b2b-130">См. сведения о ссылочном операторе присваивания `= ref` в [примечании к функциям](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="26b2b-130">For more information about the ref assignment operator `= ref`, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26b2b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="26b2b-131">See also</span></span>

- [<span data-ttu-id="26b2b-132">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="26b2b-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="26b2b-133">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="26b2b-133">C# operators</span></span>](index.md)
- [<span data-ttu-id="26b2b-134">Ключевое слово ref</span><span class="sxs-lookup"><span data-stu-id="26b2b-134">ref keyword</span></span>](../keywords/ref.md)
