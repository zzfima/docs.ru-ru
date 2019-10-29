---
title: Создание кода SQL из деревьев команд. Рекомендации
ms.date: 03/30/2017
ms.assetid: 71ef6a24-4c4f-4254-af3a-ffc0d855b0a8
ms.openlocfilehash: 869722b91550855a184a74e706271c3e2d417b84
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040002"
---
# <a name="generating-sql-from-command-trees---best-practices"></a><span data-ttu-id="5e75a-102">Создание кода SQL из деревьев команд. Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5e75a-102">Generating SQL from Command Trees - Best Practices</span></span>

<span data-ttu-id="5e75a-103">Деревья команд выходного запроса по своей структуре близки к моделям запросов, выражаемым на языке SQL.</span><span class="sxs-lookup"><span data-stu-id="5e75a-103">Output query command trees closely model queries expressible in SQL.</span></span> <span data-ttu-id="5e75a-104">Однако модули записи поставщика при создании кода SQL на основе дерева команд выходного запроса сталкиваются с некоторыми распространенными проблемами.</span><span class="sxs-lookup"><span data-stu-id="5e75a-104">However, there are certain common challenges for provider writers when generating SQL from an output command tree.</span></span> <span data-ttu-id="5e75a-105">Они обсуждаются в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="5e75a-105">This topic discusses these challenges.</span></span> <span data-ttu-id="5e75a-106">В следующем разделе приводится образец поставщика, показывающий решение этих проблем.</span><span class="sxs-lookup"><span data-stu-id="5e75a-106">In the next topic, the sample provider shows how to address these challenges.</span></span>

## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a><span data-ttu-id="5e75a-107">Группирование узлов DbExpression в инструкции SELECT языка SQL</span><span class="sxs-lookup"><span data-stu-id="5e75a-107">Group DbExpression Nodes in a SQL SELECT Statement</span></span>

<span data-ttu-id="5e75a-108">Типичная инструкция SQL имеет вложенную структуру следующего вида:</span><span class="sxs-lookup"><span data-stu-id="5e75a-108">A typical SQL statement has a nested structure of the following shape:</span></span>

```sql
SELECT …
FROM …
WHERE …
GROUP BY …
ORDER BY …
```

<span data-ttu-id="5e75a-109">Одно или несколько предложений могут быть пустыми.</span><span class="sxs-lookup"><span data-stu-id="5e75a-109">One or more clauses may be empty.</span></span>  <span data-ttu-id="5e75a-110">Вложенная инструкция SELECT может находиться в любой строке.</span><span class="sxs-lookup"><span data-stu-id="5e75a-110">A nested SELECT statement could occur in any of the lines.</span></span>

<span data-ttu-id="5e75a-111">Результат преобразования дерева команд запроса в инструкцию SELECT языка SQL будет содержать по одному подзапросу на каждый реляционный оператор.</span><span class="sxs-lookup"><span data-stu-id="5e75a-111">A possible translation of a query command tree into a SQL SELECT statement would produce one subquery for every relational operator.</span></span> <span data-ttu-id="5e75a-112">Однако это приведет к возникновению излишних вложенных запросов, и в результате инструкцию будет трудно читать.</span><span class="sxs-lookup"><span data-stu-id="5e75a-112">However, that would lead to unnecessary nested subqueries that would be difficult to read.</span></span>  <span data-ttu-id="5e75a-113">В некоторых хранилищах данных производительность такого запроса будет низкой.</span><span class="sxs-lookup"><span data-stu-id="5e75a-113">On some data stores, the query may perform poorly.</span></span>

<span data-ttu-id="5e75a-114">В качестве примера рассмотрим следующее дерево команд запроса:</span><span class="sxs-lookup"><span data-stu-id="5e75a-114">As an example, consider the following query command tree</span></span>

```csharp
Project (
a.x,
   a = Filter(
      b.y = 5,
      b = Scan("TableA")
   )
)
```

<span data-ttu-id="5e75a-115">Неэффективное преобразование даст нам:</span><span class="sxs-lookup"><span data-stu-id="5e75a-115">An inefficient translation would produce:</span></span>

```sql
SELECT a.x
FROM (   SELECT *
         FROM TableA as b
         WHERE b.y = 5) as a
```

<span data-ttu-id="5e75a-116">Заметьте, что каждый узел реляционного выражения превращается в отдельную инструкцию SELECT языка SQL.</span><span class="sxs-lookup"><span data-stu-id="5e75a-116">Note that every relational expression node becomes a new SQL SELECT statement.</span></span>

<span data-ttu-id="5e75a-117">Следовательно, важно агрегировать как можно больше узлов выражений в одну инструкцию SELECT языка SQL, не нарушая правильности инструкции.</span><span class="sxs-lookup"><span data-stu-id="5e75a-117">Therefore, it is important to aggregate as many expression nodes as possible into a single SQL SELECT statement while preserving correctness.</span></span>

