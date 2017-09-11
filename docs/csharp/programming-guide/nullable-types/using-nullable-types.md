---
title: "Использование допускающих значение NULL типов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0721d9f60abc4e158135d6b050953b3e63ab8cb5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-nullable-types-c-programming-guide"></a><span data-ttu-id="a153a-102">Использование допускающих значение NULL типов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a153a-102">Using Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="a153a-103">Типы, допускающие значение NULL, могут представлять все значения своего основного типа, а также само значение [NULL](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="a153a-103">Nullable types can represent all the values of an underlying type, and an additional [null](../../../csharp/language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="a153a-104">Типы, допускающие значение null, объявляются одним из следующих двух способов:</span><span class="sxs-lookup"><span data-stu-id="a153a-104">Nullable types are declared in one of two ways:</span></span>  
  
 `System.Nullable<T> variable`  
  
 <span data-ttu-id="a153a-105">-или-</span><span class="sxs-lookup"><span data-stu-id="a153a-105">-or-</span></span>  
  
 `T? variable`  
  
 <span data-ttu-id="a153a-106">`T` — это основной тип для типа, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a153a-106">`T` is the underlying type of the nullable type.</span></span> <span data-ttu-id="a153a-107">`T` может быть значением любого типа, включая `struct`, но не ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="a153a-107">`T` can be any value type including `struct`; it cannot be a reference type.</span></span>  
  
 <span data-ttu-id="a153a-108">В качестве примера того, когда можно использовать тип, допускающий значение null, рассмотрим обычную переменную типа Boolean, которая может иметь два значения: true и false.</span><span class="sxs-lookup"><span data-stu-id="a153a-108">For an example of when you might use a nullable type, consider how an ordinary Boolean variable can have two values: true and false.</span></span> <span data-ttu-id="a153a-109">У этого типа нет значения, обозначающего "не определено".</span><span class="sxs-lookup"><span data-stu-id="a153a-109">There is no value that signifies "undefined".</span></span> <span data-ttu-id="a153a-110">Во многих приложениях, в первую очередь взаимодействующих с базами данных, переменные могут оказаться в неопределенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="a153a-110">In many programming applications, most notably database interactions, variables can occur in an undefined state.</span></span> <span data-ttu-id="a153a-111">Например, поле в базе данных может содержать значение true или false, но оно также может вообще не содержать никакого значения.</span><span class="sxs-lookup"><span data-stu-id="a153a-111">For example, a field in a database may contain the values true or false, but it may also contain no value at all.</span></span> <span data-ttu-id="a153a-112">Подобным образом для ссылочных типов можно установить значение `null`, чтобы обозначить тот факт, что они не инициализированы.</span><span class="sxs-lookup"><span data-stu-id="a153a-112">Similarly, reference types can be set to `null` to indicate that they are not initialized.</span></span>  
  
 <span data-ttu-id="a153a-113">Это несоответствие может создавать лишнюю работу по программированию, в частности, приводить к использованию дополнительных переменных для хранения информации о состоянии, применению специальных значений, и т. п.</span><span class="sxs-lookup"><span data-stu-id="a153a-113">This disparity can create extra programming work, with additional variables used to store state information, the use of special values, and so on.</span></span> <span data-ttu-id="a153a-114">Модификатор, указывающий, что данный тип допускает значения null, позволяет в языке C# создавать переменные значащего типа, позволяющие указывать для них неопределенное значение.</span><span class="sxs-lookup"><span data-stu-id="a153a-114">The nullable type modifier enables C# to create value-type variables that indicate an undefined value.</span></span>  
  
## <a name="examples-of-nullable-types"></a><span data-ttu-id="a153a-115">Примеры типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="a153a-115">Examples of Nullable Types</span></span>  
 <span data-ttu-id="a153a-116">Любой значащий тип может использоваться как основной для типа, допускающего значение null.</span><span class="sxs-lookup"><span data-stu-id="a153a-116">Any value type may be used as the basis for a nullable type.</span></span> <span data-ttu-id="a153a-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="a153a-117">For example:</span></span>  
  
 <span data-ttu-id="a153a-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-118">[!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]</span></span>  
  
