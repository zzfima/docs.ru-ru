---
title: Типы значения, допускающие Null
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 0d259e11a969f4eb7e64626a4adf498db06ece06
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347841"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="4f3c4-102">Типы значения, допускающие Null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f3c4-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="4f3c4-103">Иногда вы работаете с типом значения, который не имеет определенного значения в определенных обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="4f3c4-104">Например, поле в базе данных может отличаться от присвоенного значения, которое является осмысленным и не имеет присвоенного значения.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="4f3c4-105">Типы значений могут быть расширены для получения их нормальных значений или значения NULL.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="4f3c4-106">Такое расширение называется *типом, допускающим значение NULL*.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="4f3c4-107">Каждый допускающий значение NULL тип создается из универсальной структуры <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="4f3c4-108">Рассмотрим базу данных, которая отслеживает действия, связанные с работой.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="4f3c4-109">В следующем примере создается тип `Boolean` Nullable и объявляется переменная этого типа.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="4f3c4-110">Объявление можно написать тремя способами:</span><span class="sxs-lookup"><span data-stu-id="4f3c4-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="4f3c4-111">Переменная `ridesBusToWork` может содержать значение `True`, значение `False`или вообще не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="4f3c4-112">Его начальное значение по умолчанию — вообще не имеет значения, что в данном случае может означать, что данные еще не были получены для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="4f3c4-113">В отличие от этого, `False` может означать, что информация была получена, и пользователь не перейдет на шину.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="4f3c4-114">Можно объявить переменные и свойства с типами, допускающими значение null, и можно объявить массив с элементами типа, допускающего значение null.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="4f3c4-115">В качестве параметров можно объявить процедуры с типами, допускающими значение null, и можно вернуть тип, допускающий значение null, из процедуры `Function`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="4f3c4-116">Нельзя создать тип, допускающий значение null, для ссылочного типа, такого как массив, `String`или класс.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="4f3c4-117">Базовый тип должен быть типом значения.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-117">The underlying type must be a value type.</span></span> <span data-ttu-id="4f3c4-118">Для получения дополнительной информации см. [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="4f3c4-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="4f3c4-119">Использование переменной типа, допускающей значение null</span><span class="sxs-lookup"><span data-stu-id="4f3c4-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="4f3c4-120">Наиболее важными членами типа, допускающего значение null, являются свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="4f3c4-121">Для переменной типа, допускающего значение null, <xref:System.Nullable%601.HasValue%2A> сообщает, содержит ли переменная определенное значение.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="4f3c4-122">Если <xref:System.Nullable%601.HasValue%2A> `True`, можно прочитать значение из <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="4f3c4-123">Обратите внимание, что свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="4f3c4-124">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4f3c4-124">Default Values</span></span>

<span data-ttu-id="4f3c4-125">При объявлении переменной с типом, допускающим значение null, ее свойство <xref:System.Nullable%601.HasValue%2A> имеет значение по умолчанию `False`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="4f3c4-126">Это означает, что по умолчанию переменная не имеет определенного значения, а не значения по умолчанию базового типа значения.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="4f3c4-127">В следующем примере переменная `numberOfChildren` изначально не имеет определенного значения, несмотря на то, что значение по умолчанию для типа `Integer` равно 0.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="4f3c4-128">Значение NULL полезно для указания неопределенного или неизвестного значения.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="4f3c4-129">Если `numberOfChildren` было объявлено как `Integer`, то не будет значения, которое могло бы означать, что информация в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="4f3c4-130">Сохранение значений</span><span class="sxs-lookup"><span data-stu-id="4f3c4-130">Storing Values</span></span>

<span data-ttu-id="4f3c4-131">Вы сохраняете значение в переменной или свойстве типа, допускающего значение null, обычным способом.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="4f3c4-132">В следующем примере значение присваивается переменной, `numberOfChildren` объявленной в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="4f3c4-133">Если переменная или свойство типа, допускающего значение null, содержит определенное значение, можно вернуть его первоначальное состояние, не имеющее присвоенного значения.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="4f3c4-134">Для этого нужно задать для переменной или свойства значение `Nothing`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="4f3c4-135">Хотя можно присвоить `Nothing` переменной типа, допускающего значение null, ее нельзя протестировать для `Nothing` с помощью знака равенства.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="4f3c4-136">При сравнении, в котором используется знак равенства, `someVar = Nothing`, всегда вычисляется `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="4f3c4-137">Можно проверить свойство <xref:System.Nullable%601.HasValue%2A> переменной для `False`или проверить с помощью оператора `Is` или `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="4f3c4-138">Получение значений</span><span class="sxs-lookup"><span data-stu-id="4f3c4-138">Retrieving Values</span></span>