<span data-ttu-id="5e75a-118">Результат такого агрегирования для приведенного выше примера будет иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="5e75a-118">The result of such aggregation for the example presented above would be:</span></span>

```sql
SELECT b.x
FROM TableA as b
WHERE b.y = 5
```

## <a name="flatten-joins-in-a-sql-select-statement"></a><span data-ttu-id="5e75a-119">Уплощение соединений в инструкции SELECT языка SQL</span><span class="sxs-lookup"><span data-stu-id="5e75a-119">Flatten Joins in a SQL SELECT Statement</span></span>

<span data-ttu-id="5e75a-120">Частным случаем агрегирования нескольких узлов в одну инструкцию SELECT языка SQL является агрегирование нескольких выражений соединения.</span><span class="sxs-lookup"><span data-stu-id="5e75a-120">One case of aggregating multiple nodes into a single SQL SELECT statement is aggregating multiple join expressions into a single SQL SELECT statement.</span></span> <span data-ttu-id="5e75a-121">Класс DbJoinExpression представляет одно соединение между двумя исходными таблицами.</span><span class="sxs-lookup"><span data-stu-id="5e75a-121">DbJoinExpression represents a single join between two inputs.</span></span> <span data-ttu-id="5e75a-122">Но в одной инструкции SELECT языка SQL можно задать несколько соединений.</span><span class="sxs-lookup"><span data-stu-id="5e75a-122">However, as part of a single SQL SELECT statement, more than one join can be specified.</span></span> <span data-ttu-id="5e75a-123">В этом случае соединения выполняются в порядке, в котором они указаны.</span><span class="sxs-lookup"><span data-stu-id="5e75a-123">In that case the joins are performed in the order specified.</span></span>

<span data-ttu-id="5e75a-124">Левосторонние соединения (которые выглядят как левые дочерние другого соединения) проще сделать плоскими и превратить в одну инструкцию SELECT языка SQL.</span><span class="sxs-lookup"><span data-stu-id="5e75a-124">Left spine joins, (joins that appear as a left child of another join) can be more easily flattened into a single SQL SELECT statement.</span></span> <span data-ttu-id="5e75a-125">В качестве примера рассмотрим следующее дерево команд запроса:</span><span class="sxs-lookup"><span data-stu-id="5e75a-125">For example, consider the following query command tree:</span></span>

```csharp
InnerJoin(
   a = LeftOuterJoin(
   b = Extent("TableA")
   c = Extent("TableB")
   ON b.y = c.x ),
   d = Extent("TableC")
   ON a.b.y = d.z
)
```

<span data-ttu-id="5e75a-126">Оно верно переводится в следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="5e75a-126">This can be correctly translated into:</span></span>

```sql
SELECT *
FROM TableA as b
LEFT OUTER JOIN TableB as c ON b.y = c.x
INNER JOIN TableC as d ON b.y = d.z
```

<span data-ttu-id="5e75a-127">Однако соединения, не являющиеся левосторонними соединениями, невозможно легко превратить в плоскую структуру, и не следует пытаться это сделать.</span><span class="sxs-lookup"><span data-stu-id="5e75a-127">However, non-left spine joins cannot easily be flattened, and you should not try to flatten them.</span></span> <span data-ttu-id="5e75a-128">В качестве примера рассмотрим соединения в следующем дереве команд запроса:</span><span class="sxs-lookup"><span data-stu-id="5e75a-128">For example, the joins in the following query command tree:</span></span>

```csharp
InnerJoin(
   a = Extent("TableA")
   b = LeftOuterJoin(
   c = Extent("TableB")
   d = Extent("TableC")
   ON c.y = d.x),
   ON a.z = b.c.y
)
```

<span data-ttu-id="5e75a-129">Это дерево будет преобразовано в инструкцию SELECT языка SQL с подзапросом.</span><span class="sxs-lookup"><span data-stu-id="5e75a-129">Would be translated to a SQL SELECT statement with a sub-query.</span></span>

```sql
SELECT *
FROM TableA as a
INNER JOIN (SELECT *
   FROM TableB as c
   LEFT OUTER JOIN TableC as d
   ON c.y = d.x) as b
ON b.y = d.z
```

## <a name="input-alias-redirecting"></a><span data-ttu-id="5e75a-130">Перенаправление входных псевдонимов</span><span class="sxs-lookup"><span data-stu-id="5e75a-130">Input Alias Redirecting</span></span>

<span data-ttu-id="5e75a-131">Чтобы понять, что представляет собой перенаправление входных псевдонимов, рассмотрим структуру реляционных выражений, таких как DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression и DbSkipExpression.</span><span class="sxs-lookup"><span data-stu-id="5e75a-131">To explain input alias redirecting, consider the structure of the relational expressions, such as DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression, and DbSkipExpression.</span></span>

