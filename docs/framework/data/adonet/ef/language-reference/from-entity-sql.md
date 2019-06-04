---
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 36e3059869ed048bd7c5294c4f5f5407288610b2
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489937"
---
# <a name="from-entity-sql"></a><span data-ttu-id="b84a3-102">FROM (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b84a3-102">FROM (Entity SQL)</span></span>
<span data-ttu-id="b84a3-103">Указывает коллекцию, используемую в [ВЫБЕРИТЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) инструкций.</span><span class="sxs-lookup"><span data-stu-id="b84a3-103">Specifies the collection used in [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b84a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b84a3-104">Syntax</span></span>  
  
```  
FROM expression [ ,...n ] as C  
```  
  
## <a name="arguments"></a><span data-ttu-id="b84a3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b84a3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b84a3-106">Любое допустимое выражение запроса, возвращающее коллекцию, которая используется как источник в инструкции `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-106">Any valid query expression that yields a collection to use as a source in a `SELECT` statement.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b84a3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b84a3-107">Remarks</span></span>  
 <span data-ttu-id="b84a3-108">Предложение `FROM` - это список с разделителями-запятыми из одного или нескольких элементов предложения `FROM`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-108">A `FROM` clause is a comma-separated list of one or more `FROM` clause items.</span></span> <span data-ttu-id="b84a3-109">Предложение `FROM` может быть использовано, чтобы указать один или несколько источников для инструкции `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-109">The `FROM` clause can be used to specify one or more sources for a `SELECT` statement.</span></span> <span data-ttu-id="b84a3-110">Самая простая форма предложения `FROM` - единственное выражение запроса, которое определяет коллекцию и псевдоним, использованные как источники в инструкции `SELECT`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b84a3-110">The simplest form of a `FROM` clause is a single query expression that identifies a collection and an alias used as the source in a `SELECT` statement, as illustrated in the following example:</span></span>  
  
 `FROM C as c`  
  
## <a name="from-clause-items"></a><span data-ttu-id="b84a3-111">Элементы предложения FROM</span><span class="sxs-lookup"><span data-stu-id="b84a3-111">FROM Clause Items</span></span>  
 <span data-ttu-id="b84a3-112">Каждый элемент предложения `FROM` ссылается на исходную коллекцию в запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b84a3-112">Each `FROM` clause item refers to a source collection in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query.</span></span> <span data-ttu-id="b84a3-113">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает следующие классы элементов предложения `FROM`: простые элементы предложения `FROM`, элементы предложения `JOIN FROM` и элементы предложения `APPLY FROM`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-113">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports the following classes of `FROM` clause items: simple `FROM` clause items, `JOIN FROM` clause items, and `APPLY FROM` clause items.</span></span> <span data-ttu-id="b84a3-114">Каждый из этих элементов предложения `FROM` более подробно описан в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b84a3-114">Each of these `FROM` clause items is described in more detail in the following sections.</span></span>  
  
### <a name="simple-from-clause-item"></a><span data-ttu-id="b84a3-115">Простой элемент предложения FROM</span><span class="sxs-lookup"><span data-stu-id="b84a3-115">Simple FROM Clause Item</span></span>  
 <span data-ttu-id="b84a3-116">Самый простой элемент предложения `FROM` - единственное выражение, которое определяет коллекцию и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b84a3-116">The simplest `FROM` clause item is a single expression that identifies a collection and an alias.</span></span> <span data-ttu-id="b84a3-117">Выражение может быть просто набором сущностей, вложенным запросом или другим выражением, которое относится к типу коллекции.</span><span class="sxs-lookup"><span data-stu-id="b84a3-117">The expression can simply be an entity set, or a subquery, or any other expression that is a collection type.</span></span> <span data-ttu-id="b84a3-118">Ниже представлен пример такого кода.</span><span class="sxs-lookup"><span data-stu-id="b84a3-118">The following is an example:</span></span>  
  
```  
LOB.Customers as c  
```  
  
 <span data-ttu-id="b84a3-119">Спецификация псевдонима является необязательным элементом.</span><span class="sxs-lookup"><span data-stu-id="b84a3-119">The alias specification is optional.</span></span> <span data-ttu-id="b84a3-120">Альтернативная спецификация приведенного выше элемента предложения from может быть следующей:</span><span class="sxs-lookup"><span data-stu-id="b84a3-120">An alternate specification of the above from clause item could be the following:</span></span>  
  
```  
LOB.Customers  
```  
  
 <span data-ttu-id="b84a3-121">Если псевдоним не задан, то [!INCLUDE[esql](../../../../../../includes/esql-md.md)] попытается сформировать псевдоним на основе выражения коллекции.</span><span class="sxs-lookup"><span data-stu-id="b84a3-121">If no alias is specified, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias based on the collection expression.</span></span>  
  
### <a name="join-from-clause-item"></a><span data-ttu-id="b84a3-122">Элемент предложения JOIN FROM</span><span class="sxs-lookup"><span data-stu-id="b84a3-122">JOIN FROM Clause Item</span></span>  
 <span data-ttu-id="b84a3-123">Элемент предложения `JOIN FROM` представляет соединение между двумя элементами предложения `FROM`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-123">A `JOIN FROM` clause item represents a join between two `FROM` clause items.</span></span> <span data-ttu-id="b84a3-124">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает перекрестные соединения, внутренние соединения, левые и правые внешние соединения и полные внешние соединения.</span><span class="sxs-lookup"><span data-stu-id="b84a3-124">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports cross joins, inner joins, left and right outer joins, and full outer joins.</span></span> <span data-ttu-id="b84a3-125">Все эти соединения поддерживаются подобно тому, как они поддерживаются в Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b84a3-125">All these joins are supported similar to the way that they are supported in Transact-SQL.</span></span> <span data-ttu-id="b84a3-126">Как и в Transact-SQL, два `FROM` связанных элементов предложения `JOIN` должны быть независимыми.</span><span class="sxs-lookup"><span data-stu-id="b84a3-126">As in Transact-SQL, the two `FROM` clause items involved in the `JOIN` must be independent.</span></span> <span data-ttu-id="b84a3-127">(т. е. они не могут быть коррелированными).</span><span class="sxs-lookup"><span data-stu-id="b84a3-127">That is, they cannot be correlated.</span></span> <span data-ttu-id="b84a3-128">В этих случаях можно использовать операторы `CROSS APPLY` или `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-128">A `CROSS APPLY` or `OUTER APPLY` can be used for these cases.</span></span>  
  
#### <a name="cross-joins"></a><span data-ttu-id="b84a3-129">Перекрестные соединения</span><span class="sxs-lookup"><span data-stu-id="b84a3-129">Cross Joins</span></span>  
 <span data-ttu-id="b84a3-130">Выражение запроса `CROSS JOIN` формируют декартово произведение двух коллекций, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b84a3-130">A `CROSS JOIN` query expression produces the Cartesian product of the two collections, as illustrated in the following example:</span></span>  
  
 `FROM C AS c CROSS JOIN D as d`  
  
#### <a name="inner-joins"></a><span data-ttu-id="b84a3-131">Внутренние соединения</span><span class="sxs-lookup"><span data-stu-id="b84a3-131">Inner Joins</span></span>  
 <span data-ttu-id="b84a3-132">Оператор `INNER JOIN` формирует ограниченное декартово произведение двух коллекций, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b84a3-132">An `INNER JOIN` produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>  
  
 `FROM C AS c [INNER] JOIN D AS d ON e`  
  
 <span data-ttu-id="b84a3-133">Предшествующее выражение запроса обрабатывает сочетание каждого элемента коллекции слева, сопоставленного каждому элементу коллекции справа, где условие `ON` имеет значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="b84a3-133">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="b84a3-134">Если не указано условие `ON`, соединение `INNER JOIN` вырождается в `CROSS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-134">If no `ON` condition is specified, an `INNER JOIN` degenerates to a `CROSS JOIN`.</span></span>  
  
#### <a name="left-outer-joins-and-right-outer-joins"></a><span data-ttu-id="b84a3-135">Левые и правые внешние соединения</span><span class="sxs-lookup"><span data-stu-id="b84a3-135">Left Outer Joins and Right Outer Joins</span></span>  
 <span data-ttu-id="b84a3-136">Выражение запроса `OUTER JOIN` формирует ограниченное декартово произведение двух коллекций, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b84a3-136">An `OUTER JOIN` query expression produces a constrained Cartesian product of the two collections, as illustrated in the following example:</span></span>  
  
 `FROM C AS c LEFT OUTER JOIN D AS d ON e`  
  
 <span data-ttu-id="b84a3-137">Предшествующее выражение запроса обрабатывает сочетание каждого элемента коллекции слева, сопоставленного каждому элементу коллекции справа, где условие `ON` имеет значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="b84a3-137">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="b84a3-138">Если условие `ON` не выполняется, выражение все же обрабатывает единственный экземпляр элемента слева, поставленный в соответствие элементу справа, со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="b84a3-138">If the `ON` condition is false, the expression still processes a single instance of the element on the left paired against the element on the right, with the value null.</span></span>  
  
 <span data-ttu-id="b84a3-139">Оператор `RIGHT OUTER JOIN` можно выразить аналогичным способом.</span><span class="sxs-lookup"><span data-stu-id="b84a3-139">A `RIGHT OUTER JOIN` may be expressed in a similar manner.</span></span>  
  
#### <a name="full-outer-joins"></a><span data-ttu-id="b84a3-140">Полные внешние соединения</span><span class="sxs-lookup"><span data-stu-id="b84a3-140">Full Outer Joins</span></span>  
 <span data-ttu-id="b84a3-141">Явное соединение `FULL OUTER JOIN` формирует ограниченное декартово произведение двух коллекций, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b84a3-141">An explicit `FULL OUTER JOIN` produces a constrained Cartesian product of the two collections as illustrated in the following example:</span></span>  
  
 `FROM C AS c FULL OUTER JOIN D AS d ON e`  
  
 <span data-ttu-id="b84a3-142">Предшествующее выражение запроса обрабатывает сочетание каждого элемента коллекции слева, сопоставленного каждому элементу коллекции справа, где условие `ON` имеет значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="b84a3-142">The previous query expression processes a combination of every element of the collection on the left paired against every element of the collection on the right, where the `ON` condition is true.</span></span> <span data-ttu-id="b84a3-143">Если условие `ON` не выполняется, выражение все же обрабатывает один экземпляр элемента слева, поставленный в соответствие элементу справа, со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="b84a3-143">If the `ON` condition is false, the expression still processes one instance of the element on the left paired against the element on the right, with the value null.</span></span> <span data-ttu-id="b84a3-144">Выражение также обрабатывает один экземпляр элемента справа, сопоставленный с элементом слева, со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="b84a3-144">It also processes one instance of the element on the right paired against the element on the left, with the value null.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b84a3-145">Для сохранения совместимости с SQL-92, в Transact-SQL ключевое слово OUTER является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b84a3-145">To preserve compatibility with SQL-92, in Transact-SQL the OUTER keyword is optional.</span></span> <span data-ttu-id="b84a3-146">Поэтому `LEFT JOIN`, `RIGHT JOIN` и `FULL JOIN` являются синонимами для `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` и `FULL OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-146">Therefore, `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN` are synonyms for `LEFT OUTER JOIN`, `RIGHT OUTER JOIN`, and `FULL OUTER JOIN`.</span></span>  
  
### <a name="apply-clause-item"></a><span data-ttu-id="b84a3-147">Элемент предложения APPLY</span><span class="sxs-lookup"><span data-stu-id="b84a3-147">APPLY Clause Item</span></span>  
 <span data-ttu-id="b84a3-148">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] поддерживает два вида операторов`APPLY`: `CROSS APPLY` и `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-148">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports two kinds of `APPLY`: `CROSS APPLY` and `OUTER APPLY`.</span></span>  
  
 <span data-ttu-id="b84a3-149">`CROSS APPLY` формирует уникальную пару каждого элемента коллекции слева с элементом коллекции, полученным путем вычисления выражения справа.</span><span class="sxs-lookup"><span data-stu-id="b84a3-149">A `CROSS APPLY` produces a unique pairing of each element of the collection on the left with an element of the collection produced by evaluating the expression on the right.</span></span> <span data-ttu-id="b84a3-150">При использовании оператора `CROSS APPLY`, выражение справа функционально зависимо от элемента слева, как показано в следующем примере связанной коллекции:</span><span class="sxs-lookup"><span data-stu-id="b84a3-150">With a `CROSS APPLY`, the expression on the right is functionally dependent on the element on the left, as illustrated in the following associated collection example:</span></span>  
  
 `SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`  
  
 <span data-ttu-id="b84a3-151">Поведение `CROSS APPLY` аналогично поведению списка соединения.</span><span class="sxs-lookup"><span data-stu-id="b84a3-151">The behavior of `CROSS APPLY` is similar to the join list.</span></span> <span data-ttu-id="b84a3-152">Если выражение справа принимает значение пустой коллекции, оператор `CROSS APPLY` не формирует пар для этого экземпляра элемента слева.</span><span class="sxs-lookup"><span data-stu-id="b84a3-152">If the expression on the right evaluates to an empty collection, the `CROSS APPLY` produces no pairings for that instance of the element on the left.</span></span>  
  
 <span data-ttu-id="b84a3-153">Оператор `OUTER APPLY` похож на `CROSS APPLY`, но пары формируются, даже если выражение справа принимает значение пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="b84a3-153">An `OUTER APPLY` resembles a `CROSS APPLY`, except a pairing is still produced even when the expression on the right evaluates to an empty collection.</span></span> <span data-ttu-id="b84a3-154">Ниже приведен пример оператора `OUTER APPLY`:</span><span class="sxs-lookup"><span data-stu-id="b84a3-154">The following is an example of an `OUTER APPLY`:</span></span>  
  
 `SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`  
  
> [!NOTE]
>  <span data-ttu-id="b84a3-155">В отличие от в Transact-SQL, нет необходимости явного unnest шага в [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b84a3-155">Unlike in Transact-SQL, there is no need for an explicit unnest step in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b84a3-156">Операторы `CROSS` и `OUTER APPLY` появились в версии [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b84a3-156">`CROSS` and `OUTER APPLY` operators were introduced in [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="b84a3-157">В некоторых случаях конвейер запросов может сформировать код Transact-SQL, который содержит операторы `CROSS APPLY` и `OUTER APPLY`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-157">In some cases, the query pipeline might produce Transact-SQL that contains `CROSS APPLY` and/or `OUTER APPLY` operators.</span></span> <span data-ttu-id="b84a3-158">Так как некоторые внутренние поставщики, включая версии SQL Server более ранней, чем [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], не поддерживают данные операторы, эти запросы нельзя выполнить на данных поставщиках.</span><span class="sxs-lookup"><span data-stu-id="b84a3-158">Because some backend providers, including versions of SQL Server earlier than [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], do not support these operators, such queries cannot be executed on these backend providers.</span></span>  
>   
>  <span data-ttu-id="b84a3-159">Некоторыми типичными сценариями, которые бы могли привести к появлению операторов `CROSS APPLY` и (или) `OUTER APPLY` в выходном запросе, являются: связанный вложенный запрос с подкачкой страниц; AnyElement со связанным вложенным запросом или с коллекцией, полученной путем навигации; запросы LINQ, в которых используются методы группирования, принимающие селектор элементов; запрос, в котором явно указан оператор `CROSS APPLY` или `OUTER APPLY`; запрос с конструкцией `DEREF` для конструкции `REF`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-159">Some typical scenarios that might lead to the presence of `CROSS APPLY` and/or `OUTER APPLY` operators in the output query are the following: a correlated subquery with paging; AnyElement over a correlated subquery or over a collection produced by navigation; LINQ queries that use grouping methods that accept an element selector; a query in which a `CROSS APPLY` or an `OUTER APPLY` are explicitly specified; a query that has a `DEREF` construct over a `REF` construct.</span></span>  
  
## <a name="multiple-collections-in-the-from-clause"></a><span data-ttu-id="b84a3-160">Несколько коллекций в предложении FROM</span><span class="sxs-lookup"><span data-stu-id="b84a3-160">Multiple Collections in the FROM Clause</span></span>  
 <span data-ttu-id="b84a3-161">Предложение `FROM` может содержать одну и более коллекций, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="b84a3-161">The `FROM` clause can contain more than one collection separated by commas.</span></span> <span data-ttu-id="b84a3-162">В таких случаях коллекции считаются объединенными.</span><span class="sxs-lookup"><span data-stu-id="b84a3-162">In these cases, the collections are assumed to be joined together.</span></span> <span data-ttu-id="b84a3-163">Такую структуру можно считать n-сторонним соединением CROSS JOIN.</span><span class="sxs-lookup"><span data-stu-id="b84a3-163">Think of these as an n-way CROSS JOIN.</span></span>  
  
 <span data-ttu-id="b84a3-164">В следующем примере `C` и `D` являются независимыми коллекциями, но `c.Names` зависит от `C`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-164">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`.</span></span>  
  
```  
FROM C AS c, D AS d, c.Names AS e  
```  
  
 <span data-ttu-id="b84a3-165">Предыдущий пример логически эквивалентен следующему примеру:</span><span class="sxs-lookup"><span data-stu-id="b84a3-165">The previous example is logically equivalent to the following example:</span></span>  
  
 `FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`  
  
## <a name="left-correlation"></a><span data-ttu-id="b84a3-166">Левая корреляция</span><span class="sxs-lookup"><span data-stu-id="b84a3-166">Left Correlation</span></span>  
 <span data-ttu-id="b84a3-167">Элементы в предложении `FROM` могут ссылаться на элементы, указанные в более ранних предложениях.</span><span class="sxs-lookup"><span data-stu-id="b84a3-167">Items in the `FROM` clause can refer to items specified in earlier clauses.</span></span> <span data-ttu-id="b84a3-168">В следующем примере `C` и `D` являются независимыми коллекциями, но `c.Names` зависит от `C`:</span><span class="sxs-lookup"><span data-stu-id="b84a3-168">In the following example, `C` and `D` are independent collections, but `c.Names` is dependent on `C`:</span></span>  
  
```  
from C as c, D as d, c.Names as e  
```  
  
 <span data-ttu-id="b84a3-169">Это логически равносильно:</span><span class="sxs-lookup"><span data-stu-id="b84a3-169">This is logically equivalent to:</span></span>  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
## <a name="semantics"></a><span data-ttu-id="b84a3-170">Семантика</span><span class="sxs-lookup"><span data-stu-id="b84a3-170">Semantics</span></span>  
 <span data-ttu-id="b84a3-171">Логически предполагается, что коллекции в предложении `FROM` - часть `n`-стороннего перекрестного соединения (за исключением случая 1-стороннего перекрестного соединения).</span><span class="sxs-lookup"><span data-stu-id="b84a3-171">Logically, the collections in the `FROM` clause are assumed to be part of an `n`-way cross join (except in the case of a 1-way cross join).</span></span> <span data-ttu-id="b84a3-172">Псевдонимы в предложении `FROM` обрабатываются слева направо и добавляются в текущую область для последующего применения.</span><span class="sxs-lookup"><span data-stu-id="b84a3-172">Aliases in the `FROM` clause are processed left to right, and are added to the current scope for later reference.</span></span> <span data-ttu-id="b84a3-173">Предполагается, что предложение `FROM` формирует мультинабор строк.</span><span class="sxs-lookup"><span data-stu-id="b84a3-173">The `FROM` clause is assumed to produce a multiset of rows.</span></span> <span data-ttu-id="b84a3-174">В предложении `FROM` будет одно поле для каждого элемента, которое представляет единственный элемент из этого элемента сбора.</span><span class="sxs-lookup"><span data-stu-id="b84a3-174">There will be one field for each item in the `FROM` clause that represents a single element from that collection item.</span></span>  
  
 <span data-ttu-id="b84a3-175">Предложение `FROM` логически формирует мультинабор строк типа Row(c, d, e); при этом предполагается, что поля c, d и e являются элементами типа `C`, `D` и `c.Names`.</span><span class="sxs-lookup"><span data-stu-id="b84a3-175">The `FROM` clause logically produces a multiset of rows of type Row(c, d, e) where fields c, d, and e are assumed to be of the element type of `C`, `D`, and `c.Names`.</span></span>  
  
 <span data-ttu-id="b84a3-176">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] появился псевдоним для каждого простого элемента предложения `FROM` в области.</span><span class="sxs-lookup"><span data-stu-id="b84a3-176">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduces an alias for each simple `FROM` clause item in scope.</span></span> <span data-ttu-id="b84a3-177">Например, в следующем фрагменте предложения FROM в область введены имена c, d и e.</span><span class="sxs-lookup"><span data-stu-id="b84a3-177">For example, in the following FROM clause snippet, The names introduced into scope are c, d, and e.</span></span>  
  
```  
from (C as c join D as d) cross apply c.Names as e  
```  
  
 <span data-ttu-id="b84a3-178">В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (в отличие от Transact-SQL), `FROM` предложение только вводит псевдонимы в область действия.</span><span class="sxs-lookup"><span data-stu-id="b84a3-178">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (unlike Transact-SQL), the `FROM` clause only introduces the aliases into scope.</span></span> <span data-ttu-id="b84a3-179">Любые обращения к столбцам (свойствам) этих коллекций нужно уточнить с помощью псевдонима.</span><span class="sxs-lookup"><span data-stu-id="b84a3-179">Any references to columns (properties) of these collections must be qualified with the alias.</span></span>  
  
## <a name="pulling-up-keys-from-nested-queries"></a><span data-ttu-id="b84a3-180">Извлечение ключей из вложенных запросов</span><span class="sxs-lookup"><span data-stu-id="b84a3-180">Pulling Up Keys from Nested Queries</span></span>  
 <span data-ttu-id="b84a3-181">Определенные типы запросов, для которых требуется извлечь ключи из вложенного запроса, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b84a3-181">Certain types of queries that require pulling up keys from a nested query are not supported.</span></span> <span data-ttu-id="b84a3-182">Например, допустим следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="b84a3-182">For example, the following query is valid:</span></span>  
  
```  
select c.Orders from Customers as c   
```  
  
 <span data-ttu-id="b84a3-183">Однако следующий запрос является недопустимым, так как вложенный запрос не содержит ключей:</span><span class="sxs-lookup"><span data-stu-id="b84a3-183">However, the following query is not valid, because the nested query does not have any keys:</span></span>  
  
```  
select {1} from {2, 3}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b84a3-184">См. также</span><span class="sxs-lookup"><span data-stu-id="b84a3-184">See also</span></span>

- [<span data-ttu-id="b84a3-185">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b84a3-185">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="b84a3-186">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="b84a3-186">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
- [<span data-ttu-id="b84a3-187">Допускающие значения NULL структурированные типы</span><span class="sxs-lookup"><span data-stu-id="b84a3-187">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
