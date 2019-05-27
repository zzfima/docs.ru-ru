---
title: Операторы для доступа к членам. Справочник по C#
description: Дополнительные сведения об операторах C#, которые можно использовать для доступа к членам типа.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: a76c2855196b229918ee0a6a7d2a4dc66d87d059
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881047"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="67b06-103">Операторы доступа к членам (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="67b06-103">Member access operators (C# Reference)</span></span>

<span data-ttu-id="67b06-104">При доступе к члену типа можно использовать следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="67b06-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="67b06-105">[`.` (доступ к члену) ](#member-access-operator-): для доступа к члену пространства имен или типа;</span><span class="sxs-lookup"><span data-stu-id="67b06-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="67b06-106">[`[]` (элемент массива или индексатор доступа) ](#indexer-operator-): для доступа к элементу массива или индексатору типа;</span><span class="sxs-lookup"><span data-stu-id="67b06-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="67b06-107">[`?.` и `?[]` (null-условные операторы)](#null-conditional-operators--and-): для выполнения операции доступа члена или элемента только в том случае, если операнд не равен null;</span><span class="sxs-lookup"><span data-stu-id="67b06-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="67b06-108">[`()` (вызов) ](#invocation-operator-): для вызова метода или делегата.</span><span class="sxs-lookup"><span data-stu-id="67b06-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="67b06-109">Оператор доступа к элементу .</span><span class="sxs-lookup"><span data-stu-id="67b06-109">Member access operator .</span></span>

<span data-ttu-id="67b06-110">Маркер `.` используется для обращения к члену пространства имен или типа, как в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="67b06-110">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="67b06-111">Используйте `.` для обращения к пространству имен, вложенному в другое пространство имен, как показано в следующем примере [директивы `using`](../keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-111">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="67b06-112">Используйте `.` для создания *полного имени* для обращения к типу в пределах пространства имен, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="67b06-112">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="67b06-113">Используйте [директиву `using`](../keywords/using-directive.md), чтобы сделать использование полных имен необязательным.</span><span class="sxs-lookup"><span data-stu-id="67b06-113">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="67b06-114">Используйте `.` для обращения к [членам типов](../../programming-guide/classes-and-structs/index.md#members) (статическим и нестатическим), как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="67b06-114">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="67b06-115">Можно также использовать `.` для вызова [метода расширения](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-115">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="67b06-116">Оператор индексатора []</span><span class="sxs-lookup"><span data-stu-id="67b06-116">Indexer operator []</span></span>

<span data-ttu-id="67b06-117">Квадратные скобки, `[]`, обычно используются для доступа к элементам массива, индексатора или указателя.</span><span class="sxs-lookup"><span data-stu-id="67b06-117">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="67b06-118">Доступ к массиву</span><span class="sxs-lookup"><span data-stu-id="67b06-118">Array access</span></span>

<span data-ttu-id="67b06-119">В приведенном ниже примере показано, как получить доступ к элементам массива.</span><span class="sxs-lookup"><span data-stu-id="67b06-119">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="67b06-120">Если индекс массива выходит за границы соответствующего измерения массива, возникает исключение <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="67b06-120">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="67b06-121">Как показано в предыдущем примере, квадратные скобки также используются в объявлении типа массива и для создания экземпляров массива.</span><span class="sxs-lookup"><span data-stu-id="67b06-121">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="67b06-122">Дополнительные сведения см. в руководстве по работе с [массивами](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-122">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="67b06-123">Доступ к индексатору</span><span class="sxs-lookup"><span data-stu-id="67b06-123">Indexer access</span></span>

<span data-ttu-id="67b06-124">В приведенном ниже примере используется тип .NET <xref:System.Collections.Generic.Dictionary%602> для демонстрации доступа к индексатору.</span><span class="sxs-lookup"><span data-stu-id="67b06-124">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="67b06-125">Индексаторы позволяют индексировать экземпляры определяемого пользователем типа аналогично индексации массива.</span><span class="sxs-lookup"><span data-stu-id="67b06-125">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="67b06-126">В отличие от индексов массива, которые должны быть целым числом, аргументы индексатора могут быть объявлены любым типом.</span><span class="sxs-lookup"><span data-stu-id="67b06-126">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="67b06-127">Дополнительные сведения см. в [руководстве по работе с индексаторами](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-127">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="67b06-128">Другие данные об использовании []</span><span class="sxs-lookup"><span data-stu-id="67b06-128">Other usages of []</span></span>

<span data-ttu-id="67b06-129">Сведения о доступе к элементу указателя см. в разделе, посвященном [оператору доступа к элементу указателя []](pointer-related-operators.md#pointer-element-access-operator-), статьи [Операторы, связанные с указателем](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-129">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="67b06-130">Кроме того, с помощью квадратных скобок можно указывать [атрибуты](../../programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-130">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="67b06-131">NULL-условные операторы: ?.</span><span class="sxs-lookup"><span data-stu-id="67b06-131">Null-conditional operators ?.</span></span> <span data-ttu-id="67b06-132">и ?[]</span><span class="sxs-lookup"><span data-stu-id="67b06-132">and ?[]</span></span>

<span data-ttu-id="67b06-133">В C# 6 и более поздних версий доступен null-условный оператор доступа к членам, `?.`, или доступа к элементам, `?[]`, который дает доступ к операнду только в том случае, если он имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="67b06-133">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="67b06-134">Если операнд имеет значение `null`, результатом применения оператора является `null`.</span><span class="sxs-lookup"><span data-stu-id="67b06-134">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span>

<span data-ttu-id="67b06-135">Операторы с условием NULL предусматривают сокращенную обработку.</span><span class="sxs-lookup"><span data-stu-id="67b06-135">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="67b06-136">Таким образом, если одна из операций в цепочке условных операций доступа к члену и операций индексирования возвращает значение `null`, то выполнение остальной части цепочки прекращается.</span><span class="sxs-lookup"><span data-stu-id="67b06-136">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="67b06-137">В следующем примере `B` вычисляется только в том случае, если `A` принимает значение `null`, а `C` вычисляется только в том случае, если `A` или `B` принимает значение `null`.</span><span class="sxs-lookup"><span data-stu-id="67b06-137">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="67b06-138">В следующем примере иллюстрируется использование операторов `?.` и `?[]`.</span><span class="sxs-lookup"><span data-stu-id="67b06-138">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="67b06-139">В предыдущем примере также показано использование [оператора объединения с null](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-139">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="67b06-140">Можно использовать оператор объединения с null, чтобы задать альтернативное выражение для оценки на случай, если результат null-условной операции будет равен `null`.</span><span class="sxs-lookup"><span data-stu-id="67b06-140">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="67b06-141">Потокобезопасный вызов делегата</span><span class="sxs-lookup"><span data-stu-id="67b06-141">Thread-safe delegate invocation</span></span>

<span data-ttu-id="67b06-142">Используйте оператор `?.` для проверки того, что делегат не равен null, и его вызова потокобезопасным способом (например, в том случае, когда вы собираетесь [породить событие](../../../standard/events/how-to-raise-and-consume-events.md)), как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="67b06-142">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="67b06-143">Этот код эквивалентен следующему коду, который будет использоваться в C# 5 или более ранней версии:</span><span class="sxs-lookup"><span data-stu-id="67b06-143">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="67b06-144">Оператор вызова ()</span><span class="sxs-lookup"><span data-stu-id="67b06-144">Invocation operator ()</span></span>

<span data-ttu-id="67b06-145">Используйте скобки, `()`, чтобы вызвать [метод](../../programming-guide/classes-and-structs/methods.md) или [делегат](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-145">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="67b06-146">Приведенный ниже пример демонстрирует вызов делегата и метода с аргументами или без них.</span><span class="sxs-lookup"><span data-stu-id="67b06-146">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/snippets/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="67b06-147">Круглые скобки также можно использовать при вызове [конструктора](../../programming-guide/classes-and-structs/constructors.md) с оператором [`new`](../keywords/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-147">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="67b06-148">Другие данные об использовании ()</span><span class="sxs-lookup"><span data-stu-id="67b06-148">Other usages of ()</span></span>

<span data-ttu-id="67b06-149">Кроме того, с помощью круглых скобок можно указывать порядок выполнения операций в выражении.</span><span class="sxs-lookup"><span data-stu-id="67b06-149">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="67b06-150">Дополнительные сведения см. в разделе [Добавление скобок](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) руководства по использованию [операторов](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-150">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="67b06-151">Список операторов, упорядоченных по уровню приоритета, см. в статье [Операторы в C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="67b06-151">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

<span data-ttu-id="67b06-152">[Выражения приведения](invocation-operator.md#cast-expression), которые вызывают оператор преобразования, также используют круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="67b06-152">[Cast expressions](invocation-operator.md#cast-expression), which invoke a conversion operator, also use parentheses.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="67b06-153">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="67b06-153">Operator overloadability</span></span>

<span data-ttu-id="67b06-154">Операторы `.` и `()` не могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="67b06-154">The `.` and `()` operators cannot be overloaded.</span></span> <span data-ttu-id="67b06-155">Оператор `[]` также считается неперегружаемым.</span><span class="sxs-lookup"><span data-stu-id="67b06-155">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="67b06-156">Используйте [индексаторы](../../programming-guide/indexers/index.md) для поддержки индексирования с помощью определяемых пользователем типов.</span><span class="sxs-lookup"><span data-stu-id="67b06-156">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="67b06-157">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="67b06-157">C# language specification</span></span>

<span data-ttu-id="67b06-158">Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="67b06-158">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="67b06-159">Доступ к членам</span><span class="sxs-lookup"><span data-stu-id="67b06-159">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="67b06-160">Доступ к элементам</span><span class="sxs-lookup"><span data-stu-id="67b06-160">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="67b06-161">Null-условный оператор</span><span class="sxs-lookup"><span data-stu-id="67b06-161">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="67b06-162">Выражения вызова</span><span class="sxs-lookup"><span data-stu-id="67b06-162">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="67b06-163">См. также</span><span class="sxs-lookup"><span data-stu-id="67b06-163">See also</span></span>

- [<span data-ttu-id="67b06-164">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="67b06-164">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="67b06-165">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="67b06-165">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="67b06-166">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="67b06-166">C# Operators</span></span>](index.md)
- [<span data-ttu-id="67b06-167">Оператор ?? (оператор объединения со значением NULL)</span><span class="sxs-lookup"><span data-stu-id="67b06-167">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