<span data-ttu-id="5e75a-132">Каждый из этих типов имеет одно или несколько свойств Input, описывающих входную коллекцию; для представления каждого элемента этого входа во время обхода коллекции используется переменная привязки, соответствующая данному элементу.</span><span class="sxs-lookup"><span data-stu-id="5e75a-132">Each of these types has one or more Input properties that describe an input collection, and a binding variable corresponding to each input is used to represent each element of that input during a collection traversal.</span></span> <span data-ttu-id="5e75a-133">Переменная привязки используется для ссылки на входной элемент, например в свойстве Predicate выражения DbFilterExpression или свойстве Projection выражения DbProjectExpression.</span><span class="sxs-lookup"><span data-stu-id="5e75a-133">The binding variable is used when referring to the input element, for example in the Predicate property of a DbFilterExpression or the Projection property of a DbProjectExpression.</span></span>

<span data-ttu-id="5e75a-134">При агрегировании большего числа узлов реляционных выражений в одну инструкцию SELECT языка SQL и вычислении выражения, являющегося частью реляционного выражения (например, свойства Projection выражения DbProjectExpression), используемая переменная привязки может не совпадать с псевдонимом входного значения, так как несколько привязок выражений будут перенаправлены в один и тот же экстент.</span><span class="sxs-lookup"><span data-stu-id="5e75a-134">When aggregating more relational expression nodes into a single SQL SELECT statement, and evaluating an expression that is part of a relational expression (for example part of the Projection property of a DbProjectExpression) the binding variable that it uses may not be the same as the alias of the input, as multiple expression bindings would have to be redirected to a single extent.</span></span>  <span data-ttu-id="5e75a-135">Эта проблема называется переименованием псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="5e75a-135">This problem is called alias renaming.</span></span>

<span data-ttu-id="5e75a-136">Рассмотрим первый пример данного раздела.</span><span class="sxs-lookup"><span data-stu-id="5e75a-136">Consider the first example in this topic.</span></span> <span data-ttu-id="5e75a-137">При примитивном преобразовании Projection a.x (DbPropertyExpression(a, x)) правильно будет преобразовать в `a.x`, поскольку мы создали псевдоним входного значения «a» для соответствия переменной привязки.</span><span class="sxs-lookup"><span data-stu-id="5e75a-137">If doing the naïve translation and translating the Projection a.x (DbPropertyExpression(a, x)), it is correct to translate it into `a.x` because we have aliased the input as "a" to match the binding variable.</span></span>  <span data-ttu-id="5e75a-138">Однако при агрегировании обоих узлов в единую инструкцию SELECT языка SQL то же выражение DbPropertyExpression следует преобразовать в `b.x`, так как для входного значения был задан псевдоним «b».</span><span class="sxs-lookup"><span data-stu-id="5e75a-138">However, when aggregating both the nodes into a single SQL SELECT statement, you need to translate the same DbPropertyExpression into `b.x`, as the input has been aliased with "b".</span></span>

## <a name="join-alias-flattening"></a><span data-ttu-id="5e75a-139">Преобразование псевдонимов соединений в плоские</span><span class="sxs-lookup"><span data-stu-id="5e75a-139">Join Alias Flattening</span></span>

<span data-ttu-id="5e75a-140">В отличие от любых других реляционных выражений в дереве выходных команд, результирующим типом для выражения DbJoinExpression является строка, состоящая из двух столбцов, каждый из которых соответствует одному из входов.</span><span class="sxs-lookup"><span data-stu-id="5e75a-140">Unlike any other relational expression in an output command tree, the DbJoinExpression outputs a result type that is a row consisting of two columns, each of which corresponds to one of the inputs.</span></span> <span data-ttu-id="5e75a-141">При построении Дбпропертекспрессион для доступа к скалярному свойству, полученному из объединения, оно находится над другим Дбпропертекспрессион.</span><span class="sxs-lookup"><span data-stu-id="5e75a-141">When a DbPropertyExpression is built to access a scalar property originating from a join, it is over another DbPropertyExpression.</span></span>

<span data-ttu-id="5e75a-142">Например, можно указать «a.b.y» в примере 2 и «b.c.y» в примере 3.</span><span class="sxs-lookup"><span data-stu-id="5e75a-142">Examples include "a.b.y" in example 2 and "b.c.y" in example 3.</span></span> <span data-ttu-id="5e75a-143">Однако в соответствующих инструкциях SQL они именуются «b.y».</span><span class="sxs-lookup"><span data-stu-id="5e75a-143">However in the corresponding SQL statements these are referred as "b.y".</span></span> <span data-ttu-id="5e75a-144">Такое присвоение новых псевдонимов называется уплощением псевдонимов соединений.</span><span class="sxs-lookup"><span data-stu-id="5e75a-144">This re-aliasing is called join alias flattening.</span></span>

