---
title: Типы значений, допускающие значение NULL
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249686"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="85384-102">Типы значения, допускающие Null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85384-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="85384-103">Иногда вы работаете с типом значения, который не имеет определенного значения в определенных обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="85384-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="85384-104">Например, поле в базе данных может иметь различие между наличием значимого значения и не имеющим назначенного значения.</span><span class="sxs-lookup"><span data-stu-id="85384-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="85384-105">Типы значений могут быть расширены, чтобы взять либо их нормальные значения, либо нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="85384-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="85384-106">Такое расширение называется *недействительным типом.*</span><span class="sxs-lookup"><span data-stu-id="85384-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="85384-107">Каждый недействительный тип значения <xref:System.Nullable%601> построен из общей структуры.</span><span class="sxs-lookup"><span data-stu-id="85384-107">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="85384-108">Рассмотрим базу данных, которая отслеживает действия, связанные с работой.</span><span class="sxs-lookup"><span data-stu-id="85384-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="85384-109">Следующий пример строит недействительный `Boolean` тип и объявляет переменную этого типа.</span><span class="sxs-lookup"><span data-stu-id="85384-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="85384-110">Заявление можно написать тремя способами:</span><span class="sxs-lookup"><span data-stu-id="85384-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="85384-111">Переменная `ridesBusToWork` может содержать `True`значение, `False`значение, или нет значения вообще.</span><span class="sxs-lookup"><span data-stu-id="85384-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="85384-112">Его начальное значение по умолчанию не является значением вообще, что в этом случае может означать, что информация еще не была получена для этого человека.</span><span class="sxs-lookup"><span data-stu-id="85384-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="85384-113">В отличие `False` от этого, может означать, что информация была получена, и человек не едет на автобусе на работу.</span><span class="sxs-lookup"><span data-stu-id="85384-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="85384-114">Вы можете декларировать переменные и свойства с необыдательными типами значений, а также объявлять массив с элементами необдуманного типа значения.</span><span class="sxs-lookup"><span data-stu-id="85384-114">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="85384-115">В качестве параметров можно объявить процедуры с необыдаными типами значений, а также вернуть из `Function` процедуры несоизглаенный тип значения.</span><span class="sxs-lookup"><span data-stu-id="85384-115">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="85384-116">Вы не можете построить недействительный тип на `String`типе ссылки, например массив, a или класс.</span><span class="sxs-lookup"><span data-stu-id="85384-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="85384-117">Базовым типом должен быть тип значения.</span><span class="sxs-lookup"><span data-stu-id="85384-117">The underlying type must be a value type.</span></span> <span data-ttu-id="85384-118">Для получения дополнительной информации [см.](value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="85384-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="85384-119">Использование переменной nullable Типа</span><span class="sxs-lookup"><span data-stu-id="85384-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="85384-120">Наиболее важными членами несоизлучаемого типа значения являются его <xref:System.Nullable%601.HasValue%2A> свойства и <xref:System.Nullable%601.Value%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="85384-120">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="85384-121">Для переменной необнутивной тип <xref:System.Nullable%601.HasValue%2A> значения, показывает, содержит ли переменная определенное значение.</span><span class="sxs-lookup"><span data-stu-id="85384-121">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="85384-122">Если <xref:System.Nullable%601.HasValue%2A> `True`это, вы можете <xref:System.Nullable%601.Value%2A>прочитать значение от .</span><span class="sxs-lookup"><span data-stu-id="85384-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="85384-123">Обратите внимание, <xref:System.Nullable%601.Value%2A> `ReadOnly` что оба <xref:System.Nullable%601.HasValue%2A> свойства и являются свойствами.</span><span class="sxs-lookup"><span data-stu-id="85384-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="85384-124">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="85384-124">Default Values</span></span>

<span data-ttu-id="85384-125">Когда вы объявляете переменную с необыдательным типом значения, ее <xref:System.Nullable%601.HasValue%2A> свойство имеет значение по `False`умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85384-125">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="85384-126">Это означает, что по умолчанию переменная не имеет определенного значения, а не значение по умолчанию своего базового типа значения.</span><span class="sxs-lookup"><span data-stu-id="85384-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="85384-127">В следующем примере `numberOfChildren` переменная изначально не имеет определенного значения, даже если значение `Integer` типа по умолчанию составляет 0.</span><span class="sxs-lookup"><span data-stu-id="85384-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="85384-128">Нулевое значение полезно для обозначения неопределенного или неизвестного значения.</span><span class="sxs-lookup"><span data-stu-id="85384-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="85384-129">Если `numberOfChildren` бы было `Integer`объявлено, не было бы значения, которое могло бы указывать на то, что информация в настоящее время недоступна.</span><span class="sxs-lookup"><span data-stu-id="85384-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="85384-130">Хранение ценностей</span><span class="sxs-lookup"><span data-stu-id="85384-130">Storing Values</span></span>

<span data-ttu-id="85384-131">Вы храните значение в переменной или свойстве нулевого типа значения типичным способом.</span><span class="sxs-lookup"><span data-stu-id="85384-131">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="85384-132">Следующий пример присваивает `numberOfChildren` значение переменной, заявленной в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="85384-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="85384-133">Если переменная или свойство нулевого типа значения содержит определенное значение, вы можете заставить ее вернуться к исходному состоянию, не имеющего значения, назначенного.</span><span class="sxs-lookup"><span data-stu-id="85384-133">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="85384-134">Вы делаете это, устанавливая `Nothing`переменную или свойство, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="85384-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="85384-135">Хотя вы можете `Nothing` назначить переменную нулевого типа значения, `Nothing` вы не можете проверить его с помощью равного знака.</span><span class="sxs-lookup"><span data-stu-id="85384-135">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="85384-136">Сравнение, которое `someVar = Nothing`использует равный `Nothing`знак, всегда оценивает .</span><span class="sxs-lookup"><span data-stu-id="85384-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="85384-137">Вы <xref:System.Nullable%601.HasValue%2A> можете проверить свойство `False`переменной для, `Is` или `IsNot` проверить с помощью оператора.</span><span class="sxs-lookup"><span data-stu-id="85384-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="85384-138">Получение значений</span><span class="sxs-lookup"><span data-stu-id="85384-138">Retrieving Values</span></span>

<span data-ttu-id="85384-139">Чтобы получить значение переменной нулевой типа значения, необходимо сначала <xref:System.Nullable%601.HasValue%2A> проверить ее свойство, чтобы подтвердить, что она имеет значение.</span><span class="sxs-lookup"><span data-stu-id="85384-139">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="85384-140">Если вы попытаетесь <xref:System.Nullable%601.HasValue%2A> прочитать значение, когда это, `False`Visual Basic бросает <xref:System.InvalidOperationException> исключение.</span><span class="sxs-lookup"><span data-stu-id="85384-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="85384-141">Ниже приводится рекомендуемый способ чтения `numberOfChildren` переменной предыдущих примеров.</span><span class="sxs-lookup"><span data-stu-id="85384-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="85384-142">Сравнение недействительных типов</span><span class="sxs-lookup"><span data-stu-id="85384-142">Comparing Nullable Types</span></span>

<span data-ttu-id="85384-143">Когда недействительные `Boolean` переменные используются в выражениях `True`Boolean, результат может быть, `False`или `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="85384-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="85384-144">Ниже приведена таблица `And` `Or`правды для и .</span><span class="sxs-lookup"><span data-stu-id="85384-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="85384-145">Потому что `b1` и `b2` теперь есть три возможных значения, Есть девять комбинаций для оценки.</span><span class="sxs-lookup"><span data-stu-id="85384-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="85384-146">b1</span><span class="sxs-lookup"><span data-stu-id="85384-146">b1</span></span>|<span data-ttu-id="85384-147">B2</span><span class="sxs-lookup"><span data-stu-id="85384-147">b2</span></span>|<span data-ttu-id="85384-148">b1 И b2</span><span class="sxs-lookup"><span data-stu-id="85384-148">b1 And b2</span></span>|<span data-ttu-id="85384-149">b1 Или b2</span><span class="sxs-lookup"><span data-stu-id="85384-149">b1 Or b2</span></span>|
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

<span data-ttu-id="85384-150">Когда значение переменной Boolean или `Nothing`выражения, `true` это `false`не является ни .</span><span class="sxs-lookup"><span data-stu-id="85384-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="85384-151">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="85384-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="85384-152">В этом `b1 And b2` примере `Nothing`оценивается.</span><span class="sxs-lookup"><span data-stu-id="85384-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="85384-153">В результате `Else` положение выполняется в `If` каждом заявлении, и вывод следующий:</span><span class="sxs-lookup"><span data-stu-id="85384-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="85384-154">`AndAlso`и `OrElse`, которые используют оценку короткого замыкания, должны оценить `Nothing`свои вторые оперы, когда первый оценивает .</span><span class="sxs-lookup"><span data-stu-id="85384-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="85384-155">Распространение</span><span class="sxs-lookup"><span data-stu-id="85384-155">Propagation</span></span>

<span data-ttu-id="85384-156">Если одна или обе операции арифметики, сравнения, переноса или типа являются необоснованной типом значения, результат операции также является необоснованной типом значения.</span><span class="sxs-lookup"><span data-stu-id="85384-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="85384-157">Если оба операции имеют значения, которые `Nothing`не являются, операция выполняется на основных значениях operands, как если бы ни один из них не был необоснованного типа значения.</span><span class="sxs-lookup"><span data-stu-id="85384-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="85384-158">В следующем примере `compare1` переменные и `sum1` неявно набраны.</span><span class="sxs-lookup"><span data-stu-id="85384-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="85384-159">Если вы полежите указателем мыши над ними, вы увидите, что компилятор вычеркивает недействительные типы значений для обоих из них.</span><span class="sxs-lookup"><span data-stu-id="85384-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="85384-160">Если один или оба operands `Nothing`имеют значение, `Nothing`результат будет .</span><span class="sxs-lookup"><span data-stu-id="85384-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="85384-161">Использование недействительных типов с данными</span><span class="sxs-lookup"><span data-stu-id="85384-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="85384-162">База данных является одним из наиболее важных мест для использования недействительных типов значений.</span><span class="sxs-lookup"><span data-stu-id="85384-162">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="85384-163">В настоящее время не все объекты базы данных поддерживают необнудаемые типы значений, но адаптеры таблиц, созданные дизайнером, поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="85384-163">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="85384-164">Смотрите [поддержку TableAdapter для недействительных типов.](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)</span><span class="sxs-lookup"><span data-stu-id="85384-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="85384-165">См. также</span><span class="sxs-lookup"><span data-stu-id="85384-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="85384-166">Типы данных</span><span class="sxs-lookup"><span data-stu-id="85384-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="85384-167">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="85384-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="85384-168">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="85384-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="85384-169">Заполнение наборов данных с помощью адаптеров таблицы</span><span class="sxs-lookup"><span data-stu-id="85384-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="85384-170">Оператор If</span><span class="sxs-lookup"><span data-stu-id="85384-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="85384-171">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="85384-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="85384-172">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="85384-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="85384-173">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="85384-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="85384-174">Недействительные типы значений (C)</span><span class="sxs-lookup"><span data-stu-id="85384-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
