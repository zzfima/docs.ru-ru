---
title: Основные операции запросов LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
ms.openlocfilehash: 91c038303c1ad7c2530964d3102aae49090c4c2a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635942"
---
# <a name="basic-linq-query-operations-c"></a><span data-ttu-id="d7ca4-102">Основные операции запросов LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="d7ca4-102">Basic LINQ Query Operations (C#)</span></span>
<span data-ttu-id="d7ca4-103">В этом разделе содержится краткое описание выражений запроса LINQ и некоторые типичные операции, выполняемые в запросе.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-103">This topic gives a brief introduction to LINQ query expressions and some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="d7ca4-104">Более подробные сведения приводятся в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d7ca4-104">More detailed information is in the following topics:</span></span>  
  
 [<span data-ttu-id="d7ca4-105">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="d7ca4-105">LINQ Query Expressions</span></span>](../../../linq/index.md)  
  
 [<span data-ttu-id="d7ca4-106">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="d7ca4-106">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)  
  
 [<span data-ttu-id="d7ca4-107">Пошаговое руководство: Написание запросов на C#</span><span class="sxs-lookup"><span data-stu-id="d7ca4-107">Walkthrough: Writing Queries in C#</span></span>](./walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
> <span data-ttu-id="d7ca4-108">Если вы уже знакомы с языком запросов, таким как SQL или XQuery, можно пропустить большую часть этого раздела.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-108">If you already are familiar with a query language such as SQL or XQuery, you can skip most of this topic.</span></span> <span data-ttu-id="d7ca4-109">Чтобы изучить порядок предложений в выражениях запроса LINQ, прочитайте о "предложении `from`" в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-109">Read about the "`from` clause" in the next section to learn about the order of clauses in LINQ query expressions.</span></span>  
  
## <a name="obtaining-a-data-source"></a><span data-ttu-id="d7ca4-110">Получение источника данных</span><span class="sxs-lookup"><span data-stu-id="d7ca4-110">Obtaining a Data Source</span></span>  
 <span data-ttu-id="d7ca4-111">В первую очередь в запросе LINQ нужно указать источник данных.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-111">In a LINQ query, the first step is to specify the data source.</span></span> <span data-ttu-id="d7ca4-112">В C#, как и в большинстве языков программирования, переменная должна быть объявлена до ее использования.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-112">In C# as in most programming languages a variable must be declared before it can be used.</span></span> <span data-ttu-id="d7ca4-113">В запросе LINQ первым идет предложение `from` для указания источника данных (`customers`) и *переменная диапазона* (`cust`).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-113">In a LINQ query, the `from` clause comes first in order to introduce the data source (`customers`) and the *range variable* (`cust`).</span></span>  
  
 [!code-csharp[csLINQGettingStarted#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#23)]  
  
 <span data-ttu-id="d7ca4-114">Переменная диапазона схожа с переменной итерации в цикле `foreach` за исключением того, что в выражении запроса не происходит фактической итерации.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-114">The range variable is like the iteration variable in a `foreach` loop except that no actual iteration occurs in a query expression.</span></span> <span data-ttu-id="d7ca4-115">При выполнении запроса переменная диапазона будет использоваться как ссылка на каждый последующий элемент в `customers`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-115">When the query is executed, the range variable will serve as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="d7ca4-116">Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="d7ca4-117">Дополнительные переменные диапазона могут быть введены предложением `let`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-117">Additional range variables can be introduced by a `let` clause.</span></span> <span data-ttu-id="d7ca4-118">Дополнительные сведения см. в разделе [Предложение let](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-118">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7ca4-119">Для неуниверсальных источников данных, таких как <xref:System.Collections.ArrayList>, переменная диапазона должна быть явно типизирована.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-119">For non-generic data sources such as <xref:System.Collections.ArrayList>, the range variable must be explicitly typed.</span></span> <span data-ttu-id="d7ca4-120">Дополнительные сведения см. в разделах [Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) и [Предложение from](../../../language-reference/keywords/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-120">For more information, see [How to query an ArrayList with LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) and [from clause](../../../language-reference/keywords/from-clause.md).</span></span>  
  
## <a name="filtering"></a><span data-ttu-id="d7ca4-121">Фильтрация</span><span class="sxs-lookup"><span data-stu-id="d7ca4-121">Filtering</span></span>  
 <span data-ttu-id="d7ca4-122">По-видимому, одной из наиболее распространенных операций с запросом является применение фильтра в форме логического выражения.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-122">Probably the most common query operation is to apply a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="d7ca4-123">Фильтр приводит к возвращению запросом только тех элементов, для которых выражение является истинным.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-123">The filter causes the query to return only those elements for which the expression is true.</span></span> <span data-ttu-id="d7ca4-124">Результат вырабатывается с использованием предложения `where`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-124">The result is produced by using the `where` clause.</span></span> <span data-ttu-id="d7ca4-125">Фильтр фактически указывает элементы для исключения из исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-125">The filter in effect specifies which elements to exclude from the source sequence.</span></span> <span data-ttu-id="d7ca4-126">В приведенном ниже примере возвращаются только те элементы `customers`, которые находятся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-126">In the following example, only those `customers` who have an address in London are returned.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#24)]  
  
 <span data-ttu-id="d7ca4-127">Для применения нужного числа выражений фильтра в предложении `where` можно использовать знакомые логические операторы C# `AND` и `OR`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-127">You can use the familiar C# logical `AND` and `OR` operators to apply as many filter expressions as necessary in the `where` clause.</span></span> <span data-ttu-id="d7ca4-128">Например, для получения только заказчиков из Лондона `AND` с именем Devon следует написать следующий код:</span><span class="sxs-lookup"><span data-stu-id="d7ca4-128">For example, to return only customers from "London" `AND` whose name is "Devon" you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#25)]  
  
 <span data-ttu-id="d7ca4-129">Для получения заказчиков из Лондона или Парижа следует написать следующий код:</span><span class="sxs-lookup"><span data-stu-id="d7ca4-129">To return customers from London or Paris, you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#26)]  
  
 <span data-ttu-id="d7ca4-130">Дополнительные сведения см. в разделе [Предложение where](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-130">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="ordering"></a><span data-ttu-id="d7ca4-131">Упорядочение</span><span class="sxs-lookup"><span data-stu-id="d7ca4-131">Ordering</span></span>  
 <span data-ttu-id="d7ca4-132">Часто целесообразно отсортировать возвращенные данные.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-132">Often it is convenient to sort the returned data.</span></span> <span data-ttu-id="d7ca4-133">Предложение `orderby` сортирует элементы возвращаемой последовательности в зависимости от компаратора по умолчанию для сортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-133">The `orderby` clause will cause the elements in the returned sequence to be sorted according to the default comparer for the type being sorted.</span></span> <span data-ttu-id="d7ca4-134">Например, приведенный ниже запрос можно расширить для сортировки результатов на основе свойства `Name`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-134">For example, the following query can be extended to sort the results based on the `Name` property.</span></span> <span data-ttu-id="d7ca4-135">Так как `Name` является строкой, сравнение по умолчанию выполняется в алфавитном порядке от А до Я.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-135">Because `Name` is a string, the default comparer performs an alphabetical sort from A to Z.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#27)]  
  
 <span data-ttu-id="d7ca4-136">Для упорядочения результатов в обратном порядке от Я до А используется предложение `orderby…descending`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-136">To order the results in reverse order, from Z to A, use the `orderby…descending` clause.</span></span>  
  
 <span data-ttu-id="d7ca4-137">Дополнительные сведения см. в разделе [Предложение orderby](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-137">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
## <a name="grouping"></a><span data-ttu-id="d7ca4-138">Группирование</span><span class="sxs-lookup"><span data-stu-id="d7ca4-138">Grouping</span></span>  
 <span data-ttu-id="d7ca4-139">Предложение `group` позволяет группировать результаты на основе указанного ключа.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-139">The `group` clause enables you to group your results based on a key that you specify.</span></span> <span data-ttu-id="d7ca4-140">Например, можно указать, что результаты должны быть сгруппированы по `City` так, чтобы все заказчики из Лондона или Парижа оказались в отдельных группах.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-140">For example you could specify that the results should be grouped by the `City` so that all customers from London or Paris are in individual groups.</span></span> <span data-ttu-id="d7ca4-141">В этом случае ключом является `cust.City`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-141">In this case, `cust.City` is the key.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#28)]  
  
 <span data-ttu-id="d7ca4-142">Когда запрос завершается предложением `group`, результаты представляются в виде списка из списков.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-142">When you end a query with a `group` clause, your results take the form of a list of lists.</span></span> <span data-ttu-id="d7ca4-143">Каждый элемент в списке является объектом, имеющим член `Key` и список элементов, сгруппированных по этому ключу.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-143">Each element in the list is an object that has a `Key` member and a list of elements that are grouped under that key.</span></span> <span data-ttu-id="d7ca4-144">При итерации запроса, создающего последовательность групп, необходимо использовать вложенный цикл `foreach`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-144">When you iterate over a query that produces a sequence of groups, you must use a nested `foreach` loop.</span></span> <span data-ttu-id="d7ca4-145">Внешний цикл выполняет итерацию каждой группы, а внутренний цикл — итерацию членов каждой группы.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-145">The outer loop iterates over each group, and the inner loop iterates over each group's members.</span></span>  
  
 <span data-ttu-id="d7ca4-146">Если необходимо ссылаться на результаты операции группировки, можно использовать ключевое слово `into` для создания идентификатора, который можно будет запрашивать.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-146">If you must refer to the results of a group operation, you can use the `into` keyword to create an identifier that can be queried further.</span></span> <span data-ttu-id="d7ca4-147">Приведенный ниже запрос возвращает только те группы, которые содержат более двух заказчиков.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-147">The following query returns only those groups that contain more than two customers:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#29)]  
  
 <span data-ttu-id="d7ca4-148">Дополнительные сведения см. в разделе [Предложение group](../../../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-148">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="joining"></a><span data-ttu-id="d7ca4-149">Соединение</span><span class="sxs-lookup"><span data-stu-id="d7ca4-149">Joining</span></span>  
 <span data-ttu-id="d7ca4-150">Операции соединения создают связи между последовательностями, неявно смоделированными в источниках данных.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-150">Join operations create associations between sequences that are not explicitly modeled in the data sources.</span></span> <span data-ttu-id="d7ca4-151">Например, можно выполнить соединение для поиска всех клиентов и дистрибьюторов, которые находятся в одном месте.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-151">For example you can perform a join to find all the customers and distributors who have the same location.</span></span> <span data-ttu-id="d7ca4-152">В LINQ предложение `join` всегда работает с коллекциями объектов, а не непосредственно с таблицами базы данных.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-152">In LINQ the `join` clause always works against object collections instead of database tables directly.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#36)]  
  
 <span data-ttu-id="d7ca4-153">В LINQ нет необходимости использовать `join` так часто, как в SQL, так как внешние ключи в LINQ представлены в объектной модели свойствами, содержащими коллекцию элементов.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-153">In LINQ, you do not have to use `join` as often as you do in SQL, because foreign keys in LINQ are represented in the object model as properties that hold a collection of items.</span></span> <span data-ttu-id="d7ca4-154">Например, объект `Customer` содержит коллекцию объектов `Order`.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-154">For example, a `Customer` object contains a collection of `Order` objects.</span></span> <span data-ttu-id="d7ca4-155">Вместо выполнения соединения доступ к заказам можно получить с помощью точечной нотации.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-155">Rather than performing a join, you access the orders by using dot notation:</span></span>  
  
```csharp
from order in Customer.Orders...  
```  
  
 <span data-ttu-id="d7ca4-156">Дополнительные сведения см. в разделе [Предложение join](../../../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-156">For more information, see [join clause](../../../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="selecting-projections"></a><span data-ttu-id="d7ca4-157">Выбор (проецирование)</span><span class="sxs-lookup"><span data-stu-id="d7ca4-157">Selecting (Projections)</span></span>  
 <span data-ttu-id="d7ca4-158">Предложение `select` создает результаты запроса и задает форму или тип каждого возвращаемого элемента.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-158">The `select` clause produces the results of the query and specifies the "shape" or type of each returned element.</span></span> <span data-ttu-id="d7ca4-159">Например, можно указать, будут ли результаты состоять из полных объектов `Customer`, только из одного члена, подмножества членов или некоторых совершенно других типов, на основе вычислений или создания новых объектов.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-159">For example, you can specify whether your results will consist of complete `Customer` objects, just one member, a subset of members, or some completely different result type based on a computation or new object creation.</span></span> <span data-ttu-id="d7ca4-160">Когда предложение `select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-160">When the `select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span> <span data-ttu-id="d7ca4-161">Использование проекций для преобразования данных является эффективной возможностью выражений запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="d7ca4-161">The use of projections to transform data is a powerful capability of LINQ query expressions.</span></span> <span data-ttu-id="d7ca4-162">Дополнительные сведения см. в разделах [Преобразования данных с помощью LINQ (C#)](./data-transformations-with-linq.md) и [Предложение select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca4-162">For more information, see [Data Transformations with LINQ (C#)](./data-transformations-with-linq.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ca4-163">См. также</span><span class="sxs-lookup"><span data-stu-id="d7ca4-163">See also</span></span>

- [<span data-ttu-id="d7ca4-164">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="d7ca4-164">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="d7ca4-165">Пошаговое руководство: Написание запросов на C#</span><span class="sxs-lookup"><span data-stu-id="d7ca4-165">Walkthrough: Writing Queries in C#</span></span>](./walkthrough-writing-queries-linq.md)
- [<span data-ttu-id="d7ca4-166">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d7ca4-166">Query Keywords (LINQ)</span></span>](../../../language-reference/keywords/query-keywords.md)
- [<span data-ttu-id="d7ca4-167">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="d7ca4-167">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