## <a name="the-members-of-nullable-types"></a><span data-ttu-id="a153a-119">Члены типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="a153a-119">The Members of Nullable Types</span></span>  
 <span data-ttu-id="a153a-120">Каждый объект типа, допускающего значение null, имеет два открытых свойства, доступных только для чтения:</span><span class="sxs-lookup"><span data-stu-id="a153a-120">Each instance of a nullable type has two public read-only properties:</span></span>  
  
-   `HasValue`  
  
     <span data-ttu-id="a153a-121">`HasValue` имеет тип `bool`.</span><span class="sxs-lookup"><span data-stu-id="a153a-121">`HasValue` is of type `bool`.</span></span> <span data-ttu-id="a153a-122">Для него устанавливается значение `true`, если переменная содержит значение, не равное NULL.</span><span class="sxs-lookup"><span data-stu-id="a153a-122">It is set to `true` when the variable contains a non-null value.</span></span>  
  
-   `Value`  
  
     <span data-ttu-id="a153a-123">`Value` имеет тот же тип, что и базовый тип.</span><span class="sxs-lookup"><span data-stu-id="a153a-123">`Value` is of the same type as the underlying type.</span></span> <span data-ttu-id="a153a-124">Если `HasValue` равно `true`, то свойство `Value` содержит полезное значение.</span><span class="sxs-lookup"><span data-stu-id="a153a-124">If `HasValue` is `true`, `Value` contains a meaningful value.</span></span> <span data-ttu-id="a153a-125">Если `HasValue` имеет значение `false`, доступ к свойству `Value` вызовет исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="a153a-125">If `HasValue` is `false`, accessing `Value` will throw a <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="a153a-126">В этом примере член `HasValue` используется для проверки того, содержит ли переменная какое-либо значение, прежде чем пытаться его показать.</span><span class="sxs-lookup"><span data-stu-id="a153a-126">In this example, the `HasValue` member is used to test whether the variable contains a value before it tries to display it.</span></span>  
  
 <span data-ttu-id="a153a-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-127">[!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]</span></span>  
  
 <span data-ttu-id="a153a-128">Проверку на наличие полезного значения можно также выполнить, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a153a-128">Testing for a value can also be done as in the following example:</span></span>  
  
 <span data-ttu-id="a153a-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-129">[!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]</span></span>  
  
## <a name="explicit-conversions"></a><span data-ttu-id="a153a-130">Явные преобразования</span><span class="sxs-lookup"><span data-stu-id="a153a-130">Explicit Conversions</span></span>  
 <span data-ttu-id="a153a-131">Тип, допускающий значение NULL, может быть приведен к своему основному типу либо явно, путем приведения типа, либо при помощи свойства `Value`.</span><span class="sxs-lookup"><span data-stu-id="a153a-131">A nullable type can be cast to a regular type, either explicitly with a cast, or by using the `Value` property.</span></span> <span data-ttu-id="a153a-132">Например:</span><span class="sxs-lookup"><span data-stu-id="a153a-132">For example:</span></span>  
  
 <span data-ttu-id="a153a-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-133">[!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]</span></span>  
  
 <span data-ttu-id="a153a-134">Если между двумя типами данных определено пользовательское преобразование типов, то это же преобразование можно также использовать с версиями этих типов, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="a153a-134">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="a153a-135">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="a153a-135">Implicit Conversions</span></span>  
 <span data-ttu-id="a153a-136">Для переменной типа, допускающего значение NULL, можно установить значение NULL с помощью ключевого слова `null`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a153a-136">A variable of nullable type can be set to null with the `null` keyword, as shown in the following example:</span></span>  
  
 <span data-ttu-id="a153a-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-137">[!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]</span></span>  
  
 <span data-ttu-id="a153a-138">Преобразование из обычного типа в тип, допускающий значение null, является неявным.</span><span class="sxs-lookup"><span data-stu-id="a153a-138">The conversion from an ordinary type to a nullable type, is implicit.</span></span>  
  
 <span data-ttu-id="a153a-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-139">[!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]</span></span>  
  
