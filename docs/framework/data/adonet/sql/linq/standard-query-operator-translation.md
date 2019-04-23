---
title: Трансляция стандартных операторов запросов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: 280557a5098c513111557f52d835b20d9a2eeb62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973893"
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="ea9ee-102">Трансляция стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="ea9ee-102">Standard Query Operator Translation</span></span>

<span data-ttu-id="ea9ee-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует стандартные операторы запросов в команды SQL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="ea9ee-104">Обработчик запросов базы данных определяет семантика выполнения преобразования SQL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-104">The query processor of the database determines the execution semantics of SQL translation.</span></span>

<span data-ttu-id="ea9ee-105">Стандартные операторы запросов определяются для *последовательностей*.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-105">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="ea9ee-106">Последовательность — *упорядоченные* и основывается на идентификации ссылки для каждого элемента последовательности.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-106">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="ea9ee-107">Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) или [Обзор операторов стандартных запросов (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-107">For more information, see [Standard Query Operators Overview (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>

<span data-ttu-id="ea9ee-108">SQL занимается главным образом *неупорядоченных наборов значений*.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-108">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="ea9ee-109">Упорядочение, которое, как правило, задается явным образом, является операцией завершающей обработки, применяемой к окончательному результату запроса, а не к промежуточным результатам.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-109">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="ea9ee-110">Идентификация определяется значениями.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-110">Identity is defined by values.</span></span> <span data-ttu-id="ea9ee-111">По этой причине запросы SQL распознаются с мультинаборами (*контейнеры*) вместо *задает*.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-111">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>

<span data-ttu-id="ea9ee-112">Далее приводится описание различий между стандартными операторами запросов и их преобразованиями SQL для поставщика SQL Server для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-112">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

## <a name="operator-support"></a><span data-ttu-id="ea9ee-113">Поддержка операторов</span><span class="sxs-lookup"><span data-stu-id="ea9ee-113">Operator Support</span></span>

### <a name="concat"></a><span data-ttu-id="ea9ee-114">Concat</span><span class="sxs-lookup"><span data-stu-id="ea9ee-114">Concat</span></span>

<span data-ttu-id="ea9ee-115">Метод <xref:System.Linq.Enumerable.Concat%2A> определен для упорядоченных множественных наборов, в которых порядок получателя и аргумента совпадают.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-115">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="ea9ee-116">Метод <xref:System.Linq.Enumerable.Concat%2A> работает как предложение `UNION ALL` для мультинаборов с общим порядком.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-116"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>

<span data-ttu-id="ea9ee-117">Завершающее действие состоит в упорядочении в SQL перед возвратом результатов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-117">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="ea9ee-118">Метод <xref:System.Linq.Enumerable.Concat%2A> не сохраняет порядок своих аргументов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-118"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="ea9ee-119">Чтобы обеспечить соответствующее упорядочение, необходимо явно упорядочить результаты метода <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-119">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>

### <a name="intersect-except-union"></a><span data-ttu-id="ea9ee-120">Intersect, Except, Union</span><span class="sxs-lookup"><span data-stu-id="ea9ee-120">Intersect, Except, Union</span></span>

<span data-ttu-id="ea9ee-121">Методы <xref:System.Linq.Enumerable.Intersect%2A> и <xref:System.Linq.Enumerable.Except%2A> правильно определяются только для наборов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-121">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="ea9ee-122">Семантика для мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-122">The semantics for multisets is undefined.</span></span>

<span data-ttu-id="ea9ee-123">Метод <xref:System.Linq.Enumerable.Union%2A> определен для мультинаборов как неупорядоченное объединение мультинаборов (в действительности, он возвращает результат, аналогичный предложению UNION ALL в SQL).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-123">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>

### <a name="take-skip"></a><span data-ttu-id="ea9ee-124">Take, Skip</span><span class="sxs-lookup"><span data-stu-id="ea9ee-124">Take, Skip</span></span>

<span data-ttu-id="ea9ee-125"><xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> методы правильно определяются только для *упорядоченные наборы*.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-125"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="ea9ee-126">Семантика для неупорядоченных наборов или мультинаборов не определена.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-126">The semantics for unordered sets or multisets are undefined.</span></span>

> [!NOTE]
> <span data-ttu-id="ea9ee-127">На методы <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> накладываются некоторые ограничения при их использовании в запросах для SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-127"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="ea9ee-128">Дополнительные сведения см. в записи «"Skip и делаются исключения в SQL Server 2000» в [Устранение неполадок](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-128">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>

<span data-ttu-id="ea9ee-129">Из-за ограничений на упорядочение в SQL [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] пытается переместить упорядочение аргументов этих методов к результату метода.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-129">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="ea9ee-130">Рассмотрим, например, следующий запрос [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ea9ee-130">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

<span data-ttu-id="ea9ee-131">В созданных для этого кода командах SQL упорядочение перемещается в конец:</span><span class="sxs-lookup"><span data-stu-id="ea9ee-131">The generated SQL for this code moves the ordering to the end, as follows:</span></span>

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

<span data-ttu-id="ea9ee-132">Становится очевидным, что при объединении методов <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> все указанные операции упорядочения должны быть согласованными.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-132">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="ea9ee-133">В противном случае результаты не определены.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-133">Otherwise, the results are undefined.</span></span>

<span data-ttu-id="ea9ee-134">Методы <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> правильно определяются для неотрицательных постоянных интегральных аргументов, соответствующих спецификации стандартных операторов запросов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-134">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>

### <a name="operators-with-no-translation"></a><span data-ttu-id="ea9ee-135">Операторы без преобразования</span><span class="sxs-lookup"><span data-stu-id="ea9ee-135">Operators with No Translation</span></span>

<span data-ttu-id="ea9ee-136">Перечисленные ниже методы не преобразуются технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-136">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ea9ee-137">Причиной этого, чаще всего, является различие между неупорядоченными мультинаборами и последовательностями.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-137">The most common reason is the difference between unordered multisets and sequences.</span></span>

|<span data-ttu-id="ea9ee-138">Операторы</span><span class="sxs-lookup"><span data-stu-id="ea9ee-138">Operators</span></span>|<span data-ttu-id="ea9ee-139">Обоснование</span><span class="sxs-lookup"><span data-stu-id="ea9ee-139">Rationale</span></span>|
|---------------|---------------|
|<span data-ttu-id="ea9ee-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="ea9ee-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="ea9ee-141">SQL-запросы работают с мультинаборами и не работают с последовательностями.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-141">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="ea9ee-142">Атрибут `ORDER BY` должен быть последним предложением, применяемым к статистической функции.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-142">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="ea9ee-143">По этой причине преобразование общего назначения для этих двух методов отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-143">For this reason, there is no general-purpose translation for these two methods.</span></span>|
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="ea9ee-144">Преобразование этого метода возможно для упорядоченных наборов, однако в настоящее время он не преобразуется технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-144">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="ea9ee-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="ea9ee-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="ea9ee-146">Преобразование этих методов возможно для упорядоченных наборов, однако в настоящее время они не преобразуются технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-146">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="ea9ee-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="ea9ee-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="ea9ee-148">Запросы SQL работают с мультинаборами и не работают с индексируемыми последовательностями.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-148">SQL queries operate on multisets, not on indexable sequences.</span></span>|
|<span data-ttu-id="ea9ee-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (перегрузка с аргументом по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ea9ee-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="ea9ee-150">В общем случае значение по умолчанию для произвольного кортежа указать невозможно.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-150">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="ea9ee-151">В некоторых случаях для кортежей можно указать нулевые значения через внешние соединения.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-151">Null values for tuples are possible in some cases through outer joins.</span></span>|

## <a name="expression-translation"></a><span data-ttu-id="ea9ee-152">Преобразование выражений</span><span class="sxs-lookup"><span data-stu-id="ea9ee-152">Expression Translation</span></span>

### <a name="null-semantics"></a><span data-ttu-id="ea9ee-153">Семантика значений NULL</span><span class="sxs-lookup"><span data-stu-id="ea9ee-153">Null semantics</span></span>

<span data-ttu-id="ea9ee-154">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не накладывает семантику сравнения со значением NULL на команды SQL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-154">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="ea9ee-155">Операторы сравнения синтаксически преобразуются в эквивалентные команды SQL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-155">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="ea9ee-156">По этой причине семантика отражает семантику SQL в соответствии с параметрами сервера или подключения.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-156">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="ea9ee-157">Например два значения null считаются неравными параметры SQL Server по умолчанию, но можно изменить параметры, чтобы изменить семантику.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-157">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ea9ee-158">не учитывает параметры сервера при преобразовании запросов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-158">does not consider server settings when it translates queries.</span></span>

<span data-ttu-id="ea9ee-159">Сравнение с литералом NULL преобразуется в соответствующую версию SQL (`is null` или `is not null`).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-159">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>

<span data-ttu-id="ea9ee-160">Значение `null` в параметрах сортировки определяется SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-160">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ea9ee-161">не изменяет параметров сортировки.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-161">does not change the collation.</span></span>

### <a name="aggregates"></a><span data-ttu-id="ea9ee-162">Агрегатные выражения</span><span class="sxs-lookup"><span data-stu-id="ea9ee-162">Aggregates</span></span>

<span data-ttu-id="ea9ee-163">Агрегатный метод <xref:System.Linq.Enumerable.Sum%2A>, который входит в состав стандартных операторов запросов, выполняет сравнение с нулем для поиска пустой последовательности или последовательности, содержащей только значения NULL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-163">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="ea9ee-164">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], семантики SQL остаются без изменений, и <xref:System.Linq.Enumerable.Sum%2A> принимает значение `null` вместо нуля для пустой последовательности или последовательности, содержащей только значения NULL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>

<span data-ttu-id="ea9ee-165">Ограничения SQL для промежуточных результатов применяются к агрегатным выражениям в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-165">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ea9ee-166">Результат метода <xref:System.Linq.Enumerable.Sum%2A>, суммирующего 32-разрядные целые значения, вычисляется не на основе 64-разрядных результатов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-166">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="ea9ee-167">При преобразовании [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для метода <xref:System.Linq.Enumerable.Sum%2A> может произойти переполнение даже в том случае, если выполнение реализации стандартного оператора запроса для соответствующей последовательности в памяти не приводит к переполнению.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-167">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>

<span data-ttu-id="ea9ee-168">Аналогичным образом преобразование [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для метода <xref:System.Linq.Enumerable.Average%2A>, вычисляющего среднее значение целых чисел, возвращает тип `integer`, а не `double`.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-168">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>

### <a name="entity-arguments"></a><span data-ttu-id="ea9ee-169">Аргументы сущностей</span><span class="sxs-lookup"><span data-stu-id="ea9ee-169">Entity Arguments</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ea9ee-170">включает типы сущностей для использования в <xref:System.Linq.Enumerable.GroupBy%2A> и <xref:System.Linq.Enumerable.OrderBy%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-170">enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="ea9ee-171">При преобразовании этих операторов использование аргумента типа рассматривается как указание всех членов данного типа.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-171">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="ea9ee-172">Ниже приведены примеры эквивалентного кода.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-172">For example, the following code is equivalent:</span></span>

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a><span data-ttu-id="ea9ee-173">Сравниваемые и проверяемые на равенство аргументы</span><span class="sxs-lookup"><span data-stu-id="ea9ee-173">Equatable / Comparable Arguments</span></span>

<span data-ttu-id="ea9ee-174">Ниже перечислены методы, в реализации которых требуется равенство аргументов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-174">Equality of arguments is required in the implementation of the following methods:</span></span>

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ea9ee-175">поддерживает равенства и сравнения для *неструктурированный* аргументы, но не для аргументов, которые являются последовательностями или содержат последовательности.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-175">supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="ea9ee-176">Плоский аргумент представляет собой тип, который можно сопоставить со строкой SQL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-176">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="ea9ee-177">Проекция одного или нескольких типов сущностей, которые можно статически определить как не содержащие последовательностей, считается плоским аргументом.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-177">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>

<span data-ttu-id="ea9ee-178">Ниже представлены примеры плоских аргументов.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-178">Following are examples of flat arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

<span data-ttu-id="ea9ee-179">Ниже представлены примеры аргументов, не являющихся плоскими (иерархических аргументов).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-179">The following are examples of non-flat (hierarchical) arguments.</span></span>

[!code-csharp[DLinqSQOTranslation#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a><span data-ttu-id="ea9ee-180">Преобразование функций Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea9ee-180">Visual Basic Function Translation</span></span>

<span data-ttu-id="ea9ee-181">Ниже перечислены используемые компилятором Visual Basic вспомогательные функции, которые преобразуются в соответствующие операторы и функции SQL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-181">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

<span data-ttu-id="ea9ee-182">Методы преобразования:</span><span class="sxs-lookup"><span data-stu-id="ea9ee-182">Conversion methods:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="ea9ee-183">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="ea9ee-183">ToBoolean</span></span>|<span data-ttu-id="ea9ee-184">ToSByte</span><span class="sxs-lookup"><span data-stu-id="ea9ee-184">ToSByte</span></span>|<span data-ttu-id="ea9ee-185">ToByte</span><span class="sxs-lookup"><span data-stu-id="ea9ee-185">ToByte</span></span>|<span data-ttu-id="ea9ee-186">ToChar</span><span class="sxs-lookup"><span data-stu-id="ea9ee-186">ToChar</span></span>|
|<span data-ttu-id="ea9ee-187">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="ea9ee-187">ToCharArrayRankOne</span></span>|<span data-ttu-id="ea9ee-188">ToDate</span><span class="sxs-lookup"><span data-stu-id="ea9ee-188">ToDate</span></span>|<span data-ttu-id="ea9ee-189">ToDecimal</span><span class="sxs-lookup"><span data-stu-id="ea9ee-189">ToDecimal</span></span>|<span data-ttu-id="ea9ee-190">ToDouble</span><span class="sxs-lookup"><span data-stu-id="ea9ee-190">ToDouble</span></span>|
|<span data-ttu-id="ea9ee-191">ToInteger</span><span class="sxs-lookup"><span data-stu-id="ea9ee-191">ToInteger</span></span>|<span data-ttu-id="ea9ee-192">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="ea9ee-192">ToUInteger</span></span>|<span data-ttu-id="ea9ee-193">ToLong</span><span class="sxs-lookup"><span data-stu-id="ea9ee-193">ToLong</span></span>|<span data-ttu-id="ea9ee-194">ToULong</span><span class="sxs-lookup"><span data-stu-id="ea9ee-194">ToULong</span></span>|
|<span data-ttu-id="ea9ee-195">ToShort</span><span class="sxs-lookup"><span data-stu-id="ea9ee-195">ToShort</span></span>|<span data-ttu-id="ea9ee-196">ToUShort</span><span class="sxs-lookup"><span data-stu-id="ea9ee-196">ToUShort</span></span>|<span data-ttu-id="ea9ee-197">ToSingle</span><span class="sxs-lookup"><span data-stu-id="ea9ee-197">ToSingle</span></span>|<span data-ttu-id="ea9ee-198">ToString</span><span class="sxs-lookup"><span data-stu-id="ea9ee-198">ToString</span></span>|

## <a name="inheritance-support"></a><span data-ttu-id="ea9ee-199">Поддержка наследования</span><span class="sxs-lookup"><span data-stu-id="ea9ee-199">Inheritance Support</span></span>

### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="ea9ee-200">Ограничения сопоставления при наследовании</span><span class="sxs-lookup"><span data-stu-id="ea9ee-200">Inheritance Mapping Restrictions</span></span>

<span data-ttu-id="ea9ee-201">Дополнительные сведения см. в разделе [Как Сопоставление иерархий наследования](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-201">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>

### <a name="inheritance-in-queries"></a><span data-ttu-id="ea9ee-202">Наследование в запросах</span><span class="sxs-lookup"><span data-stu-id="ea9ee-202">Inheritance in Queries</span></span>

<span data-ttu-id="ea9ee-203">В проекции поддерживаются только приведения типов C#.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-203">C# casts are supported only in projection.</span></span> <span data-ttu-id="ea9ee-204">Приведения типов, используемые в других средах, пропускаются и не преобразуются.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-204">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="ea9ee-205">Помимо преобразования имен функций SQL, SQL фактически выполняет действия, эквивалентные операциям класса <xref:System.Convert> среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-205">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="ea9ee-206">Это означает, что SQL может изменить значение одного типа на значение другого типа.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-206">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="ea9ee-207">Здесь нет операции, эквивалентной приведению типов в среде CLR, поскольку отсутствует понятие повторной интерпретации тех же битов как битов другого типа.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-207">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="ea9ee-208">По этой причине приведение типов C# работает только на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-208">That is why a C# cast works only locally.</span></span> <span data-ttu-id="ea9ee-209">Оно не используется для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-209">It is not remoted.</span></span>

<span data-ttu-id="ea9ee-210">Операторы `is` и `as`, а также метод `GetType` не ограничены оператором `Select`.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-210">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="ea9ee-211">Они могут использоваться также и в других операторах запроса.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-211">They can be used in other query operators also.</span></span>

## <a name="sql-server-2008-support"></a><span data-ttu-id="ea9ee-212">Поддержка SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="ea9ee-212">SQL Server 2008 Support</span></span>

<span data-ttu-id="ea9ee-213">Начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1), LINQ to SQL поддерживает сопоставление с новыми типами даты и времени, которые появились в SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-213">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="ea9ee-214">Однако операторы запросов LINQ to SQL, которые иногда используются при обработке значений, сопоставляемых с этими новыми типами, имеют определенные ограничения.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-214">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>

### <a name="unsupported-query-operators"></a><span data-ttu-id="ea9ee-215">Неподдерживаемые операторы запросов</span><span class="sxs-lookup"><span data-stu-id="ea9ee-215">Unsupported Query Operators</span></span>

<span data-ttu-id="ea9ee-216">Следующие операторы запросов не поддерживаются для значений, сопоставляемых с новыми типами даты и времени SQL Server: `DATETIME2`, `DATE`, `TIME` и `DATETIMEOFFSET`.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-216">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

<span data-ttu-id="ea9ee-217">Дополнительные сведения о сопоставлении этих типов даты и времени SQL Server см. в разделе [сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-217">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>

## <a name="sql-server-2005-support"></a><span data-ttu-id="ea9ee-218">Поддержка SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="ea9ee-218">SQL Server 2005 Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ea9ee-219">не поддерживает следующие функции SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-219">does not support the following SQL Server 2005 features:</span></span>

- <span data-ttu-id="ea9ee-220">Хранимые процедуры, написанные для среды SQL CLR.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-220">Stored procedures written for SQL CLR.</span></span>

- <span data-ttu-id="ea9ee-221">Пользовательский тип.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-221">User-defined type.</span></span>

- <span data-ttu-id="ea9ee-222">Функции запросов XML.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-222">XML query features.</span></span>

## <a name="sql-server-2000-support"></a><span data-ttu-id="ea9ee-223">Поддержка SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="ea9ee-223">SQL Server 2000 Support</span></span>

<span data-ttu-id="ea9ee-224">На поддержку [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] влияют следующие ограничения [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)] (по сравнению с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-224">The following [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] limitations (compared to [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)]) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>

### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="ea9ee-225">Операторы «Cross Apply» и «Outer Apply»</span><span class="sxs-lookup"><span data-stu-id="ea9ee-225">Cross Apply and Outer Apply Operators</span></span>

<span data-ttu-id="ea9ee-226">Эти операторы недоступны в [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-226">These operators are not available in [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> <span data-ttu-id="ea9ee-227">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] пытается выполнить ряд операций перезаписи, чтобы заменить их соответствующими объединениями.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-227">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries a series of rewrites to replace them with appropriate joins.</span></span>

<span data-ttu-id="ea9ee-228">Операторы `Cross Apply` и `Outer Apply` создаются для перехода по отношениям.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-228">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="ea9ee-229">Набор запросов, для которого такие операции перезаписи возможны, не является правильно определенным.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-229">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="ea9ee-230">По этой причине минимальным набором запросов, поддерживаемым для [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)], является набор, который не включает переходов по отношениям.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-230">For this reason, the minimal set of queries that is supported for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] is the set that does not involve relationship navigation.</span></span>

### <a name="text--ntext"></a><span data-ttu-id="ea9ee-231">text / ntext</span><span class="sxs-lookup"><span data-stu-id="ea9ee-231">text / ntext</span></span>

<span data-ttu-id="ea9ee-232">Типы данных `text`  /  `ntext` нельзя использовать в некоторых операциях запросов для `varchar(max)`  /  `nvarchar(max)`, которые поддерживаются приложением [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-232">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].</span></span>

<span data-ttu-id="ea9ee-233">Способов разрешения проблем, связанных с этим ограничением, не существует.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-233">No resolution is available for this limitation.</span></span> <span data-ttu-id="ea9ee-234">В частности, метод `Distinct()` нельзя использовать для результата, который содержит члены, сопоставленные с `text` или `ntext`.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-234">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>

### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="ea9ee-235">Поведение, инициируемое вложенными запросами</span><span class="sxs-lookup"><span data-stu-id="ea9ee-235">Behavior Triggered by Nested Queries</span></span>

[!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] <span data-ttu-id="ea9ee-236">((SP4)) связыватель обладает некоторыми особенностями поведения, которые инициируются вложенными запросами.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-236">(through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="ea9ee-237">Набор запросов SQL, которые инициируют эти особенности, не является правильно определенным.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-237">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="ea9ee-238">По этой причине невозможно определить набор [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запросы, которые могут вызывать исключения SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-238">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>

### <a name="skip-and-take-operators"></a><span data-ttu-id="ea9ee-239">Операторы «Skip» и «Take»</span><span class="sxs-lookup"><span data-stu-id="ea9ee-239">Skip and Take Operators</span></span>

<span data-ttu-id="ea9ee-240">На методы <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A> накладываются некоторые ограничения при их использовании в запросах для [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9ee-240"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> <span data-ttu-id="ea9ee-241">Дополнительные сведения см. в записи «"Skip и делаются исключения в SQL Server 2000» в [Устранение неполадок](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-241">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>

## <a name="object-materialization"></a><span data-ttu-id="ea9ee-242">Материализация объектов</span><span class="sxs-lookup"><span data-stu-id="ea9ee-242">Object Materialization</span></span>

<span data-ttu-id="ea9ee-243">Материализация создает объекты среды CLR из строк, возвращаемых одним или несколькими запросами SQL.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-243">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>

- <span data-ttu-id="ea9ee-244">Следующие вызовы *выполнен локально* как часть материализации:</span><span class="sxs-lookup"><span data-stu-id="ea9ee-244">The following calls are *executed locally* as a part of materialization:</span></span>

  - <span data-ttu-id="ea9ee-245">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="ea9ee-245">Constructors</span></span>

  - <span data-ttu-id="ea9ee-246">Методы `ToString` в проекциях</span><span class="sxs-lookup"><span data-stu-id="ea9ee-246">`ToString` methods in projections</span></span>

  - <span data-ttu-id="ea9ee-247">Приведения типов в проекциях</span><span class="sxs-lookup"><span data-stu-id="ea9ee-247">Type casts in projections</span></span>

- <span data-ttu-id="ea9ee-248">Методами, которые следуют <xref:System.Linq.Enumerable.AsEnumerable%2A> метод *выполнен локально*.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-248">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="ea9ee-249">Этот метод не приводит к немедленному выполнению.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-249">This method does not cause immediate execution.</span></span>

- <span data-ttu-id="ea9ee-250">В качестве типа возвращаемых данных результата запроса или члена типа результата можно использовать значение `struct`.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-250">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="ea9ee-251">Сущности должны быть классами.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-251">Entities are required to be classes.</span></span> <span data-ttu-id="ea9ee-252">Анонимные типы материализуются как экземпляры классов, но в проекциях можно использовать структуры (не сущности).</span><span class="sxs-lookup"><span data-stu-id="ea9ee-252">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>

- <span data-ttu-id="ea9ee-253">Член типа возвращаемого значения может быть типом, реализующим интерфейс <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-253">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="ea9ee-254">Он материализуется как локальная коллекция.</span><span class="sxs-lookup"><span data-stu-id="ea9ee-254">It is materialized as a local collection.</span></span>

- <span data-ttu-id="ea9ee-255">Следующие методы вызывают *немедленную материализацию* последовательности, к которой применяются эти методы:</span><span class="sxs-lookup"><span data-stu-id="ea9ee-255">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a><span data-ttu-id="ea9ee-256">См. также</span><span class="sxs-lookup"><span data-stu-id="ea9ee-256">See also</span></span>

- [<span data-ttu-id="ea9ee-257">Ссылки</span><span class="sxs-lookup"><span data-stu-id="ea9ee-257">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="ea9ee-258">Возврат или пропуск элементов последовательности</span><span class="sxs-lookup"><span data-stu-id="ea9ee-258">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)
- [<span data-ttu-id="ea9ee-259">Сцепление двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="ea9ee-259">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)
- [<span data-ttu-id="ea9ee-260">Возврат разности наборов между двумя последовательностями</span><span class="sxs-lookup"><span data-stu-id="ea9ee-260">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)
- [<span data-ttu-id="ea9ee-261">Возврат пересечения наборов двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="ea9ee-261">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)
- [<span data-ttu-id="ea9ee-262">Возврат объединения наборов двух последовательностей</span><span class="sxs-lookup"><span data-stu-id="ea9ee-262">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)
