---
title: Типы значения, допускающие Null (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8734114b9d657066a0ef0b2d648f0290c03b1cbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="d04d0-102">Типы значения, допускающие Null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d04d0-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="d04d0-103">Иногда пользователь работает с типом значения, не имеет определенного значения в определенных обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="d04d0-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="d04d0-104">Например поле в базе данных может потребоваться различать наличие присвоенного значения, имеет смысл и отсутствие присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="d04d0-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="d04d0-105">Типы значений можно расширить выполнить обычные значения или значение null.</span><span class="sxs-lookup"><span data-stu-id="d04d0-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="d04d0-106">Такое расширение называется *обнуляемый*.</span><span class="sxs-lookup"><span data-stu-id="d04d0-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="d04d0-107">Каждый тип nullable создается на основе универсального <xref:System.Nullable%601> структуры.</span><span class="sxs-lookup"><span data-stu-id="d04d0-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="d04d0-108">Рассмотрим базу данных, отслеживающий должностных обязанностей.</span><span class="sxs-lookup"><span data-stu-id="d04d0-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="d04d0-109">В следующем примере создается допускающему значение NULL `Boolean` введите и объявляется переменная этого типа.</span><span class="sxs-lookup"><span data-stu-id="d04d0-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="d04d0-110">Можно написать объявление тремя способами:</span><span class="sxs-lookup"><span data-stu-id="d04d0-110">You can write the declaration in three ways:</span></span>  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 <span data-ttu-id="d04d0-111">Переменная `ridesBusToWork` может содержать значение `True`, значение `False`, или без значения.</span><span class="sxs-lookup"><span data-stu-id="d04d0-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="d04d0-112">Его начальное значение по умолчанию имеет никакого смысла, который в этом случае может означать, что данные не еще были получены для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d04d0-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="d04d0-113">Напротив `False` может означать, что данные были получены лицо не велосипеде шины для работы.</span><span class="sxs-lookup"><span data-stu-id="d04d0-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="d04d0-114">Можно объявить переменные и свойства с типами nullable, и можно объявить массив элементов типа nullable.</span><span class="sxs-lookup"><span data-stu-id="d04d0-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="d04d0-115">Можно объявить процедуру с типами nullable в качестве параметров, и может возвращать тип nullable из `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="d04d0-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="d04d0-116">Не удается создать тип nullable для ссылочного типа, такого как массив, `String`, или класс.</span><span class="sxs-lookup"><span data-stu-id="d04d0-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="d04d0-117">Базовый тип должен быть типом значения.</span><span class="sxs-lookup"><span data-stu-id="d04d0-117">The underlying type must be a value type.</span></span> <span data-ttu-id="d04d0-118">Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="d04d0-118">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="d04d0-119">С помощью переменной типа значения NULL</span><span class="sxs-lookup"><span data-stu-id="d04d0-119">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="d04d0-120">Наиболее важные члены типа nullable являются его <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="d04d0-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="d04d0-121">Для переменной типа nullable <xref:System.Nullable%601.HasValue%2A> указывает, содержит ли переменная определенное значение.</span><span class="sxs-lookup"><span data-stu-id="d04d0-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="d04d0-122">Если <xref:System.Nullable%601.HasValue%2A> — `True`, можно считать значение из <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="d04d0-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="d04d0-123">Обратите внимание, что оба <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> , `ReadOnly` свойства.</span><span class="sxs-lookup"><span data-stu-id="d04d0-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="d04d0-124">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d04d0-124">Default Values</span></span>  
 <span data-ttu-id="d04d0-125">При объявлении переменной с типом nullable его <xref:System.Nullable%601.HasValue%2A> свойство имеет значение по умолчанию `False`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="d04d0-126">Это означает, что по умолчанию переменная не имеет заданного значения, вместо значения по умолчанию значение базового типа.</span><span class="sxs-lookup"><span data-stu-id="d04d0-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="d04d0-127">В следующем примере переменная `numberOfChildren` изначально не имеет заданного значения, даже если значение по умолчанию `Integer` тип равен 0.</span><span class="sxs-lookup"><span data-stu-id="d04d0-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 <span data-ttu-id="d04d0-128">Значение null полезно для обнаружения неопределенного или неизвестного значения.</span><span class="sxs-lookup"><span data-stu-id="d04d0-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="d04d0-129">Если `numberOfChildren` значения были объявлены как `Integer`, будет не значение, которое может указывать, что данные еще не доступных в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="d04d0-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="d04d0-130">Сохранение значений</span><span class="sxs-lookup"><span data-stu-id="d04d0-130">Storing Values</span></span>  
 <span data-ttu-id="d04d0-131">Сохраните значение в переменную или свойство типа nullable обычным образом.</span><span class="sxs-lookup"><span data-stu-id="d04d0-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="d04d0-132">Следующий пример присваивает значение переменной `numberOfChildren` объявленного в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="d04d0-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 <span data-ttu-id="d04d0-133">Если переменная или свойство типа nullable содержит определенное значение, вы можете вызвать для возврата к исходному состоянию отсутствия назначенное значение.</span><span class="sxs-lookup"><span data-stu-id="d04d0-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="d04d0-134">Это можно сделать, задав переменную или свойство `Nothing`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d04d0-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="d04d0-135">Несмотря на то, что можно назначить `Nothing` переменной типа nullable, нельзя проверить ее `Nothing` с помощью знака равенства.</span><span class="sxs-lookup"><span data-stu-id="d04d0-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="d04d0-136">Сравнение, в котором используется знак равенства, `someVar = Nothing`, всегда равно `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="d04d0-137">Можно проверить переменную <xref:System.Nullable%601.HasValue%2A> свойство `False`, или проверить с помощью `Is` или `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="d04d0-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="d04d0-138">Получение значений</span><span class="sxs-lookup"><span data-stu-id="d04d0-138">Retrieving Values</span></span>  
 <span data-ttu-id="d04d0-139">Чтобы получить значение переменной типа nullable, сначала следует проверить его <xref:System.Nullable%601.HasValue%2A> свойство, чтобы убедиться, что он имеет значение.</span><span class="sxs-lookup"><span data-stu-id="d04d0-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="d04d0-140">При попытке прочитать значение при <xref:System.Nullable%601.HasValue%2A> — `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] вызывает <xref:System.InvalidOperationException> исключение.</span><span class="sxs-lookup"><span data-stu-id="d04d0-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="d04d0-141">В следующем примере показано рекомендуемый способ чтения переменной `numberOfChildren` из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="d04d0-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="d04d0-142">Сравнение типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="d04d0-142">Comparing Nullable Types</span></span>  
 <span data-ttu-id="d04d0-143">Если значения NULL `Boolean` переменные используются в логических выражениях, результат может быть `True`, `False`, или `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="d04d0-144">Ниже приведена таблица истинности для `And` и `Or`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="d04d0-145">Поскольку `b1` и `b2` теперь имеют три возможных значения, существует девять комбинаций для оценки.</span><span class="sxs-lookup"><span data-stu-id="d04d0-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="d04d0-146">B1</span><span class="sxs-lookup"><span data-stu-id="d04d0-146">b1</span></span>|<span data-ttu-id="d04d0-147">В2</span><span class="sxs-lookup"><span data-stu-id="d04d0-147">b2</span></span>|<span data-ttu-id="d04d0-148">B1 и В2</span><span class="sxs-lookup"><span data-stu-id="d04d0-148">b1 And b2</span></span>|<span data-ttu-id="d04d0-149">B1 или В2</span><span class="sxs-lookup"><span data-stu-id="d04d0-149">b1 Or b2</span></span>|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 <span data-ttu-id="d04d0-150">Если значение логической переменной или выражения равно `Nothing`, он не является ни `true` , ни `false`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="d04d0-151">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="d04d0-151">Consider the following example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 <span data-ttu-id="d04d0-152">В этом примере `b1 And b2` равен `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="d04d0-153">В результате `Else` предложение выполняется в каждом `If` инструкции и вывод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d04d0-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  <span data-ttu-id="d04d0-154">`AndAlso`и `OrElse`, которые используют сокращенные вычисления, должны оценивать свои вторые операнды при первой, результатом которого является `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="d04d0-155">Распространение</span><span class="sxs-lookup"><span data-stu-id="d04d0-155">Propagation</span></span>  
 <span data-ttu-id="d04d0-156">Если один или оба операнда арифметические, сравнения, shift или тип операции, допускающие значение NULL, результат операции также допускает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d04d0-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="d04d0-157">Если оба операнда имеют значения, которые не являются `Nothing`, операция выполняется на основных значениях операндов, как если бы ни был тип nullable.</span><span class="sxs-lookup"><span data-stu-id="d04d0-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="d04d0-158">В следующем примере переменные `compare1` и `sum1` неявным.</span><span class="sxs-lookup"><span data-stu-id="d04d0-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="d04d0-159">При наведении указателя мыши над ними вы увидите, что компилятор выводит для них типы, допускающие значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d04d0-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 <span data-ttu-id="d04d0-160">Если один или оба операнда имеют значение `Nothing`, это приведет к появлению `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d04d0-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="d04d0-161">Использование допускающих значение NULL типов с данными</span><span class="sxs-lookup"><span data-stu-id="d04d0-161">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="d04d0-162">Базы данных является одним из наиболее важных местах использовать типы, допускающие значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d04d0-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="d04d0-163">Не все объекты базы данных в настоящее время поддерживает типы, допускающие значение NULL, но адаптеры таблицы, автоматически созданный конструктором.</span><span class="sxs-lookup"><span data-stu-id="d04d0-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="d04d0-164">В разделе «Поддержки адаптера таблицы для типов, допускающих значение NULL» [Общие сведения о TableAdapter](/visualstudio/data-tools/tableadapter-overview).</span><span class="sxs-lookup"><span data-stu-id="d04d0-164">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](/visualstudio/data-tools/tableadapter-overview).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d04d0-165">См. также</span><span class="sxs-lookup"><span data-stu-id="d04d0-165">See Also</span></span>  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [<span data-ttu-id="d04d0-166">Использование допускающих значение NULL типов</span><span class="sxs-lookup"><span data-stu-id="d04d0-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="d04d0-167">Типы данных</span><span class="sxs-lookup"><span data-stu-id="d04d0-167">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="d04d0-168">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="d04d0-168">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="d04d0-169">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="d04d0-169">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="d04d0-170">Общие сведения об адаптере таблиц</span><span class="sxs-lookup"><span data-stu-id="d04d0-170">TableAdapter Overview</span></span>](/visualstudio/data-tools/tableadapter-overview)  
 [<span data-ttu-id="d04d0-171">Оператор If</span><span class="sxs-lookup"><span data-stu-id="d04d0-171">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="d04d0-172">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="d04d0-172">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="d04d0-173">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="d04d0-173">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="d04d0-174">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="d04d0-174">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
