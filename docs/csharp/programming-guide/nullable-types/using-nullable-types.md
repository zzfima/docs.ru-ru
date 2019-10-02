---
title: Использование типов значений, допускающих значение NULL. Руководство по программированию на C#
ms.custom: seodec18
description: Узнайте, как в C# использовать типы значений, допускающие значение NULL
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396165"
---
# <a name="using-nullable-value-types-c-programming-guide"></a><span data-ttu-id="36831-103">Использование типов значений, допускающих значение NULL (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="36831-103">Using nullable value types (C# Programming Guide)</span></span>

<span data-ttu-id="36831-104">Типы значений, допускающие значение NULL, могут представлять все значения своего базового типа `T`, а также дополнительное значение [NULL](../../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="36831-104">Nullable value types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="36831-105">Дополнительные сведения см. в статье [Типы значений, допускающие значение NULL (руководство по программированию на C#)](index.md).</span><span class="sxs-lookup"><span data-stu-id="36831-105">For more information, see the [Nullable value types](index.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="36831-106">В C# 8.0 появилась возможность использования ссылочных типов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="36831-106">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="36831-107">Дополнительные сведения см. в статье [Ссылочные типы, допускающие значение NULL](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="36831-107">For more information, see [Nullable reference types](../../nullable-references.md).</span></span> <span data-ttu-id="36831-108">Типы значений, допускающие значение NULL, доступны начиная с C# 2.</span><span class="sxs-lookup"><span data-stu-id="36831-108">The nullable value types are available starting with C# 2.</span></span>

<span data-ttu-id="36831-109">Вы можете ссылаться на тип значения, допускающий значение NULL, в любой из следующих взаимозаменяемых форм: `Nullable<T>` или `T?`.</span><span class="sxs-lookup"><span data-stu-id="36831-109">You can refer to a nullable value type in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="36831-110">`T` должно быть типом значения.</span><span class="sxs-lookup"><span data-stu-id="36831-110">`T` must be a value type.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="36831-111">Назначение и объявление</span><span class="sxs-lookup"><span data-stu-id="36831-111">Declaration and assignment</span></span>

<span data-ttu-id="36831-112">Так как тип значения можно неявно преобразовать в соответствующий тип значения, допускающий значение NULL, вы назначаете значение такому типу значения так же, как его базовому типу значения.</span><span class="sxs-lookup"><span data-stu-id="36831-112">As a value type can be implicitly converted to the corresponding nullable value type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="36831-113">Вы также можете присвоить значение `null`.</span><span class="sxs-lookup"><span data-stu-id="36831-113">You also can assign the `null` value.</span></span> <span data-ttu-id="36831-114">Например:</span><span class="sxs-lookup"><span data-stu-id="36831-114">For example:</span></span>

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="36831-115">Изучение значение типа, допускающего значение NULL</span><span class="sxs-lookup"><span data-stu-id="36831-115">Examination of a nullable type value</span></span>

<span data-ttu-id="36831-116">Используйте следующие свойства только для чтения, чтобы изучить экземпляр типа значения, допускающего значение NULL, со значением NULL и извлечь значение базового типа:</span><span class="sxs-lookup"><span data-stu-id="36831-116">Use the following readonly properties to examine an instance of a nullable value type for null and retrieve a value of an underlying type:</span></span>

- <span data-ttu-id="36831-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> указывает, имеет ли экземпляр типа, допускающего значение NULL, значение своего базового типа.</span><span class="sxs-lookup"><span data-stu-id="36831-117"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>

- <span data-ttu-id="36831-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> возвращает значение базового типа, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="36831-118"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="36831-119">Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, свойство <xref:System.Nullable%601.Value%2A> выдает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="36831-119">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="36831-120">В коде в следующем примере используется свойство `HasValue`, чтобы проверить, содержит ли переменная значение, перед его отображением:</span><span class="sxs-lookup"><span data-stu-id="36831-120">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

<span data-ttu-id="36831-121">Вы также можете сравнить переменную типа значения, допускающего значение NULL, с `null` вместо использования свойства `HasValue`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="36831-121">You also can compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="36831-122">Начиная с версии C# 7.0 для проверки и получения значения типа значения, допускающего значение NULL, можно использовать [сопоставление шаблонов](../../pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="36831-122">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable value type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="36831-123">Преобразование из типа значения, допускающего значение NULL, в базовый тип</span><span class="sxs-lookup"><span data-stu-id="36831-123">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="36831-124">Если вам нужно присвоить значение типа значения, допускающего значение NULL, типу, не допускающему значение NULL, используйте [оператор объединения с NULL`??`](../../language-reference/operators/null-coalescing-operator.md), чтобы указать значение для присваивания, если значение типа значения, допускающего значение NULL, равно NULL (вы также можете использовать метод <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>):</span><span class="sxs-lookup"><span data-stu-id="36831-124">If you need to assign a value of a nullable value type to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a value of a nullable value type is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="36831-125">Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа значения, допускающего значение NULL, равно `null`, должно быть значением по умолчанию базового типа.</span><span class="sxs-lookup"><span data-stu-id="36831-125">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a value of a nullable value type is `null` should be the default value of the underlying value type.</span></span>

<span data-ttu-id="36831-126">Вы можете явно привести тип значения, допускающий значение NULL, к типу, не допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="36831-126">You can explicitly cast a nullable value type to a non-nullable type.</span></span> <span data-ttu-id="36831-127">Например:</span><span class="sxs-lookup"><span data-stu-id="36831-127">For example:</span></span>

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="36831-128">Во время выполнения, если значение типа значения, допускающего значение NULL, равно `null`, явное приведение вызывает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="36831-128">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="36831-129">Тип, не допускающий значение NULL, неявно преобразуется в соответствующий тип, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="36831-129">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>

## <a name="operators"></a><span data-ttu-id="36831-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="36831-130">Operators</span></span>

<span data-ttu-id="36831-131">Предопределенные унарные и бинарные операторы, а также любые операторы, определенные программистом, которые существуют для типов значений, также можно использовать и с соответствующими типами, допускающими значение NULL.</span><span class="sxs-lookup"><span data-stu-id="36831-131">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by corresponding nullable types.</span></span> <span data-ttu-id="36831-132">Эти операторы возвращают значение `null`, если один или оба операнда имеют значение `null`. В противном случае оператор использует содержащиеся значения для вычисления результата.</span><span class="sxs-lookup"><span data-stu-id="36831-132">These operators produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="36831-133">Например:</span><span class="sxs-lookup"><span data-stu-id="36831-133">For example:</span></span>

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> <span data-ttu-id="36831-134">Для типа `bool?` предопределенные операторы `&` и `|` не следуют правилам, описанным в этом разделе: результат вычисления оператора может быть отличным от NULL, даже если один из операндов имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="36831-134">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="36831-135">См. подробнее о [логических операторах, поддерживающих значение NULL](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](../../language-reference/operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="36831-135">For more information, see the [Nullable Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../../language-reference/operators/boolean-logical-operators.md) article.</span></span>
  
<span data-ttu-id="36831-136">Для операторов отношения (`<`, `>`, `<=`, `>=`), если один или оба операнда имеют значение `null`, результатом будет `false`.</span><span class="sxs-lookup"><span data-stu-id="36831-136">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are `null`, the result is `false`.</span></span> <span data-ttu-id="36831-137">Тут важно не полагать, что если какая-то операция сравнения (например, `<=`) возвращает `false`, то противоположное сравнение (`>`) обязательно вернет `true`.</span><span class="sxs-lookup"><span data-stu-id="36831-137">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="36831-138">В следующем примере показано, что 10</span><span class="sxs-lookup"><span data-stu-id="36831-138">The following example shows that 10 is</span></span>

- <span data-ttu-id="36831-139">не больше и не равно значению `null`,</span><span class="sxs-lookup"><span data-stu-id="36831-139">neither greater than or equal to `null`,</span></span>
- <span data-ttu-id="36831-140">не меньше чем `null`.</span><span class="sxs-lookup"><span data-stu-id="36831-140">nor less than `null`.</span></span>

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

<span data-ttu-id="36831-141">В приведенном выше примере видно, что проверка на равенство двух типов значения, допускающих значение NULL, которые оба равны NULL, всегда даст `true`.</span><span class="sxs-lookup"><span data-stu-id="36831-141">The above example also shows that an equality comparison of two nullable value types that are both null evaluates to `true`.</span></span>

<span data-ttu-id="36831-142">Дополнительные сведения см. в разделе о [поднятых операторах](~/_csharplang/spec/expressions.md#lifted-operators) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="36831-142">For more information, see the [Lifted operators](~/_csharplang/spec/expressions.md#lifted-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="36831-143">Упаковка-преобразование и распаковка-преобразование</span><span class="sxs-lookup"><span data-stu-id="36831-143">Boxing and unboxing</span></span>

<span data-ttu-id="36831-144">Тип, допускающий значение NULL, [упакован](../types/boxing-and-unboxing.md) по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="36831-144">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="36831-145">Если <xref:System.Nullable%601.HasValue%2A> возвращает `false`, создается пустая ссылка.</span><span class="sxs-lookup"><span data-stu-id="36831-145">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="36831-146">Если <xref:System.Nullable%601.HasValue%2A> возвращает `true`, упаковывается значение базового типа `T`, а не экземпляр <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="36831-146">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="36831-147">Можно распаковать упакованный тип значения в соответствующий тип, допускающий значение NULL, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="36831-147">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a><span data-ttu-id="36831-148">См. также</span><span class="sxs-lookup"><span data-stu-id="36831-148">See also</span></span>

- [<span data-ttu-id="36831-149">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="36831-149">Nullable value types</span></span>](index.md)
- <span data-ttu-id="36831-150">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Что означает термин "расширенные"?)</span><span class="sxs-lookup"><span data-stu-id="36831-150">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)</span></span>