## <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="5e75a-145">Переименование столбцов и псевдонимов экстентов</span><span class="sxs-lookup"><span data-stu-id="5e75a-145">Column Name and Extent Alias Renaming</span></span>

<span data-ttu-id="5e75a-146">Если запрос SELECT языка SQL, содержащий соединение, должен быть выполнен в проекции, то при перечислении всех участвующих в запросе столбцов из входных таблиц может произойти коллизия имен, так как имена столбцов во входных таблицах могут совпадать.</span><span class="sxs-lookup"><span data-stu-id="5e75a-146">If a SQL SELECT query that has a join has to be completed with a projection, when enumerating all the participating columns from the inputs, a name collision may occur, as more than one input may have the same column name.</span></span> <span data-ttu-id="5e75a-147">Чтобы избежать коллизии, следует использовать для столбца другое имя.</span><span class="sxs-lookup"><span data-stu-id="5e75a-147">Use a different name for the column to avoid the collision.</span></span>

<span data-ttu-id="5e75a-148">Кроме того, при уплощении соединений участвующие в запросе таблицы (или вложенные запросы) могут содержать конфликтующие псевдонимы. В таком случае эти псевдонимы следует переименовать.</span><span class="sxs-lookup"><span data-stu-id="5e75a-148">Also, when flattening joins, participating tables (or subqueries) may have colliding aliases in which case these need to be renamed.</span></span>

## <a name="avoid-select-"></a><span data-ttu-id="5e75a-149">Предотвращение применения инструкции SELECT \*</span><span class="sxs-lookup"><span data-stu-id="5e75a-149">Avoid SELECT \*</span></span>

<span data-ttu-id="5e75a-150">Не следует использовать оператор `SELECT *` для выборки из базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="5e75a-150">Do not use `SELECT *` to select from base tables.</span></span> <span data-ttu-id="5e75a-151">Модель хранения в Entity Framework приложении может включать только подмножество столбцов, которые находятся в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="5e75a-151">The storage model in an Entity Framework application may only include a subset of the columns that are in the database table.</span></span> <span data-ttu-id="5e75a-152">В этом случае оператор `SELECT *` может выдать неверный результат.</span><span class="sxs-lookup"><span data-stu-id="5e75a-152">In this case, `SELECT *` may produce an incorrect result.</span></span> <span data-ttu-id="5e75a-153">Вместо этого следует указать все столбцы, участвующие в запросе, по именам столбцов из результирующего типа выражений, участвующих в запросе.</span><span class="sxs-lookup"><span data-stu-id="5e75a-153">Instead, you should specify all participating columns by using the column names from the result type of the participating expressions.</span></span>

## <a name="reuse-of-expressions"></a><span data-ttu-id="5e75a-154">Повторное использование выражений</span><span class="sxs-lookup"><span data-stu-id="5e75a-154">Reuse of Expressions</span></span>

<span data-ttu-id="5e75a-155">Выражения можно повторно использовать в дереве команд запроса, переданном Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="5e75a-155">Expressions may be reused in the query command tree passed by the Entity Framework.</span></span> <span data-ttu-id="5e75a-156">Не следует предполагать, что каждое выражение появляется в дереве команд запроса только один раз.</span><span class="sxs-lookup"><span data-stu-id="5e75a-156">Do not assume that each expression appears only once in the query command tree.</span></span>

## <a name="mapping-primitive-types"></a><span data-ttu-id="5e75a-157">Сопоставление примитивных типов</span><span class="sxs-lookup"><span data-stu-id="5e75a-157">Mapping Primitive Types</span></span>

<span data-ttu-id="5e75a-158">При сопоставлении концептуальных типов (типов модели EDM) с типами поставщика следует проводить сопоставление с самым большим типом (Int32), чтобы поместились все возможные значения.</span><span class="sxs-lookup"><span data-stu-id="5e75a-158">When mapping conceptual (EDM) types to provider types, you should map to the widest type (Int32) so that all possible values fit.</span></span> <span data-ttu-id="5e75a-159">Кроме того, Избегайте сопоставления с типами, которые не могут использоваться для многих операций, таких как типы больших двоичных объектов (например, `ntext` в SQL Server).</span><span class="sxs-lookup"><span data-stu-id="5e75a-159">Also, avoid mapping to types that cannot be used for many operations, like BLOB types (for example, `ntext` in SQL Server).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e75a-160">См. также</span><span class="sxs-lookup"><span data-stu-id="5e75a-160">See also</span></span>

- [<span data-ttu-id="5e75a-161">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="5e75a-161">SQL Generation</span></span>](sql-generation.md)
