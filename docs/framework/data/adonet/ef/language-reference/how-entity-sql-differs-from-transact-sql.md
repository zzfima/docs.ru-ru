---
title: Отличия Entity SQL от Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 299cb9bbe90c72619cf809a8fc673fca456bd6fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150235"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="c7ebc-102">Отличия Entity SQL от Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7ebc-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="c7ebc-103">Эта тема описывает [!INCLUDE[esql](../../../../../../includes/esql-md.md)] различия между и Трансакт-СЗЛ.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="c7ebc-104">Поддержка наследования и связей</span><span class="sxs-lookup"><span data-stu-id="c7ebc-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-105">работает непосредственно с концептуальными схемами сущности и поддерживает концептуальные модели, такие как наследование и отношения.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-105">works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="c7ebc-106">При работе с наследованием часто полезно выбрать экземпляры подтипа из коллекции экземпляров супертипа.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="c7ebc-107">Оператор [типа](oftype-entity-sql.md) в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (по `oftype` аналогии с в Секвенсах C) предоставляет эту возможность.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-107">The [oftype](oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="c7ebc-108">Поддержка коллекций</span><span class="sxs-lookup"><span data-stu-id="c7ebc-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-109">рассматривает коллекции как первоклассные сущности.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-109">treats collections as first-class entities.</span></span> <span data-ttu-id="c7ebc-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-110">For example:</span></span>  
  