<span data-ttu-id="4f3c4-139">Чтобы получить значение переменной типа, допускающего значение null, сначала следует проверить его свойство <xref:System.Nullable%601.HasValue%2A>, чтобы убедиться, что оно имеет значение.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="4f3c4-140">Если попытаться считать значение, когда <xref:System.Nullable%601.HasValue%2A> `False`, Visual Basic выдаст исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="4f3c4-141">В следующем примере показан рекомендуемый способ чтения переменной `numberOfChildren` из предыдущих примеров.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="4f3c4-142">Сравнение типов, допускающих значение null</span><span class="sxs-lookup"><span data-stu-id="4f3c4-142">Comparing Nullable Types</span></span>

<span data-ttu-id="4f3c4-143">Если в логических выражениях используются значения NULL `Boolean` переменные, результат может быть `True`, `False`или `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="4f3c4-144">Ниже приведена таблица истинности для `And` и `Or`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="4f3c4-145">Поскольку `b1` и `b2` теперь имеют три возможных значения, можно вычислить девять комбинаций.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="4f3c4-146">B1</span><span class="sxs-lookup"><span data-stu-id="4f3c4-146">b1</span></span>|<span data-ttu-id="4f3c4-147">ячейк</span><span class="sxs-lookup"><span data-stu-id="4f3c4-147">b2</span></span>|<span data-ttu-id="4f3c4-148">B1 и B2</span><span class="sxs-lookup"><span data-stu-id="4f3c4-148">b1 And b2</span></span>|<span data-ttu-id="4f3c4-149">B1 или B2</span><span class="sxs-lookup"><span data-stu-id="4f3c4-149">b1 Or b2</span></span>|
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

<span data-ttu-id="4f3c4-150">Если значение логической переменной или выражения `Nothing`, оно не является ни `true`, ни `false`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="4f3c4-151">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="4f3c4-152">В этом примере `b1 And b2` вычисляется как `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="4f3c4-153">В результате предложение `Else` выполняется в каждой инструкции `If`, и выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4f3c4-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="4f3c4-154">`AndAlso` и `OrElse`, которые используют сокращенную оценку, должны оценивать свои вторые операнды, когда первый вычисляется как `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="4f3c4-155">Распространение</span><span class="sxs-lookup"><span data-stu-id="4f3c4-155">Propagation</span></span>

<span data-ttu-id="4f3c4-156">Если один или оба операнда арифметических операций, операции сравнения, сдвига или типа допускают значение null, результат операции также может допускать значение null.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="4f3c4-157">Если оба операнда имеют значения, которые не `Nothing`, операция выполняется с базовыми значениями операндов, как если бы ни был тип, допускающий значение null.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="4f3c4-158">В следующем примере переменные `compare1` и `sum1` неявно типизированы.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="4f3c4-159">Если навести на них указатель мыши, вы увидите, что компилятор выводит типы, допускающие значение null, для обоих типов.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="4f3c4-160">Если один или оба операнда имеют значение `Nothing`, результат будет `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="4f3c4-161">Использование типов, допускающих значение null, с данными</span><span class="sxs-lookup"><span data-stu-id="4f3c4-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="4f3c4-162">База данных является одним из наиболее важных мест для использования типов, допускающих значение null.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="4f3c4-163">Не все объекты базы данных в настоящее время поддерживают типы, допускающие значение null, но адаптеры таблиц, созданные конструктором, выполняют.</span><span class="sxs-lookup"><span data-stu-id="4f3c4-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="4f3c4-164">См. раздел [Поддержка TableAdapter для типов, допускающих значение NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="4f3c4-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f3c4-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f3c4-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="4f3c4-166">Типы данных</span><span class="sxs-lookup"><span data-stu-id="4f3c4-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="4f3c4-167">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="4f3c4-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="4f3c4-168">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="4f3c4-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="4f3c4-169">Заполнение наборов данных с помощью адаптера таблицы</span><span class="sxs-lookup"><span data-stu-id="4f3c4-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="4f3c4-170">Оператор If</span><span class="sxs-lookup"><span data-stu-id="4f3c4-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="4f3c4-171">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="4f3c4-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="4f3c4-172">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="4f3c4-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="4f3c4-173">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="4f3c4-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="4f3c4-174">Типы значений, допускающие значение null (C#)</span><span class="sxs-lookup"><span data-stu-id="4f3c4-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
