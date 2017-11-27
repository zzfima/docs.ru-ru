---
title: "Отличия Entity SQL от Transact-SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5d99b433cb499316872cfb09d9fca7f7da753bb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="94b23-102">Отличия Entity SQL от Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94b23-102">How Entity SQL Differs from Transact-SQL</span></span>
<span data-ttu-id="94b23-103">В этом разделе описываются различия между [!INCLUDE[esql](../../../../../../includes/esql-md.md)] и [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94b23-103">This topic describes the differences between [!INCLUDE[esql](../../../../../../includes/esql-md.md)] and [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="94b23-104">Поддержка наследования и связей</span><span class="sxs-lookup"><span data-stu-id="94b23-104">Inheritance and Relationships Support</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-105">работает непосредственно с концептуальными схемами сущности и поддерживает функции концептуальной модели, как наследование и связи.</span><span class="sxs-lookup"><span data-stu-id="94b23-105"> works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="94b23-106">При работе с наследованием часто полезно выбрать экземпляры подтипа из коллекции экземпляров супертипа.</span><span class="sxs-lookup"><span data-stu-id="94b23-106">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="94b23-107">[Oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) оператор в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (аналогично `oftype` в последовательностях C#) предоставляет эту возможность.</span><span class="sxs-lookup"><span data-stu-id="94b23-107">The [oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="94b23-108">Поддержка коллекций</span><span class="sxs-lookup"><span data-stu-id="94b23-108">Support for Collections</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-109">коллекции рассматриваются как сущности первого класса.</span><span class="sxs-lookup"><span data-stu-id="94b23-109"> treats collections as first-class entities.</span></span> <span data-ttu-id="94b23-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="94b23-110">For example:</span></span>  
  
-   <span data-ttu-id="94b23-111">Выражения коллекций допускаются в предложении `from`.</span><span class="sxs-lookup"><span data-stu-id="94b23-111">Collection expressions are valid in a `from` clause.</span></span>  
  
-   <span data-ttu-id="94b23-112">Вложенные запросы `in` и `exists` были обобщены, чтобы разрешить любые коллекции.</span><span class="sxs-lookup"><span data-stu-id="94b23-112">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="94b23-113">Вложенный запрос - один из видов коллекций.</span><span class="sxs-lookup"><span data-stu-id="94b23-113">A subquery is one kind of collection.</span></span> <span data-ttu-id="94b23-114">`e1 in e2` и `exists(e)` - конструкции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для выполнения этих операций.</span><span class="sxs-lookup"><span data-stu-id="94b23-114">`e1 in e2` and `exists(e)` are the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] constructs to perform these operations.</span></span>  
  
-   <span data-ttu-id="94b23-115">Операторы работы с наборами, такие как `union`, `intersect` и `except`, теперь работают с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="94b23-115">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
-   <span data-ttu-id="94b23-116">Операции соединения с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="94b23-116">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="94b23-117">Поддержка выражений</span><span class="sxs-lookup"><span data-stu-id="94b23-117">Support for Expressions</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="94b23-118">имеет вложенные запросы (таблицы) и выражения (строки и столбцы).</span><span class="sxs-lookup"><span data-stu-id="94b23-118"> has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="94b23-119">Для поддержки коллекций и вложенных коллекций [!INCLUDE[esql](../../../../../../includes/esql-md.md)] делает все выражения.</span><span class="sxs-lookup"><span data-stu-id="94b23-119">To support collections and nested collections, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] makes everything an expression.</span></span> <span data-ttu-id="94b23-120">Код [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является более легко компонуемым по сравнению с кодом [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] - любое выражение может использоваться в любом месте.</span><span class="sxs-lookup"><span data-stu-id="94b23-120">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] is more composable than [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]—every expression can be used anywhere.</span></span> <span data-ttu-id="94b23-121">Результатом выражения запроса всегда является коллекция проецируемых типов, которая может быть использована везде, где разрешено выражение коллекции.</span><span class="sxs-lookup"><span data-stu-id="94b23-121">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="94b23-122">Сведения о [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] выражения, которые не поддерживаются в [!INCLUDE[esql](../../../../../../includes/esql-md.md)], в разделе [неподдерживаемые выражения](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="94b23-122">For information about [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], see [Unsupported Expressions](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="94b23-123">Допустимы все приведенные ниже запросы [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="94b23-123">The following are all valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries:</span></span>  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="94b23-124">Единая обработка вложенных запросов</span><span class="sxs-lookup"><span data-stu-id="94b23-124">Uniform Treatment of Subqueries</span></span>  
 <span data-ttu-id="94b23-125">Ориентированности на таблицы, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] выполняет контекстную интерпретацию вложенных запросов.</span><span class="sxs-lookup"><span data-stu-id="94b23-125">Given its emphasis on tables, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="94b23-126">Например, вложенный запрос в `from` предложение считается мультинабором (таблица).</span><span class="sxs-lookup"><span data-stu-id="94b23-126">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="94b23-127">Тот же вложенный запрос в предложении `select` считается скалярным вложенным запросом.</span><span class="sxs-lookup"><span data-stu-id="94b23-127">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="94b23-128">Аналогичным образом, вложенный запрос, используемый в левой части `in` оператор считается скалярным вложенным запросом, а с правой стороны предполагается вложенный запрос мультинабора.</span><span class="sxs-lookup"><span data-stu-id="94b23-128">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="94b23-129">Эти различия устранены в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94b23-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] eliminates these differences.</span></span> <span data-ttu-id="94b23-130">Выражение имеет единую интерпретацию, которая не зависит от контекста, в котором оно использовано.</span><span class="sxs-lookup"><span data-stu-id="94b23-130">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-131">рассматривает всех вложенных запросов к будет мультинабора.</span><span class="sxs-lookup"><span data-stu-id="94b23-131"> considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="94b23-132">Если из вложенного запроса, скалярное значение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет `anyelement` оператор обращается к коллекции (в данном случае вложенный запрос), который извлекает одноэлементное значение из коллекции.</span><span class="sxs-lookup"><span data-stu-id="94b23-132">If a scalar value is desired from the subquery, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="94b23-133">Устранение неявных приведений для вложенных запросов</span><span class="sxs-lookup"><span data-stu-id="94b23-133">Avoiding Implicit Coercions for Subqueries</span></span>  
 <span data-ttu-id="94b23-134">Побочный эффект единообразной обработки вложенных запросов - неявное преобразование вложенных запросов к скалярным значениям.</span><span class="sxs-lookup"><span data-stu-id="94b23-134">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="94b23-135">В частности, в языке [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] мультинабор строк (с единственным полем) неявно преобразуется в скалярную величину, тип данных которой совпадает с типом данных поля.</span><span class="sxs-lookup"><span data-stu-id="94b23-135">Specifically, in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 <span data-ttu-id="94b23-136">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает такое неявное приведение.</span><span class="sxs-lookup"><span data-stu-id="94b23-136">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support this implicit coercion.</span></span> <span data-ttu-id="94b23-137">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предусмотрены оператор ANYELEMENT, который извлекает одноэлементное значение из коллекции, и предложение `select value`, позволяющее избежать создания оболочки строк в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="94b23-137">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the ANYELEMENT operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="94b23-138">Выбранное значение: устранение неявной оболочки строк</span><span class="sxs-lookup"><span data-stu-id="94b23-138">Select Value: Avoiding the Implicit Row Wrapper</span></span>  
 <span data-ttu-id="94b23-139">Предложение select во [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] вложенный запрос неявно создает оболочку строк вокруг элементов в предложении.</span><span class="sxs-lookup"><span data-stu-id="94b23-139">The select clause in a [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="94b23-140">Это означает, что нельзя создавать коллекции скалярных величин или объектов.</span><span class="sxs-lookup"><span data-stu-id="94b23-140">This implies that we cannot create collections of scalars or objects.</span></span> [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="94b23-141">обеспечивает неявное приведение между rowtype с одним полем и одноэлементным значением того же типа данных.</span><span class="sxs-lookup"><span data-stu-id="94b23-141"> allows an implicit coercion between a rowtype with one field, and a singleton value of the same data type.</span></span>  
  
 <span data-ttu-id="94b23-142">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет предложение `select value`, чтобы пропустить неявное построение строки.</span><span class="sxs-lookup"><span data-stu-id="94b23-142">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="94b23-143">В предложении `select value` можно указать только один элемент.</span><span class="sxs-lookup"><span data-stu-id="94b23-143">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="94b23-144">При использовании такого предложения не создается оболочка строк вокруг элементов в предложении `select`, что позволяет получить коллекцию необходимой формы, например: `select value a`.</span><span class="sxs-lookup"><span data-stu-id="94b23-144">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example: `select value a`.</span></span>  
  
 <span data-ttu-id="94b23-145">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает также конструктор строк, позволяющий создавать произвольные строки.</span><span class="sxs-lookup"><span data-stu-id="94b23-145">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="94b23-146">Предложение `select` принимает один или несколько элементов в проекции и возвращает результаты в записи данных с полями, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94b23-146">`select` takes one or more elements in the projection and results in a data record with fields, as follows:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="94b23-147">Левая корреляция и задание псевдонимов</span><span class="sxs-lookup"><span data-stu-id="94b23-147">Left Correlation and Aliasing</span></span>  
 <span data-ttu-id="94b23-148">В языке [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] выражения в данной области (отдельное предложение, такое как `select` или `from`) не могут ссылаться на выражения, определенные ранее в той же области.</span><span class="sxs-lookup"><span data-stu-id="94b23-148">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="94b23-149">Некоторые диалекты SQL (в том числе [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) поддерживают их ограниченные формы в предложении `from`.</span><span class="sxs-lookup"><span data-stu-id="94b23-149">Some dialects of SQL (including [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]) do support limited forms of these in the `from` clause.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-150">обобщает левые корреляции в `from` предложения и одинаково их обрабатывает.</span><span class="sxs-lookup"><span data-stu-id="94b23-150"> generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="94b23-151">Выражения в предложении `from` могут содержать ссылки на более ранние определения (определения слева) в том же предложении без дополнительных синтаксических конструкций.</span><span class="sxs-lookup"><span data-stu-id="94b23-151">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 <span data-ttu-id="94b23-152">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] также налагаются дополнительные ограничения на запросы, включающие предложения `group by`.</span><span class="sxs-lookup"><span data-stu-id="94b23-152">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="94b23-153">Выражения в `select` предложение и `having` предложение таких запросов могут ссылаться только на `group by` ключи через псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="94b23-153">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="94b23-154">Следующая конструкция допустима в [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] , но не находится в [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="94b23-154">The following construct is valid in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] but are not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 <span data-ttu-id="94b23-155">На языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] необходимо написать:</span><span class="sxs-lookup"><span data-stu-id="94b23-155">To do this in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span></span>  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="94b23-156">Ссылочные столбцы (свойства) таблиц (коллекций)</span><span class="sxs-lookup"><span data-stu-id="94b23-156">Referencing Columns (Properties) of Tables (Collections)</span></span>  
 <span data-ttu-id="94b23-157">Все ссылочные столбцы в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] должны быть квалифицированы с псевдонимом таблицы.</span><span class="sxs-lookup"><span data-stu-id="94b23-157">All column references in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] must be qualified with the table alias.</span></span> <span data-ttu-id="94b23-158">Следующая конструкция (предполагается, что `a` является допустимым столбцом таблицы `T`) является допустимым в [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] , но не в [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94b23-158">The following construct (assuming that `a` is a valid column of table `T`) is valid in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] but not in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
```  
select a from T  
```  
  
 <span data-ttu-id="94b23-159">Форма [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="94b23-159">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] form is</span></span>  
  
```  
select t.a as A from T as t  
```  
  
 <span data-ttu-id="94b23-160">Псевдонимы таблицы в предложении `from` необязательны.</span><span class="sxs-lookup"><span data-stu-id="94b23-160">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="94b23-161">Имя таблицы используется как неявный псевдоним.</span><span class="sxs-lookup"><span data-stu-id="94b23-161">The name of the table is used as the implicit alias.</span></span> <span data-ttu-id="94b23-162">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] допустима также следующая форма:</span><span class="sxs-lookup"><span data-stu-id="94b23-162">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows the following form as well:</span></span>  
  
```  
select Tab.a from Tab  
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="94b23-163">Перемещение по объектам</span><span class="sxs-lookup"><span data-stu-id="94b23-163">Navigation Through Objects</span></span>  
 <span data-ttu-id="94b23-164">В языке [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] для ссылок на столбцы (строки) таблицы используется символ «.».</span><span class="sxs-lookup"><span data-stu-id="94b23-164">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] uses the "." notation for referencing columns of (a row of) a table.</span></span> <span data-ttu-id="94b23-165">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] этот подход (заимствованный из языков программирования) расширен и позволяет перемещаться по свойствам объекта</span><span class="sxs-lookup"><span data-stu-id="94b23-165">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="94b23-166">Например, если `p` - выражение типа Person, с помощью следующего синтаксиса [!INCLUDE[esql](../../../../../../includes/esql-md.md)] можно ссылаться на город в его адресе.</span><span class="sxs-lookup"><span data-stu-id="94b23-166">For example, if `p` is an expression of type Person, the following is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax for referencing the city of the address of this person.</span></span>  
  
```  
p.Address.City   
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="94b23-167">Не поддерживается *</span><span class="sxs-lookup"><span data-stu-id="94b23-167">No Support for *</span></span>  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]<span data-ttu-id="94b23-168">поддерживает * синтаксис в качестве псевдонима для всей строки и уточненного \* синтаксис (t.\*) для быстрого поля этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="94b23-168"> supports the unqualified * syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="94b23-169">Кроме того [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] позволяет ввести число специальных (\*) статистическое выражение, включающее значения NULL.</span><span class="sxs-lookup"><span data-stu-id="94b23-169">In addition, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 <span data-ttu-id="94b23-170">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает конструкцию «*».</span><span class="sxs-lookup"><span data-stu-id="94b23-170">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support the * construct.</span></span> <span data-ttu-id="94b23-171">Запросы [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] в форме `select * from T` и `select T1.* from T1, T2...` могут быть выражены в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] как `select value t from T as t` и `select value t1 from T1 as t1, T2 as t2...`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="94b23-171">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="94b23-172">Эти конструкции также обеспечивают наследование (заменяемость значений), в то время как варианты `select *` ограничены свойствами верхнего уровня объявленного типа.</span><span class="sxs-lookup"><span data-stu-id="94b23-172">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 <span data-ttu-id="94b23-173">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает статистическую функцию `count(*)`.</span><span class="sxs-lookup"><span data-stu-id="94b23-173">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="94b23-174">Взамен рекомендуется использовать `count(0)`.</span><span class="sxs-lookup"><span data-stu-id="94b23-174">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="94b23-175">Изменения на предложение Group By</span><span class="sxs-lookup"><span data-stu-id="94b23-175">Changes to Group By</span></span>  
 <span data-ttu-id="94b23-176">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает псевдонимы ключей `group by`.</span><span class="sxs-lookup"><span data-stu-id="94b23-176">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports aliasing of `group by` keys.</span></span> <span data-ttu-id="94b23-177">Выражения в предложении `select` и предложении `having` таких запросов должны ссылаться на ключи `group by` через псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="94b23-177">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="94b23-178">Например, синтаксическая конструкция [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="94b23-178">For example, this [!INCLUDE[esql](../../../../../../includes/esql-md.md)] syntax:</span></span>  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 <span data-ttu-id="94b23-179">...эквивалентна следующей конструкции [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="94b23-179">...is equivalent to the following [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:</span></span>  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="94b23-180">Статистические функции на основе коллекций</span><span class="sxs-lookup"><span data-stu-id="94b23-180">Collection-Based Aggregates</span></span>  
 <span data-ttu-id="94b23-181">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает два типа статистических функций.</span><span class="sxs-lookup"><span data-stu-id="94b23-181">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="94b23-182">Статистические функции на основе коллекций работают с коллекциями и возвращают результат статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="94b23-182">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="94b23-183">Они могут применяться в любом месте в запросе и не требуют предложения `group by`.</span><span class="sxs-lookup"><span data-stu-id="94b23-183">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="94b23-184">Например:</span><span class="sxs-lookup"><span data-stu-id="94b23-184">For example:</span></span>  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 <span data-ttu-id="94b23-185">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] также поддерживает статистические функции в стиле SQL.</span><span class="sxs-lookup"><span data-stu-id="94b23-185">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] also supports SQL-style aggregates.</span></span> <span data-ttu-id="94b23-186">Например:</span><span class="sxs-lookup"><span data-stu-id="94b23-186">For example:</span></span>  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="94b23-187">Использование предложения ORDER BY</span><span class="sxs-lookup"><span data-stu-id="94b23-187">ORDER BY Clause Usage</span></span>  
 <span data-ttu-id="94b23-188">В языке [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] предложения ORDER BY могут быть указаны только в самом верхнем блоке инструкции SELECT ..</span><span class="sxs-lookup"><span data-stu-id="94b23-188">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows ORDER BY clauses to be specified only in the topmost SELECT ..</span></span> <span data-ttu-id="94b23-189">FROM ..</span><span class="sxs-lookup"><span data-stu-id="94b23-189">FROM ..</span></span> <span data-ttu-id="94b23-190">WHERE.</span><span class="sxs-lookup"><span data-stu-id="94b23-190">WHERE block.</span></span> <span data-ttu-id="94b23-191">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] можно использовать вложенное выражение ORDER BY, которое может быть размещено в любом месте запроса, однако упорядочение во вложенном запросе не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="94b23-191">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] you can use a nested ORDER BY expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a><span data-ttu-id="94b23-192">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="94b23-192">Identifiers</span></span>  
 <span data-ttu-id="94b23-193">В языке [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] сравнение идентификаторов всегда осуществляется с учетом параметров сортировки текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="94b23-193">In [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="94b23-194">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] регистр символов в идентификаторах не учитывается, однако учитываются диакритические знаки (в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] различаются символы с диакритическими знаками и без таковых; например «a» не равно «ấ»).</span><span class="sxs-lookup"><span data-stu-id="94b23-194">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], identifiers are always case insensitive and accent sensitive (that is, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> <span data-ttu-id="94b23-195">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] версии символов, которые внешне кажутся одинаковыми, но определены на разных кодовых страницах, считаются различными символами.</span><span class="sxs-lookup"><span data-stu-id="94b23-195">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="94b23-196">Дополнительные сведения см. в разделе [набор символов ввода](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="94b23-196">For more information, see [Input Character Set](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="94b23-197">Функциональность Transact-SQL, недоступная в Entity SQL</span><span class="sxs-lookup"><span data-stu-id="94b23-197">Transact-SQL Functionality Not Available in Entity SQL</span></span>  
 <span data-ttu-id="94b23-198">Следующая функциональность [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] недоступна в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94b23-198">The following [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] functionality is not available in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
 <span data-ttu-id="94b23-199">DML</span><span class="sxs-lookup"><span data-stu-id="94b23-199">DML</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-200">в настоящее время не поддерживает инструкции DML (Вставка, обновление и удаление).</span><span class="sxs-lookup"><span data-stu-id="94b23-200"> currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="94b23-201">DDL</span><span class="sxs-lookup"><span data-stu-id="94b23-201">DDL</span></span>  
 <span data-ttu-id="94b23-202">Текущая версия [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает DDL.</span><span class="sxs-lookup"><span data-stu-id="94b23-202">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="94b23-203">Командное программирование</span><span class="sxs-lookup"><span data-stu-id="94b23-203">Imperative Programming</span></span>  
 <span data-ttu-id="94b23-204">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживает командное программирование в отличие от [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94b23-204">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides no support for imperative programming, unlike [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="94b23-205">Используйте вместо этого языки программирования.</span><span class="sxs-lookup"><span data-stu-id="94b23-205">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="94b23-206">Функции группирования</span><span class="sxs-lookup"><span data-stu-id="94b23-206">Grouping Functions</span></span>  
 <span data-ttu-id="94b23-207">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пока не поддерживает функции группирования (например, CUBE, ROLLUP и GROUPING_SET).</span><span class="sxs-lookup"><span data-stu-id="94b23-207">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="94b23-208">Функции аналитики</span><span class="sxs-lookup"><span data-stu-id="94b23-208">Analytic Functions</span></span>  
 <span data-ttu-id="94b23-209">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не предоставляет (пока) поддержку функций аналитики.</span><span class="sxs-lookup"><span data-stu-id="94b23-209">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="94b23-210">Встроенные функции, операторы</span><span class="sxs-lookup"><span data-stu-id="94b23-210">Built-in Functions, Operators</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-211">поддерживает подмножество [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]встроенных функций и операторов.</span><span class="sxs-lookup"><span data-stu-id="94b23-211"> supports a subset of [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]'s built in functions and operators.</span></span> <span data-ttu-id="94b23-212">Вероятно, эти операторы и функции будут реализованы ведущими поставщиками хранилищ.</span><span class="sxs-lookup"><span data-stu-id="94b23-212">These operators and functions are likely to be supported by the major store providers.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-213">использует функции конкретного хранилища, объявленные в манифесте поставщика.</span><span class="sxs-lookup"><span data-stu-id="94b23-213"> uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="94b23-214">Кроме того [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] позволяет объявлять встроенные и пользовательские функции хранилища для [!INCLUDE[esql](../../../../../../includes/esql-md.md)] для использования.</span><span class="sxs-lookup"><span data-stu-id="94b23-214">Additionally, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] allows you to declare built-in and user-defined existing store functions, for [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to use.</span></span>  
  
 <span data-ttu-id="94b23-215">Подсказки</span><span class="sxs-lookup"><span data-stu-id="94b23-215">Hints</span></span>  
 <span data-ttu-id="94b23-216">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не предоставляет механизм подсказок в запросах.</span><span class="sxs-lookup"><span data-stu-id="94b23-216">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="94b23-217">Пакетирование результатов запроса</span><span class="sxs-lookup"><span data-stu-id="94b23-217">Batching Query Results</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-218"> не поддерживает пакетирование результатов запросов.</span><span class="sxs-lookup"><span data-stu-id="94b23-218"> does not support batching query results.</span></span> <span data-ttu-id="94b23-219">Например, следующее выражение допустимо [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (отправляемый как пакет):</span><span class="sxs-lookup"><span data-stu-id="94b23-219">For example, the following is valid [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (sending as a batch):</span></span>  
  
```  
select * from products;  
select * from catagories;  
```  
  
 <span data-ttu-id="94b23-220">Однако эквивалент [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="94b23-220">However, the equivalent [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not supported:</span></span>  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="94b23-221"> поддерживает только запросы, которые выдают один результат на одну команду.</span><span class="sxs-lookup"><span data-stu-id="94b23-221"> only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b23-222">См. также</span><span class="sxs-lookup"><span data-stu-id="94b23-222">See Also</span></span>  
 [<span data-ttu-id="94b23-223">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="94b23-223">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="94b23-224">Неподдерживаемые выражения</span><span class="sxs-lookup"><span data-stu-id="94b23-224">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)