- <span data-ttu-id="c7ebc-111">Выражения коллекций допускаются в предложении `from`.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-111">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="c7ebc-112">Вложенные запросы `in` и `exists` были обобщены, чтобы разрешить любые коллекции.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="c7ebc-113">Вложенный запрос - один из видов коллекций.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="c7ebc-114">`e1 in e2` и `exists(e)` - конструкции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для выполнения этих операций.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="c7ebc-115">Операторы работы с наборами, такие как `union`, `intersect` и `except`, теперь работают с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="c7ebc-116">Операции соединения с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="c7ebc-117">Поддержка выражений</span><span class="sxs-lookup"><span data-stu-id="c7ebc-117">Support for Expressions</span></span>  
 <span data-ttu-id="c7ebc-118">В Трансакт-СЗЛ есть подзапросы (таблицы) и выражения (строки и столбцы).</span><span class="sxs-lookup"><span data-stu-id="c7ebc-118">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="c7ebc-119">Для поддержки коллекций [!INCLUDE[esql](../../../../../../includes/esql-md.md)] и вложенных коллекций, делает все выражение.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-120">более композитным, чем Трансакт-СЗЛ - каждое выражение может быть использовано в любом месте.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-120">is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="c7ebc-121">Результатом выражения запроса всегда является коллекция проецируемых типов, которая может быть использована везде, где разрешено выражение коллекции.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="c7ebc-122">Для получения информации о выражениях Transact-S'L, которые не поддерживаются, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [см.](unsupported-expressions-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="c7ebc-122">For information about Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="c7ebc-123">Допустимы все приведенные ниже запросы [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="c7ebc-124">Единая обработка вложенных запросов</span><span class="sxs-lookup"><span data-stu-id="c7ebc-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="c7ebc-125">С учетом акцента на таблицах, Transact-S'L выполняет контекстуальную интерпретацию субзапросов.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-125">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="c7ebc-126">Например, подкачность `from` в оговорке считается мультинабором (таблица).</span><span class="sxs-lookup"><span data-stu-id="c7ebc-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="c7ebc-127">Тот же вложенный запрос в предложении `select` считается скалярным вложенным запросом.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="c7ebc-128">Аналогичным образом, выжим, используемый `in` на левой стороне оператора, считается скалярным вычком, в то время как правая сторона, как ожидается, будет многосетовой подгруппой.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="c7ebc-129">Эти различия устранены в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7ebc-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] eliminates these differences.</span></span> <span data-ttu-id="c7ebc-130">Выражение имеет единую интерпретацию, которая не зависит от контекста, в котором оно использовано.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-131">рассматривает все подзапросы как мультинаборные подзапросы.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-131">considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="c7ebc-132">Если значение масштабирования желательно из подкатого, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] `anyelement` предоставляет оператор, который работает на коллекции (в данном случае, subquery), и извлекает значение синглтона из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="c7ebc-133">Устранение неявных приведений для вложенных запросов</span><span class="sxs-lookup"><span data-stu-id="c7ebc-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="c7ebc-134">Побочный эффект единообразной обработки вложенных запросов - неявное преобразование вложенных запросов к скалярным значениям.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="c7ebc-135">В частности, в Transact-S'L многомножество строк (с одним полем) неявно преобразуется в масштабируемое значение, тип данных которого является значением поля.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-135">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 <span data-ttu-id="c7ebc-136">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает такое неявное приведение.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-136">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support this implicit coercion.</span></span> <span data-ttu-id="c7ebc-137">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предусмотрены оператор ANYELEMENT, который извлекает одноэлементное значение из коллекции, и предложение `select value`, позволяющее избежать создания оболочки строк в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-137">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="c7ebc-138">Выбранное значение: устранение неявной оболочки строк</span><span class="sxs-lookup"><span data-stu-id="c7ebc-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="c7ebc-139">Выбранное положение в подзапросе Transact-S'L неявно создает обертку строки вокруг элементов в оговорке.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-139">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="c7ebc-140">Это означает, что нельзя создавать коллекции скалярных величин или объектов.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-140">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="c7ebc-141">Трансакт-СЗЛ допускает неявное принуждение между типом строки с одним полем и однотонным значением одного и того же типа данных.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-141">Transact-SQL allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 <span data-ttu-id="c7ebc-142">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет предложение `select value`, чтобы пропустить неявное построение строки.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-142">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="c7ebc-143">В предложении `select value` можно указать только один элемент.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="c7ebc-144">При использовании такого предложения не создается оболочка строк вокруг элементов в предложении `select`, что позволяет получить коллекцию необходимой формы, например: `select value a`.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 <span data-ttu-id="c7ebc-145">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает также конструктор строк, позволяющий создавать произвольные строки.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-145">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="c7ebc-146">Предложение `select` принимает один или несколько элементов в проекции и возвращает результаты в записи данных с полями, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="c7ebc-147">Левая корреляция и задание псевдонимов</span><span class="sxs-lookup"><span data-stu-id="c7ebc-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="c7ebc-148">В Transact-S'L выражения в данной области `select` (одна оговорка, как или `from`) не могут ссылаться на выражения, определенные ранее в той же области.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-148">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="c7ebc-149">Некоторые диалекты СЗЛ (в том числе Transact-S'L) поддерживают ограниченные формы этих в оговорке. `from`</span><span class="sxs-lookup"><span data-stu-id="c7ebc-149">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-150">обобщает левые корреляции в оговорке `from` и относится к ним единообразно.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-150">generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="c7ebc-151">Выражения в предложении `from` могут содержать ссылки на более ранние определения (определения слева) в том же предложении без дополнительных синтаксических конструкций.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 <span data-ttu-id="c7ebc-152">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] также налагаются дополнительные ограничения на запросы, включающие предложения `group by`.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-152">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="c7ebc-153">Выражения в `select` оговорке `having` и пункте таких запросов `group by` могут относиться только к ключам только через их псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="c7ebc-154">Следующая конструкция действительна в Transact-S'L, но не в: [!INCLUDE[esql](../../../../../../includes/esql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ebc-154">The following construct is valid in Transact-SQL but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="c7ebc-155">На языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] необходимо написать:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="c7ebc-156">Ссылочные столбцы (свойства) таблиц (коллекций)</span><span class="sxs-lookup"><span data-stu-id="c7ebc-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="c7ebc-157">Все ссылочные столбцы в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] должны быть квалифицированы с псевдонимом таблицы.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="c7ebc-158">Следующая конструкция `a` (при условии, `T`что это действительный столбец таблицы) действительна в Transact-S'L, но не в [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7ebc-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="c7ebc-159">Форма [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="c7ebc-160">Псевдонимы таблицы в предложении `from` необязательны.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="c7ebc-161">Имя таблицы используется как неявный псевдоним.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-161">The name of the table is used as the implicit alias.</span></span> <span data-ttu-id="c7ebc-162">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] допустима также следующая форма:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-162">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="c7ebc-163">Перемещение по объектам</span><span class="sxs-lookup"><span data-stu-id="c7ebc-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="c7ebc-164">В "Трансакт-СЗЛ" используется обозначение "." для обозначения столбцов (ряд) таблицы.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-164">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> <span data-ttu-id="c7ebc-165">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] этот подход (заимствованный из языков программирования) расширен и позволяет перемещаться по свойствам объекта</span><span class="sxs-lookup"><span data-stu-id="c7ebc-165">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="c7ebc-166">Например, если `p` - выражение типа Person, с помощью следующего синтаксиса [!INCLUDE[esql](../../../../../../includes/esql-md.md)] можно ссылаться на город в его адресе.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="c7ebc-167">Не поддерживается \*</span><span class="sxs-lookup"><span data-stu-id="c7ebc-167">No Support for \*</span></span>  
 <span data-ttu-id="c7ebc-168">«Трансакт-СЗЛ» поддерживает неквалифицированный синтаксис в качестве псевдонима \* для всего\*ряда, а также квалифицированный синтаксис (т. ) в качестве ярлыка для полей этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-168">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="c7ebc-169">Кроме того, Transact-S'L допускает\*специальный подсчет () агрегат, который включает в себя нулевую информацию.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-169">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 <span data-ttu-id="c7ebc-170">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает конструкцию «\*».</span><span class="sxs-lookup"><span data-stu-id="c7ebc-170">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support the \* construct.</span></span> <span data-ttu-id="c7ebc-171">Запросы Трансакт-СЗЛ формы `select * from T` `select T1.* from T1, T2...` и могут [!INCLUDE[esql](../../../../../../includes/esql-md.md)] быть `select value t from T as t` `select value t1 from T1 as t1, T2 as t2...`выражены как и, соответственно.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-171">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="c7ebc-172">Эти конструкции также обеспечивают наследование (заменяемость значений), в то время как варианты `select *` ограничены свойствами верхнего уровня объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 <span data-ttu-id="c7ebc-173">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает статистическую функцию `count(*)`.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-173">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="c7ebc-174">Используйте вместо этого `count(0)`.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="c7ebc-175">Изменения на предложение Group By</span><span class="sxs-lookup"><span data-stu-id="c7ebc-175">Changes to Group By</span></span>  
 <span data-ttu-id="c7ebc-176">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает псевдонимы ключей `group by`.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-176">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports aliasing of `group by` keys.</span></span> <span data-ttu-id="c7ebc-177">Выражения в предложении `select` и предложении `having` таких запросов должны ссылаться на ключи `group by` через псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="c7ebc-178">Например, синтаксическая конструкция [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="c7ebc-179">... эквивалентно следующему Трансакт-СЗЛ:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-179">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="c7ebc-180">Статистические функции на основе коллекций</span><span class="sxs-lookup"><span data-stu-id="c7ebc-180">Collection-Based Aggregates</span></span>  
 <span data-ttu-id="c7ebc-181">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает два типа статистических функций.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-181">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="c7ebc-182">Статистические функции на основе коллекций работают с коллекциями и возвращают результат статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="c7ebc-183">Они могут применяться в любом месте в запросе и не требуют предложения `group by`.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="c7ebc-184">Пример:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-184">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 <span data-ttu-id="c7ebc-185">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] также поддерживает статистические функции в стиле SQL.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-185">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also supports SQL-style aggregates.</span></span> <span data-ttu-id="c7ebc-186">Пример:</span><span class="sxs-lookup"><span data-stu-id="c7ebc-186">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="c7ebc-187">Использование предложения ORDER BY</span><span class="sxs-lookup"><span data-stu-id="c7ebc-187">ORDER BY Clause Usage</span></span>  
<span data-ttu-id="c7ebc-188">Трансакт-СЗЛ `ORDER BY` позволяет указывать положения только в `SELECT .. FROM .. WHERE` верхнем блоке.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-188">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="c7ebc-189">В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] вложенном выражении `ORDER BY` можно использовать вложенное выражение, и оно может быть размещено в любом месте запроса, но заказ в вложенном запросе не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-189">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="c7ebc-190">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="c7ebc-190">Identifiers</span></span>  
 <span data-ttu-id="c7ebc-191">В Transact-S'L сравнение идентификаторов основано на сопоставлении текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-191">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="c7ebc-192">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] регистр символов в идентификаторах не учитывается, однако учитываются диакритические знаки (в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] различаются символы с диакритическими знаками и без таковых; например «a» не равно «ấ»).</span><span class="sxs-lookup"><span data-stu-id="c7ebc-192">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> <span data-ttu-id="c7ebc-193">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] версии символов, которые внешне кажутся одинаковыми, но определены на разных кодовых страницах, считаются различными символами.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-193">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="c7ebc-194">Для получения дополнительной информации [см.](input-character-set-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="c7ebc-194">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="c7ebc-195">Функциональность Transact-SQL, недоступная в Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c7ebc-195">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="c7ebc-196">Следующая функциональность Transact-S'L [!INCLUDE[esql](../../../../../../includes/esql-md.md)]недоступна в .</span><span class="sxs-lookup"><span data-stu-id="c7ebc-196">The following Transact-SQL functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="c7ebc-197">DML</span><span class="sxs-lookup"><span data-stu-id="c7ebc-197">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-198">в настоящее время не поддерживает dML-выписки (вставить, обновить, удалить).</span><span class="sxs-lookup"><span data-stu-id="c7ebc-198">currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="c7ebc-199">DDL</span><span class="sxs-lookup"><span data-stu-id="c7ebc-199">DDL</span></span>  
 <span data-ttu-id="c7ebc-200">Текущая версия [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает DDL.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-200">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="c7ebc-201">Командное программирование</span><span class="sxs-lookup"><span data-stu-id="c7ebc-201">Imperative Programming</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-202">не оказывает поддержки императивному программированию, в отличие от Трансакт-СЗЛ.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-202">provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="c7ebc-203">Используйте вместо этого языки программирования.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-203">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="c7ebc-204">Функции группирования</span><span class="sxs-lookup"><span data-stu-id="c7ebc-204">Grouping Functions</span></span>  
 <span data-ttu-id="c7ebc-205">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пока не поддерживает функции группирования (например, CUBE, ROLLUP и GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="c7ebc-205">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="c7ebc-206">Аналитические функции</span><span class="sxs-lookup"><span data-stu-id="c7ebc-206">Analytic Functions</span></span>  
 <span data-ttu-id="c7ebc-207">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не предоставляет (пока) поддержку функций аналитики.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-207">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="c7ebc-208">Встроенные функции, операторы</span><span class="sxs-lookup"><span data-stu-id="c7ebc-208">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-209">поддерживает подмножество трансат-СЗЛ, встроенных в функции и операторов.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-209">supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="c7ebc-210">Вероятно, эти операторы и функции будут реализованы ведущими поставщиками хранилищ.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-210">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="c7ebc-211">использует функции, задекларированные в манифесте поставщика.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-211">uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="c7ebc-212">Кроме того, система Entity Framework позволяет декларировать встроенные и [!INCLUDE[esql](../../../../../../includes/esql-md.md)] определяемые пользователем существующие функции хранилища для использования.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-212">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="c7ebc-213">Указания</span><span class="sxs-lookup"><span data-stu-id="c7ebc-213">Hints</span></span>  
 <span data-ttu-id="c7ebc-214">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не предоставляет механизм подсказок в запросах.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-214">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="c7ebc-215">Пакетирование результатов запроса</span><span class="sxs-lookup"><span data-stu-id="c7ebc-215">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="c7ebc-216">не поддерживает пакетирование результатов запросов.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-216">does not support batching query results.</span></span> <span data-ttu-id="c7ebc-217">Например, действует следующий данный Transact-S'L (отправка в виде партии):</span><span class="sxs-lookup"><span data-stu-id="c7ebc-217">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="c7ebc-218">Однако эквивалент [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-218">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="c7ebc-219">поддерживает только запросы, которые выдают один результат на одну команду.</span><span class="sxs-lookup"><span data-stu-id="c7ebc-219">only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ebc-220">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7ebc-220">See also</span></span>

- [<span data-ttu-id="c7ebc-221">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c7ebc-221">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="c7ebc-222">Неподдерживаемые выражения</span><span class="sxs-lookup"><span data-stu-id="c7ebc-222">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