## <a name="operators"></a><span data-ttu-id="a153a-140">Операторы</span><span class="sxs-lookup"><span data-stu-id="a153a-140">Operators</span></span>  
 <span data-ttu-id="a153a-141">Предопределенные унарные и бинарные операции, а также любые операции, определенные программистом, которые существуют для значащих типов, также можно использовать и с типами, допускающими значение null.</span><span class="sxs-lookup"><span data-stu-id="a153a-141">The predefined unary and binary operators and any user-defined operators that exist for value types may also be used by nullable types.</span></span> <span data-ttu-id="a153a-142">Эти операции возвращают значение null, если операнды имеют значение null; в противном случае операция использует содержащееся значение для вычисления результата.</span><span class="sxs-lookup"><span data-stu-id="a153a-142">These operators produce a null value if the operands are null; otherwise, the operator uses the contained value to calculate the result.</span></span> <span data-ttu-id="a153a-143">Например:</span><span class="sxs-lookup"><span data-stu-id="a153a-143">For example:</span></span>  
  
 <span data-ttu-id="a153a-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-144">[!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]</span></span>  
  
 <span data-ttu-id="a153a-145">Если при сравнении с допускающими значение NULL типами значение одного из таких типов равно NULL, а второй тип содержит другое значение, то результатом сравнения всегда является `false` , за исключением использования оператора `!=` (не равно).</span><span class="sxs-lookup"><span data-stu-id="a153a-145">When you perform comparisons with nullable types, if the value of one of the nullable types is null and the other is not, all comparisons evaluate to `false` except for `!=` (not equal).</span></span> <span data-ttu-id="a153a-146">Тут важно не полагать, что если какая-то операция сравнения возвращает `false`, то противоположная ей операция обязательно вернет `true`.</span><span class="sxs-lookup"><span data-stu-id="a153a-146">It is important not to assume that because a particular comparison returns `false`, the opposite case returns `true`.</span></span> <span data-ttu-id="a153a-147">В следующем примере число 10 не больше, не меньше и не равно null.</span><span class="sxs-lookup"><span data-stu-id="a153a-147">In the following example, 10 is not greater than, less than, nor equal to null.</span></span> <span data-ttu-id="a153a-148">Только `num1 != num2` даст `true`.</span><span class="sxs-lookup"><span data-stu-id="a153a-148">Only `num1 != num2` evaluates to `true`.</span></span>  
  
 <span data-ttu-id="a153a-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-149">[!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]</span></span>  
  
 <span data-ttu-id="a153a-150">Проверка на равенство двух типов, допускающих значение NULL, которые оба равны NULL, всегда даст `true`.</span><span class="sxs-lookup"><span data-stu-id="a153a-150">An equality comparison of two nullable types that are both null evaluates to `true`.</span></span>  
  
## <a name="the--operator"></a><span data-ttu-id="a153a-151">??</span><span class="sxs-lookup"><span data-stu-id="a153a-151">The ??</span></span> <span data-ttu-id="a153a-152">Оператор</span><span class="sxs-lookup"><span data-stu-id="a153a-152">Operator</span></span>  
 <span data-ttu-id="a153a-153">Оператор `??` определяет значение по умолчанию, которое используется, когда значение типа, допускающего NULL, присваивается значению типа, не допускающего NULL.</span><span class="sxs-lookup"><span data-stu-id="a153a-153">The `??` operator defines a default value that is returned when a nullable type is assigned to a non-nullable type.</span></span>  
  
 <span data-ttu-id="a153a-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-154">[!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]</span></span>  
  
 <span data-ttu-id="a153a-155">Эту операцию также можно использовать с несколькими значениями типа, допускающего null.</span><span class="sxs-lookup"><span data-stu-id="a153a-155">This operator can also be used with multiple nullable types.</span></span> <span data-ttu-id="a153a-156">Например:</span><span class="sxs-lookup"><span data-stu-id="a153a-156">For example:</span></span>  
  
 <span data-ttu-id="a153a-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="a153a-157">[!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]</span></span>  
  
