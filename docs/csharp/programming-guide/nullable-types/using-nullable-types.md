---
title: "Использование допускающих значение NULL типов (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c8a42392bbcd2e53c54ff4c13bf98c048262ae4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="4c489-102">Использование допускающих значение NULL типов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4c489-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="4c489-103">Типы, допускающие значение NULL, могут представлять все значения своего основного типа, а также само значение [NULL](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="4c489-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="4c489-104">Типы, допускающие значение null, объявляются одним из следующих двух способов:</span><span class="sxs-lookup"><span data-stu-id="4c489-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="4c489-105">-или-</span><span class="sxs-lookup"><span data-stu-id="4c489-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="4c489-106">`T` — это основной тип для типа, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="4c489-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="4c489-107">`T` может быть значением любого типа, включая `struct`, но не ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="4c489-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="4c489-108">В качестве примера того, когда можно использовать тип, допускающий значение null, рассмотрим обычную переменную типа Boolean, которая может иметь два значения: true и false.</span><span class="sxs-lookup"><span data-stu-id="4c489-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="4c489-109">У этого типа нет значения, обозначающего "не определено".</span><span class="sxs-lookup"><span data-stu-id="4c489-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="4c489-110">Во многих приложениях, в первую очередь взаимодействующих с базами данных, переменные могут оказаться в неопределенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="4c489-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="4c489-111">Например, поле в базе данных может содержать значение true или false, но оно также может вообще не содержать никакого значения.</span><span class="sxs-lookup"><span data-stu-id="4c489-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="4c489-112">Подобным образом для ссылочных типов можно установить значение `null`, чтобы обозначить тот факт, что они не инициализированы.</span><span class="sxs-lookup"><span data-stu-id="4c489-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="4c489-113">Это несоответствие может создавать лишнюю работу по программированию, в частности, приводить к использованию дополнительных переменных для хранения информации о состоянии, применению специальных значений, и т. п.</span><span class="sxs-lookup"><span data-stu-id="4c489-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="4c489-114">Модификатор, указывающий, что данный тип допускает значения null, позволяет в языке C# создавать переменные значащего типа, позволяющие указывать для них неопределенное значение.</span><span class="sxs-lookup"><span data-stu-id="4c489-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="4c489-115">Примеры типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="4c489-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="4c489-116">Любой значащий тип может использоваться как основной для типа, допускающего значение null.</span><span class="sxs-lookup"><span data-stu-id="4c489-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="4c489-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="4c489-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="4c489-118">Члены типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="4c489-118">The Members of Nullable Types</span></span>  
 <span data-ttu-id="4c489-119">Каждый объект типа, допускающего значение null, имеет два открытых свойства, доступных только для чтения:</span><span class="sxs-lookup"><span data-stu-id="4c489-119">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="4c489-120">`HasValue` имеет тип `bool`.</span><span class="sxs-lookup"><span data-stu-id="4c489-120">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="4c489-121">Для него устанавливается значение `true`, если переменная содержит значение, не равное NULL.</span><span class="sxs-lookup"><span data-stu-id="4c489-121">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="4c489-122">`Value` имеет тот же тип, что и базовый тип.</span><span class="sxs-lookup"><span data-stu-id="4c489-122">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="4c489-123">Если `HasValue` равно `true`, то свойство `Value` содержит полезное значение.</span><span class="sxs-lookup"><span data-stu-id="4c489-123">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="4c489-124">Если `HasValue` имеет значение `false`, доступ к свойству `Value` вызовет исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="4c489-124">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="4c489-125">В этом примере член `HasValue` используется для проверки того, содержит ли переменная какое-либо значение, прежде чем пытаться его показать.</span><span class="sxs-lookup"><span data-stu-id="4c489-125">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 <span data-ttu-id="4c489-126">Проверку на наличие полезного значения можно также выполнить, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4c489-126">Testing for a value can also be done as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a><span data-ttu-id="4c489-127">Явные преобразования</span><span class="sxs-lookup"><span data-stu-id="4c489-127">Explicit Conversions</span></span>  
 <span data-ttu-id="4c489-128">Тип, допускающий значение NULL, может быть приведен к своему основному типу либо явно, путем приведения типа, либо при помощи свойства `Value`.</span><span class="sxs-lookup"><span data-stu-id="4c489-128">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="4c489-129">Пример:</span><span class="sxs-lookup"><span data-stu-id="4c489-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 <span data-ttu-id="4c489-130">Если между двумя типами данных определено пользовательское преобразование типов, то это же преобразование можно также использовать с версиями этих типов, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="4c489-130">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="4c489-131">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="4c489-131">Implicit Conversions</span></span>  
 <span data-ttu-id="4c489-132">Для переменной типа, допускающего значение NULL, можно установить значение NULL с помощью ключевого слова `null`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4c489-132">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 <span data-ttu-id="4c489-133">Преобразование из обычного типа в тип, допускающий значение null, является неявным.</span><span class="sxs-lookup"><span data-stu-id="4c489-133">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a><span data-ttu-id="4c489-134">Операторы</span><span class="sxs-lookup"><span data-stu-id="4c489-134">Operators</span></span>  
 <span data-ttu-id="4c489-135">Предопределенные унарные и бинарные операции, а также любые операции, определенные программистом, которые существуют для значащих типов, также можно использовать и с типами, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="4c489-135">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="4c489-136">Эти операции возвращают значение null, если операнды имеют значение null; в противном случае операция использует содержащееся значение для вычисления результата.</span><span class="sxs-lookup"><span data-stu-id="4c489-136">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="4c489-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="4c489-137">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 <span data-ttu-id="4c489-138">Если при сравнении с допускающими значение NULL типами значение одного из таких типов равно NULL, а второй тип содержит другое значение, то результатом сравнения всегда является `false` , за исключением использования оператора `!=` (не равно).</span><span class="sxs-lookup"><span data-stu-id="4c489-138">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="4c489-139">Тут важно не полагать, что если какая-то операция сравнения возвращает `false`, то противоположная ей операция обязательно вернет `true`.</span><span class="sxs-lookup"><span data-stu-id="4c489-139">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="4c489-140">В следующем примере число 10 не больше, не меньше и не равно null.</span><span class="sxs-lookup"><span data-stu-id="4c489-140">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="4c489-141">Только `num1 != num2` даст `true`.</span><span class="sxs-lookup"><span data-stu-id="4c489-141">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 <span data-ttu-id="4c489-142">Проверка на равенство двух типов, допускающих значение NULL, которые оба равны NULL, всегда даст `true`.</span><span class="sxs-lookup"><span data-stu-id="4c489-142">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="4c489-143">??</span><span class="sxs-lookup"><span data-stu-id="4c489-143">The ??</span></span> <span data-ttu-id="4c489-144">Оператор</span><span class="sxs-lookup"><span data-stu-id="4c489-144">Operator</span></span>  
 <span data-ttu-id="4c489-145">Оператор `??` определяет значение по умолчанию, которое используется, когда значение типа, допускающего NULL, присваивается значению типа, не допускающего NULL.</span><span class="sxs-lookup"><span data-stu-id="4c489-145">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 <span data-ttu-id="4c489-146">Эту операцию также можно использовать с несколькими значениями типа, допускающего null.</span><span class="sxs-lookup"><span data-stu-id="4c489-146">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="4c489-147">Пример:</span><span class="sxs-lookup"><span data-stu-id="4c489-147">For example:</span></span>  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a><span data-ttu-id="4c489-148">Тип bool?</span><span class="sxs-lookup"><span data-stu-id="4c489-148">The bool? type</span></span>  
 <span data-ttu-id="4c489-149">Тип `bool?`, допускающий значение NULL, может содержать три разных значения: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) и [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="4c489-149">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="4c489-150">Сведения о приведении bool? к bool см. в разделе [Практическое руководство. Безопасное приведение bool? к bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="4c489-150">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="4c489-151">Тип Boolean, допускающий значение null, подобен типу Boolean в SQL.</span><span class="sxs-lookup"><span data-stu-id="4c489-151">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="4c489-152">Чтобы убедиться, что результаты операторов `&` и `|` согласуются с трехзначным типом Boolean в SQL, предусмотрены следующие предопределенные операторы:</span><span class="sxs-lookup"><span data-stu-id="4c489-152">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="4c489-153">Результаты этих операций приведены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="4c489-153">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="4c489-154">X</span><span class="sxs-lookup"><span data-stu-id="4c489-154">X</span></span>|<span data-ttu-id="4c489-155">y</span><span class="sxs-lookup"><span data-stu-id="4c489-155">y</span></span>|<span data-ttu-id="4c489-156">x&y</span><span class="sxs-lookup"><span data-stu-id="4c489-156">x&y</span></span>|<span data-ttu-id="4c489-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="4c489-157">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="4c489-158">true</span><span class="sxs-lookup"><span data-stu-id="4c489-158">true</span></span>|<span data-ttu-id="4c489-159">true</span><span class="sxs-lookup"><span data-stu-id="4c489-159">true</span></span>|<span data-ttu-id="4c489-160">true</span><span class="sxs-lookup"><span data-stu-id="4c489-160">true</span></span>|<span data-ttu-id="4c489-161">true</span><span class="sxs-lookup"><span data-stu-id="4c489-161">true</span></span>|  
|<span data-ttu-id="4c489-162">true</span><span class="sxs-lookup"><span data-stu-id="4c489-162">true</span></span>|<span data-ttu-id="4c489-163">false</span><span class="sxs-lookup"><span data-stu-id="4c489-163">false</span></span>|<span data-ttu-id="4c489-164">false</span><span class="sxs-lookup"><span data-stu-id="4c489-164">false</span></span>|<span data-ttu-id="4c489-165">true</span><span class="sxs-lookup"><span data-stu-id="4c489-165">true</span></span>|  
|<span data-ttu-id="4c489-166">true</span><span class="sxs-lookup"><span data-stu-id="4c489-166">true</span></span>|<span data-ttu-id="4c489-167">null</span><span class="sxs-lookup"><span data-stu-id="4c489-167">null</span></span>|<span data-ttu-id="4c489-168">null</span><span class="sxs-lookup"><span data-stu-id="4c489-168">null</span></span>|<span data-ttu-id="4c489-169">true</span><span class="sxs-lookup"><span data-stu-id="4c489-169">true</span></span>|  
|<span data-ttu-id="4c489-170">false</span><span class="sxs-lookup"><span data-stu-id="4c489-170">false</span></span>|<span data-ttu-id="4c489-171">true</span><span class="sxs-lookup"><span data-stu-id="4c489-171">true</span></span>|<span data-ttu-id="4c489-172">false</span><span class="sxs-lookup"><span data-stu-id="4c489-172">false</span></span>|<span data-ttu-id="4c489-173">true</span><span class="sxs-lookup"><span data-stu-id="4c489-173">true</span></span>|  
|<span data-ttu-id="4c489-174">false</span><span class="sxs-lookup"><span data-stu-id="4c489-174">false</span></span>|<span data-ttu-id="4c489-175">false</span><span class="sxs-lookup"><span data-stu-id="4c489-175">false</span></span>|<span data-ttu-id="4c489-176">false</span><span class="sxs-lookup"><span data-stu-id="4c489-176">false</span></span>|<span data-ttu-id="4c489-177">false</span><span class="sxs-lookup"><span data-stu-id="4c489-177">false</span></span>|  
|<span data-ttu-id="4c489-178">false</span><span class="sxs-lookup"><span data-stu-id="4c489-178">false</span></span>|<span data-ttu-id="4c489-179">null</span><span class="sxs-lookup"><span data-stu-id="4c489-179">null</span></span>|<span data-ttu-id="4c489-180">false</span><span class="sxs-lookup"><span data-stu-id="4c489-180">false</span></span>|<span data-ttu-id="4c489-181">null</span><span class="sxs-lookup"><span data-stu-id="4c489-181">null</span></span>|  
|<span data-ttu-id="4c489-182">null</span><span class="sxs-lookup"><span data-stu-id="4c489-182">null</span></span>|<span data-ttu-id="4c489-183">true</span><span class="sxs-lookup"><span data-stu-id="4c489-183">true</span></span>|<span data-ttu-id="4c489-184">null</span><span class="sxs-lookup"><span data-stu-id="4c489-184">null</span></span>|<span data-ttu-id="4c489-185">true</span><span class="sxs-lookup"><span data-stu-id="4c489-185">true</span></span>|  
|<span data-ttu-id="4c489-186">null</span><span class="sxs-lookup"><span data-stu-id="4c489-186">null</span></span>|<span data-ttu-id="4c489-187">false</span><span class="sxs-lookup"><span data-stu-id="4c489-187">false</span></span>|<span data-ttu-id="4c489-188">false</span><span class="sxs-lookup"><span data-stu-id="4c489-188">false</span></span>|<span data-ttu-id="4c489-189">null</span><span class="sxs-lookup"><span data-stu-id="4c489-189">null</span></span>|  
|<span data-ttu-id="4c489-190">null</span><span class="sxs-lookup"><span data-stu-id="4c489-190">null</span></span>|<span data-ttu-id="4c489-191">null</span><span class="sxs-lookup"><span data-stu-id="4c489-191">null</span></span>|<span data-ttu-id="4c489-192">null</span><span class="sxs-lookup"><span data-stu-id="4c489-192">null</span></span>|<span data-ttu-id="4c489-193">null</span><span class="sxs-lookup"><span data-stu-id="4c489-193">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c489-194">См. также</span><span class="sxs-lookup"><span data-stu-id="4c489-194">See Also</span></span>  
 [<span data-ttu-id="4c489-195">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4c489-195">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4c489-196">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="4c489-196">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="4c489-197">Упаковка-преобразование типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="4c489-197">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [<span data-ttu-id="4c489-198">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="4c489-198">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
