---
title: Использование допускающих значение NULL типов (руководство по программированию на C#)
description: Узнайте, как в C# использовать типы, допускающие значение NULL
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 9c9ab5c3ca1dd49f011bf9c980945fa9da0d8cfc
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148357"
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="41442-103">Использование допускающих значение NULL типов (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="41442-103">Using nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="41442-104">Типы, допускающие значение NULL, могут представлять все значения своего базового типа `T`, а также дополнительное значение [NULL](../../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="41442-104">Nullable types are types that represent all the values of an underlying value type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="41442-105">Дополнительные сведения см. в разделе [Типы, допускающие значение NULL](index.md).</span><span class="sxs-lookup"><span data-stu-id="41442-105">For more information, see the [Nullable types](index.md) topic.</span></span>

<span data-ttu-id="41442-106">Вы можете ссылаться на тип, допускающий значение NULL, в любой из следующих форм: `Nullable<T>` или `T?`.</span><span class="sxs-lookup"><span data-stu-id="41442-106">You can refer to a nullable type in any of the following forms: `Nullable<T>` or `T?`.</span></span> <span data-ttu-id="41442-107">Эти две формы записи являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="41442-107">These two forms are interchangeable.</span></span>  
  
## <a name="declaration-and-assignment"></a><span data-ttu-id="41442-108">Назначение и объявление</span><span class="sxs-lookup"><span data-stu-id="41442-108">Declaration and assignment</span></span>

<span data-ttu-id="41442-109">Поскольку тип значения может быть неявно преобразован в соответствующий тип, допускающий значение NULL, вы назначаете значение такому типу так же, как его базовому типу значения.</span><span class="sxs-lookup"><span data-stu-id="41442-109">As a value type can be implicitly converted to the corresponding nullable type, you assign a value to a nullable type as you would for its underlying value type.</span></span> <span data-ttu-id="41442-110">Вы также можете присвоить значение `null`.</span><span class="sxs-lookup"><span data-stu-id="41442-110">You also can assign the `null` value.</span></span>  <span data-ttu-id="41442-111">Например:</span><span class="sxs-lookup"><span data-stu-id="41442-111">For example:</span></span>
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a><span data-ttu-id="41442-112">Изучение значение типа, допускающего значение NULL</span><span class="sxs-lookup"><span data-stu-id="41442-112">Examination of a nullable type value</span></span>

<span data-ttu-id="41442-113">Используйте следующие свойства только для чтения, чтобы изучить экземпляр типа, допускающего значение NULL, со значением NULL и извлечь значение базового типа:</span><span class="sxs-lookup"><span data-stu-id="41442-113">Use the following readonly properties to examine an instance of a nullable type for null and retrieve a value of an underlying type:</span></span>  
  
- <span data-ttu-id="41442-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> указывает, имеет ли экземпляр типа, допускающего значение NULL, значение своего базового типа.</span><span class="sxs-lookup"><span data-stu-id="41442-114"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable type has a value of its underlying type.</span></span>
  
- <span data-ttu-id="41442-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> возвращает значение базового типа, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="41442-115"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="41442-116">Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, свойство <xref:System.Nullable%601.Value%2A> выдает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="41442-116">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>
  
<span data-ttu-id="41442-117">В коде в следующем примере используется свойство `HasValue`, чтобы проверить, содержит ли переменная значение, перед его отображением:</span><span class="sxs-lookup"><span data-stu-id="41442-117">The code in the following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
<span data-ttu-id="41442-118">Вы также можете сравнить тип, допускающий значение NULL, с `null` вместо использования свойства `HasValue`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41442-118">You also can compare a nullable type variable with `null` instead of using the `HasValue` property, as the following example shows:</span></span>  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

<span data-ttu-id="41442-119">Начиная с версии C# 7.0 для проверки и получения значения типа, допускающего значение NULL, можно использовать [сопоставление шаблонов](../../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="41442-119">Beginning with C# 7.0, you can use [pattern matching](../../pattern-matching.md) to both examine and get a value of a nullable type:</span></span>

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a><span data-ttu-id="41442-120">Преобразование из типа, допускающего значение NULL, в базовый тип</span><span class="sxs-lookup"><span data-stu-id="41442-120">Conversion from a nullable type to an underlying type</span></span>

<span data-ttu-id="41442-121">Если вам нужно присвоить значение типа, допускающего значение NULL, типу, не допускающему значение NULL, используйте [оператор объединения с NULL`??`](../../language-reference/operators/null-coalescing-operator.md), чтобы указать значение для присваивания, если значение типа, допускающего значение NULL, равно NULL (вы также можете использовать метод <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>):</span><span class="sxs-lookup"><span data-stu-id="41442-121">If you need to assign a nullable type value to a non-nullable type, use the [null-coalescing operator `??`](../../language-reference/operators/null-coalescing-operator.md) to specify the value to be assigned if a nullable type value is null (you also can use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method to do that):</span></span>
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

<span data-ttu-id="41442-122">Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа, допускающего значение NULL, равно NULL, должно быть значением по умолчанию базового типа.</span><span class="sxs-lookup"><span data-stu-id="41442-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is null should be the default value of the underlying value type.</span></span>
  
<span data-ttu-id="41442-123">Вы можете явно привести тип, допускающий значение NULL, к типу, не допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="41442-123">You can explicitly cast a nullable type to a non-nullable type.</span></span> <span data-ttu-id="41442-124">Например:</span><span class="sxs-lookup"><span data-stu-id="41442-124">For example:</span></span>  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

<span data-ttu-id="41442-125">Во время выполнения, если значение типа, допускающего значение NULL, равно NULL, явное приведение вызывает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="41442-125">At run time, if the value of a nullable type is null, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="41442-126">Тип, не допускающий значение NULL, неявно преобразуется в соответствующий тип, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="41442-126">A non-nullable value type is implicitly converted to the corresponding nullable type.</span></span>
  
## <a name="operators"></a><span data-ttu-id="41442-127">Операторы</span><span class="sxs-lookup"><span data-stu-id="41442-127">Operators</span></span>

<span data-ttu-id="41442-128">Предопределенные унарные и бинарные операции, а также любые операции, определенные программистом, которые существуют для значащих типов, также можно использовать и с типами, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="41442-128">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="41442-129">Эти операции возвращают значение NULL, если один или оба операнда имеют значение NULL; в противном случае операция использует содержащееся значение для вычисления результата.</span><span class="sxs-lookup"><span data-stu-id="41442-129">These operators produce a null value if one or both operands are null; otherwise, the operator uses the contained values to calculate the result.</span></span> <span data-ttu-id="41442-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="41442-130">For example:</span></span>  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]
  
<span data-ttu-id="41442-131">Для операторов отношения (`<`, `>`, `<=`, `>=`), если один или оба операнда имеют значение NULL, результатом будет `false`.</span><span class="sxs-lookup"><span data-stu-id="41442-131">For the relational operators (`<`, `>`, `<=`, `>=`), if one or both operands are null, the result is `false`.</span></span> <span data-ttu-id="41442-132">Тут важно не полагать, что если какая-то операция сравнения (например, `<=`) возвращает `false`, то противоположное сравнение (`>`) обязательно вернет `true`.</span><span class="sxs-lookup"><span data-stu-id="41442-132">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="41442-133">В следующем примере показано, что 10</span><span class="sxs-lookup"><span data-stu-id="41442-133">The following example shows that 10 is</span></span>

- <span data-ttu-id="41442-134">не больше и не равно значению NULL</span><span class="sxs-lookup"><span data-stu-id="41442-134">neither greater than or equal to null,</span></span>
- <span data-ttu-id="41442-135">и не меньше, чем значение NULL.</span><span class="sxs-lookup"><span data-stu-id="41442-135">nor less than null.</span></span>
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
<span data-ttu-id="41442-136">В приведенном выше примере видно, что проверка на равенство двух типов, допускающих значение NULL, которые оба равны NULL, всегда даст `true`.</span><span class="sxs-lookup"><span data-stu-id="41442-136">The above example also shows that an equality comparison of two nullable types that are both null evaluates to `true`.</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="41442-137">Упаковка-преобразование и распаковка-преобразование</span><span class="sxs-lookup"><span data-stu-id="41442-137">Boxing and unboxing</span></span>

<span data-ttu-id="41442-138">Тип, допускающий значение NULL, [упакован](../types/boxing-and-unboxing.md) по следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="41442-138">A nullable value type is [boxed](../types/boxing-and-unboxing.md) by the following rules:</span></span>

- <span data-ttu-id="41442-139">Если <xref:System.Nullable%601.HasValue%2A> возвращает `false`, создается пустая ссылка.</span><span class="sxs-lookup"><span data-stu-id="41442-139">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>  
- <span data-ttu-id="41442-140">Если <xref:System.Nullable%601.HasValue%2A> возвращает `true`, упаковывается значение базового типа `T`, а не экземпляр <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="41442-140">If <xref:System.Nullable%601.HasValue%2A> returns `true`, a value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="41442-141">Можно распаковать упакованный тип значения в соответствующий тип, допускающий значение NULL, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="41442-141">You can unbox the boxed value type to the corresponding nullable type, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="the-bool-type"></a><span data-ttu-id="41442-142">Тип bool?</span><span class="sxs-lookup"><span data-stu-id="41442-142">The bool? type</span></span>

<span data-ttu-id="41442-143">Тип `bool?`, допускающий значение NULL, может содержать три разных значения: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) и [null](../../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="41442-143">The `bool?` nullable type can contain three different values: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md), and [null](../../language-reference/keywords/null.md).</span></span> <span data-ttu-id="41442-144">Тип `bool?` подобен типу Boolean в SQL.</span><span class="sxs-lookup"><span data-stu-id="41442-144">The `bool?` type is like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="41442-145">Чтобы убедиться, что результаты операторов `&` и `|` согласуются с трехзначным типом Boolean в SQL, предусмотрены следующие предопределенные операторы:</span><span class="sxs-lookup"><span data-stu-id="41442-145">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>

- `bool? operator &(bool? x, bool? y)`  
- `bool? operator |(bool? x, bool? y)`  
  
<span data-ttu-id="41442-146">Семантика этих операторов определяется по следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="41442-146">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="41442-147">x</span><span class="sxs-lookup"><span data-stu-id="41442-147">x</span></span>|<span data-ttu-id="41442-148">y</span><span class="sxs-lookup"><span data-stu-id="41442-148">y</span></span>|<span data-ttu-id="41442-149">x&y</span><span class="sxs-lookup"><span data-stu-id="41442-149">x&y</span></span>|<span data-ttu-id="41442-150">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="41442-150">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="41442-151">true</span><span class="sxs-lookup"><span data-stu-id="41442-151">true</span></span>|<span data-ttu-id="41442-152">true</span><span class="sxs-lookup"><span data-stu-id="41442-152">true</span></span>|<span data-ttu-id="41442-153">true</span><span class="sxs-lookup"><span data-stu-id="41442-153">true</span></span>|<span data-ttu-id="41442-154">true</span><span class="sxs-lookup"><span data-stu-id="41442-154">true</span></span>|  
|<span data-ttu-id="41442-155">true</span><span class="sxs-lookup"><span data-stu-id="41442-155">true</span></span>|<span data-ttu-id="41442-156">False</span><span class="sxs-lookup"><span data-stu-id="41442-156">false</span></span>|<span data-ttu-id="41442-157">false</span><span class="sxs-lookup"><span data-stu-id="41442-157">false</span></span>|<span data-ttu-id="41442-158">true</span><span class="sxs-lookup"><span data-stu-id="41442-158">true</span></span>|  
|<span data-ttu-id="41442-159">true</span><span class="sxs-lookup"><span data-stu-id="41442-159">true</span></span>|<span data-ttu-id="41442-160">null</span><span class="sxs-lookup"><span data-stu-id="41442-160">null</span></span>|<span data-ttu-id="41442-161">null</span><span class="sxs-lookup"><span data-stu-id="41442-161">null</span></span>|<span data-ttu-id="41442-162">true</span><span class="sxs-lookup"><span data-stu-id="41442-162">true</span></span>|  
|<span data-ttu-id="41442-163">False</span><span class="sxs-lookup"><span data-stu-id="41442-163">false</span></span>|<span data-ttu-id="41442-164">true</span><span class="sxs-lookup"><span data-stu-id="41442-164">true</span></span>|<span data-ttu-id="41442-165">False</span><span class="sxs-lookup"><span data-stu-id="41442-165">false</span></span>|<span data-ttu-id="41442-166">true</span><span class="sxs-lookup"><span data-stu-id="41442-166">true</span></span>|  
|<span data-ttu-id="41442-167">False</span><span class="sxs-lookup"><span data-stu-id="41442-167">false</span></span>|<span data-ttu-id="41442-168">False</span><span class="sxs-lookup"><span data-stu-id="41442-168">false</span></span>|<span data-ttu-id="41442-169">False</span><span class="sxs-lookup"><span data-stu-id="41442-169">false</span></span>|<span data-ttu-id="41442-170">False</span><span class="sxs-lookup"><span data-stu-id="41442-170">false</span></span>|  
|<span data-ttu-id="41442-171">False</span><span class="sxs-lookup"><span data-stu-id="41442-171">false</span></span>|<span data-ttu-id="41442-172">null</span><span class="sxs-lookup"><span data-stu-id="41442-172">null</span></span>|<span data-ttu-id="41442-173">False</span><span class="sxs-lookup"><span data-stu-id="41442-173">false</span></span>|<span data-ttu-id="41442-174">null</span><span class="sxs-lookup"><span data-stu-id="41442-174">null</span></span>|  
|<span data-ttu-id="41442-175">null</span><span class="sxs-lookup"><span data-stu-id="41442-175">null</span></span>|<span data-ttu-id="41442-176">true</span><span class="sxs-lookup"><span data-stu-id="41442-176">true</span></span>|<span data-ttu-id="41442-177">null</span><span class="sxs-lookup"><span data-stu-id="41442-177">null</span></span>|<span data-ttu-id="41442-178">true</span><span class="sxs-lookup"><span data-stu-id="41442-178">true</span></span>|  
|<span data-ttu-id="41442-179">null</span><span class="sxs-lookup"><span data-stu-id="41442-179">null</span></span>|<span data-ttu-id="41442-180">False</span><span class="sxs-lookup"><span data-stu-id="41442-180">false</span></span>|<span data-ttu-id="41442-181">False</span><span class="sxs-lookup"><span data-stu-id="41442-181">false</span></span>|<span data-ttu-id="41442-182">null</span><span class="sxs-lookup"><span data-stu-id="41442-182">null</span></span>|  
|<span data-ttu-id="41442-183">null</span><span class="sxs-lookup"><span data-stu-id="41442-183">null</span></span>|<span data-ttu-id="41442-184">null</span><span class="sxs-lookup"><span data-stu-id="41442-184">null</span></span>|<span data-ttu-id="41442-185">null</span><span class="sxs-lookup"><span data-stu-id="41442-185">null</span></span>|<span data-ttu-id="41442-186">null</span><span class="sxs-lookup"><span data-stu-id="41442-186">null</span></span>|  

<span data-ttu-id="41442-187">Обратите внимание, что эти два оператора не следуют правилам, описанным в разделе [Операторы](#operators): результат вычисления оператора может быть отличным от NULL, даже если один из операндов имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="41442-187">Note that these two operators don't follow the rules described in the [Operators](#operators) section: the result of an operator evaluation can be non-null even if one of the operands is null.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41442-188">См. также</span><span class="sxs-lookup"><span data-stu-id="41442-188">See Also</span></span>

- [<span data-ttu-id="41442-189">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="41442-189">Nullable types</span></span>](index.md)  
- [<span data-ttu-id="41442-190">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="41442-190">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- <span data-ttu-id="41442-191">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Что означает термин "расширенные"?)</span><span class="sxs-lookup"><span data-stu-id="41442-191">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)</span></span>  