## <a name="the-bool-type"></a><span data-ttu-id="a153a-158">Тип bool?</span><span class="sxs-lookup"><span data-stu-id="a153a-158">The bool? type</span></span>  
 <span data-ttu-id="a153a-159">Тип `bool?`, допускающий значение NULL, может содержать три разных значения: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) и [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="a153a-159">The `bool?` nullable type can contain three different values: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) and [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="a153a-160">Сведения о приведении bool? к bool см. в разделе [Практическое руководство. Безопасное приведение bool? к bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span><span class="sxs-lookup"><span data-stu-id="a153a-160">For information about how to cast from a bool? to a bool, see [How to: Safely Cast from bool? to bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).</span></span>  
  
 <span data-ttu-id="a153a-161">Тип Boolean, допускающий значение null, подобен типу Boolean в SQL.</span><span class="sxs-lookup"><span data-stu-id="a153a-161">Nullable Booleans are like the Boolean variable type that is used in SQL.</span></span> <span data-ttu-id="a153a-162">Чтобы убедиться, что результаты операторов `&` и `|` согласуются с трехзначным типом Boolean в SQL, предусмотрены следующие предопределенные операторы:</span><span class="sxs-lookup"><span data-stu-id="a153a-162">To ensure that the results produced by the `&` and `|` operators are consistent with the three-valued Boolean type in SQL, the following predefined operators are provided:</span></span>  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 <span data-ttu-id="a153a-163">Результаты этих операций приведены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="a153a-163">The results of these operators are listed in the following table:</span></span>  
  
|<span data-ttu-id="a153a-164">X</span><span class="sxs-lookup"><span data-stu-id="a153a-164">X</span></span>|<span data-ttu-id="a153a-165">y</span><span class="sxs-lookup"><span data-stu-id="a153a-165">y</span></span>|<span data-ttu-id="a153a-166">x&y</span><span class="sxs-lookup"><span data-stu-id="a153a-166">x&y</span></span>|<span data-ttu-id="a153a-167">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="a153a-167">x&#124;y</span></span>|  
|-------|-------|---------|--------------|  
|<span data-ttu-id="a153a-168">true</span><span class="sxs-lookup"><span data-stu-id="a153a-168">true</span></span>|<span data-ttu-id="a153a-169">true</span><span class="sxs-lookup"><span data-stu-id="a153a-169">true</span></span>|<span data-ttu-id="a153a-170">true</span><span class="sxs-lookup"><span data-stu-id="a153a-170">true</span></span>|<span data-ttu-id="a153a-171">true</span><span class="sxs-lookup"><span data-stu-id="a153a-171">true</span></span>|  
|<span data-ttu-id="a153a-172">true</span><span class="sxs-lookup"><span data-stu-id="a153a-172">true</span></span>|<span data-ttu-id="a153a-173">false</span><span class="sxs-lookup"><span data-stu-id="a153a-173">false</span></span>|<span data-ttu-id="a153a-174">false</span><span class="sxs-lookup"><span data-stu-id="a153a-174">false</span></span>|<span data-ttu-id="a153a-175">true</span><span class="sxs-lookup"><span data-stu-id="a153a-175">true</span></span>|  
|<span data-ttu-id="a153a-176">true</span><span class="sxs-lookup"><span data-stu-id="a153a-176">true</span></span>|<span data-ttu-id="a153a-177">null</span><span class="sxs-lookup"><span data-stu-id="a153a-177">null</span></span>|<span data-ttu-id="a153a-178">null</span><span class="sxs-lookup"><span data-stu-id="a153a-178">null</span></span>|<span data-ttu-id="a153a-179">true</span><span class="sxs-lookup"><span data-stu-id="a153a-179">true</span></span>|  
|<span data-ttu-id="a153a-180">false</span><span class="sxs-lookup"><span data-stu-id="a153a-180">false</span></span>|<span data-ttu-id="a153a-181">true</span><span class="sxs-lookup"><span data-stu-id="a153a-181">true</span></span>|<span data-ttu-id="a153a-182">false</span><span class="sxs-lookup"><span data-stu-id="a153a-182">false</span></span>|<span data-ttu-id="a153a-183">true</span><span class="sxs-lookup"><span data-stu-id="a153a-183">true</span></span>|  
|<span data-ttu-id="a153a-184">false</span><span class="sxs-lookup"><span data-stu-id="a153a-184">false</span></span>|<span data-ttu-id="a153a-185">false</span><span class="sxs-lookup"><span data-stu-id="a153a-185">false</span></span>|<span data-ttu-id="a153a-186">false</span><span class="sxs-lookup"><span data-stu-id="a153a-186">false</span></span>|<span data-ttu-id="a153a-187">false</span><span class="sxs-lookup"><span data-stu-id="a153a-187">false</span></span>|  
|<span data-ttu-id="a153a-188">false</span><span class="sxs-lookup"><span data-stu-id="a153a-188">false</span></span>|<span data-ttu-id="a153a-189">null</span><span class="sxs-lookup"><span data-stu-id="a153a-189">null</span></span>|<span data-ttu-id="a153a-190">false</span><span class="sxs-lookup"><span data-stu-id="a153a-190">false</span></span>|<span data-ttu-id="a153a-191">null</span><span class="sxs-lookup"><span data-stu-id="a153a-191">null</span></span>|  
|<span data-ttu-id="a153a-192">null</span><span class="sxs-lookup"><span data-stu-id="a153a-192">null</span></span>|<span data-ttu-id="a153a-193">true</span><span class="sxs-lookup"><span data-stu-id="a153a-193">true</span></span>|<span data-ttu-id="a153a-194">null</span><span class="sxs-lookup"><span data-stu-id="a153a-194">null</span></span>|<span data-ttu-id="a153a-195">true</span><span class="sxs-lookup"><span data-stu-id="a153a-195">true</span></span>|  
|<span data-ttu-id="a153a-196">null</span><span class="sxs-lookup"><span data-stu-id="a153a-196">null</span></span>|<span data-ttu-id="a153a-197">false</span><span class="sxs-lookup"><span data-stu-id="a153a-197">false</span></span>|<span data-ttu-id="a153a-198">false</span><span class="sxs-lookup"><span data-stu-id="a153a-198">false</span></span>|<span data-ttu-id="a153a-199">null</span><span class="sxs-lookup"><span data-stu-id="a153a-199">null</span></span>|  
|<span data-ttu-id="a153a-200">null</span><span class="sxs-lookup"><span data-stu-id="a153a-200">null</span></span>|<span data-ttu-id="a153a-201">null</span><span class="sxs-lookup"><span data-stu-id="a153a-201">null</span></span>|<span data-ttu-id="a153a-202">null</span><span class="sxs-lookup"><span data-stu-id="a153a-202">null</span></span>|<span data-ttu-id="a153a-203">null</span><span class="sxs-lookup"><span data-stu-id="a153a-203">null</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a153a-204">См. также</span><span class="sxs-lookup"><span data-stu-id="a153a-204">See Also</span></span>  
 <span data-ttu-id="a153a-205">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a153a-205">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a153a-206">[Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="a153a-206">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 <span data-ttu-id="a153a-207">[Упаковка-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span><span class="sxs-lookup"><span data-stu-id="a153a-207">[Boxing Nullable Types](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md) </span></span>  
 [<span data-ttu-id="a153a-208">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="a153a-208">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)

