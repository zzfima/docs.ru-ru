---
title: '- Операторы - и -=. Справочник по C#'
ms.custom: seodec18
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: cf642fcac7233d27f2ed9052829c145038e93419
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038874"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="30cf9-102">Операторы - и -= (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="30cf9-102">- and -= operators (C# reference)</span></span>

<span data-ttu-id="30cf9-103">Операторы `-` и `-=` поддерживаются встроенными [целыми](../builtin-types/integral-numeric-types.md) числовыми типами и числовыми типами [с плавающей запятой](../builtin-types/floating-point-numeric-types.md), а также типами [делегатов](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="30cf9-103">The `-` and `-=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="30cf9-104">Сведения об арифметическом операторе `-` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор вычитания -](arithmetic-operators.md#subtraction-operator--) в статье [Арифметические операторы](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="30cf9-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="30cf9-105">Удаление делегатов</span><span class="sxs-lookup"><span data-stu-id="30cf9-105">Delegate removal</span></span>

<span data-ttu-id="30cf9-106">Для операндов одного и того же типа [delegate](../builtin-types/reference-types.md#the-delegate-type) оператор `-` возвращает экземпляр делегата, который вычисляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="30cf9-106">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="30cf9-107">Если оба операнда не равны NULL и список вызовов правого операнда является соответствующим подчиненным списком списка вызовов левого операнда, результатом операции является новый список вызовов, который получается путем удаления записей правого операнда из списка вызовов левого операнда.</span><span class="sxs-lookup"><span data-stu-id="30cf9-107">If both operands are non-null and the invocation list of the right-hand operand is a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is a new invocation list that is obtained by removing the right-hand operand's entries from the invocation list of the left-hand operand.</span></span> <span data-ttu-id="30cf9-108">Если список правого операнда соответствует нескольким смежным подчиненным спискам в списке левого операнда, удаляется только крайний правый совпадающий подсписок.</span><span class="sxs-lookup"><span data-stu-id="30cf9-108">If the right-hand operand's list matches multiple contiguous sublists in the left-hand operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="30cf9-109">Если удаление приводит к пустому списку, возвращается `null`.</span><span class="sxs-lookup"><span data-stu-id="30cf9-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="30cf9-110">Если список вызовов правого операнда не является соответствующим смежным подчиненным списком списка вызовов левого операнда, результатом операции является левый операнд.</span><span class="sxs-lookup"><span data-stu-id="30cf9-110">If the invocation list of the right-hand operand is not a proper contiguous sublist of the invocation list of the left-hand operand, the result of the operation is the left-hand operand.</span></span> <span data-ttu-id="30cf9-111">Так, удаление делегата, который не является частью многоадресного делегата, ни к чему не приводит и многоадресный делегат никак не меняется.</span><span class="sxs-lookup"><span data-stu-id="30cf9-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="30cf9-112">В предыдущем примере также показано, что во время удаления делегата сравниваются его экземпляры.</span><span class="sxs-lookup"><span data-stu-id="30cf9-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="30cf9-113">Например, делегаты, созданные в результате оценки идентичных [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) не будут равны.</span><span class="sxs-lookup"><span data-stu-id="30cf9-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="30cf9-114">Дополнительные сведения о равенстве делегатов см. в разделе об [операторах равенства делегатов](~/_csharplang/spec/expressions.md#delegate-equality-operators) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="30cf9-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="30cf9-115">Если левый операнд имеет значение `null`, результатом операции является `null`.</span><span class="sxs-lookup"><span data-stu-id="30cf9-115">If the left-hand operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="30cf9-116">Если правый операнд имеет значение `null`, результатом операции является левый операнд.</span><span class="sxs-lookup"><span data-stu-id="30cf9-116">If the right-hand operand is `null`, the result of the operation is the left-hand operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="30cf9-117">Объединить делегаты можно с помощью [оператора `+`](addition-operator.md#delegate-combination).</span><span class="sxs-lookup"><span data-stu-id="30cf9-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="30cf9-118">См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="30cf9-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="30cf9-119">Оператор присваивания вычитания (-=)</span><span class="sxs-lookup"><span data-stu-id="30cf9-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="30cf9-120">Выражение, использующее оператор `-=`, такое как</span><span class="sxs-lookup"><span data-stu-id="30cf9-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="30cf9-121">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="30cf9-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="30cf9-122">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="30cf9-122">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="30cf9-123">В следующем примере иллюстрируется использование оператора `-=`.</span><span class="sxs-lookup"><span data-stu-id="30cf9-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="30cf9-124">Можно также использовать оператор `-=`, который позволяет указать метод обработчика событий для удаления при отмене подписки на [событие](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="30cf9-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="30cf9-125">Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="30cf9-125">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="30cf9-126">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="30cf9-126">Operator overloadability</span></span>

<span data-ttu-id="30cf9-127">Определяемый пользователем тип может [перегружать](operator-overloading.md) оператор `-`.</span><span class="sxs-lookup"><span data-stu-id="30cf9-127">A user-defined type can [overload](operator-overloading.md) the `-` operator.</span></span> <span data-ttu-id="30cf9-128">При перегрузке бинарного оператора `-` неявно перегружается и соответствующий оператор `-=`.</span><span class="sxs-lookup"><span data-stu-id="30cf9-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="30cf9-129">Определяемый пользователем тип не может перегружать оператор `-=` явным образом.</span><span class="sxs-lookup"><span data-stu-id="30cf9-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="30cf9-130">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="30cf9-130">C# language specification</span></span>

<span data-ttu-id="30cf9-131">Дополнительные сведения см. в разделе [Оператор унарного минуса](~/_csharplang/spec/expressions.md#unary-minus-operator) и [Оператор вычитания](~/_csharplang/spec/expressions.md#subtraction-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="30cf9-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="30cf9-132">См. также</span><span class="sxs-lookup"><span data-stu-id="30cf9-132">See also</span></span>

- [<span data-ttu-id="30cf9-133">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="30cf9-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="30cf9-134">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="30cf9-134">C# operators</span></span>](index.md)
- [<span data-ttu-id="30cf9-135">События</span><span class="sxs-lookup"><span data-stu-id="30cf9-135">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="30cf9-136">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="30cf9-136">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="30cf9-137">Операторы + и +=</span><span class="sxs-lookup"><span data-stu-id="30cf9-137">+ and += operators</span></span>](addition-operator.md)
