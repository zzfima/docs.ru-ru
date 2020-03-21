---
title: Основные операции запроса
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266382"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="0407f-102">Основные операции запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0407f-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="0407f-103">Эта тема содержит краткое введение в выражения Language-Integrated Query (LIN') в Visual Basic и некоторые типичные виды операций, выполняемых в запросе.</span><span class="sxs-lookup"><span data-stu-id="0407f-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="0407f-104">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="0407f-104">For more information, see the following topics:</span></span>  
  
 <span data-ttu-id="0407f-105">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0407f-105">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
  
 [<span data-ttu-id="0407f-106">Запросов</span><span class="sxs-lookup"><span data-stu-id="0407f-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="0407f-107">Пошаговое руководство. Написание запросов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0407f-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="0407f-108">Определение источника данных (от)</span><span class="sxs-lookup"><span data-stu-id="0407f-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="0407f-109">В запросе LIN'а первым шагом является указание источника данных, который необходимо заказать.</span><span class="sxs-lookup"><span data-stu-id="0407f-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="0407f-110">Таким образом, `From` пункт в запросе всегда на первом месте.</span><span class="sxs-lookup"><span data-stu-id="0407f-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="0407f-111">Операторы запросов выбирают и формируют результат в зависимости от типа источника.</span><span class="sxs-lookup"><span data-stu-id="0407f-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="0407f-112">В `From` пункте указывается источник `customers`данных и *переменная диапазона*. `cust`</span><span class="sxs-lookup"><span data-stu-id="0407f-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="0407f-113">Переменная диапазона подобна переменной итерации цикла, за исключением того, что в выражении запроса не происходит фактической итерации.</span><span class="sxs-lookup"><span data-stu-id="0407f-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="0407f-114">При выполнении запроса, часто с `For Each` помощью цикла, переменная диапазона служит `customers`отсылкой к каждому последующем элементу в .</span><span class="sxs-lookup"><span data-stu-id="0407f-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="0407f-115">Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде.</span><span class="sxs-lookup"><span data-stu-id="0407f-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="0407f-116">Для примеров запросов, написанных с [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)явным ввозами и без нее, см.</span><span class="sxs-lookup"><span data-stu-id="0407f-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="0407f-117">Для получения дополнительной информации `From` о том, как использовать положение в Visual Basic, см. [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0407f-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="0407f-118">Фильтрация данных (Где)</span><span class="sxs-lookup"><span data-stu-id="0407f-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="0407f-119">Вероятно, наиболее распространенной операцией запроса является применение фильтра в виде выражения Boolean.</span><span class="sxs-lookup"><span data-stu-id="0407f-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="0407f-120">Затем запрос возвращает только те элементы, для которых выражение верно.</span><span class="sxs-lookup"><span data-stu-id="0407f-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="0407f-121">Для `Where` выполнения фильтрации используется пункт.</span><span class="sxs-lookup"><span data-stu-id="0407f-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="0407f-122">Фильтр определяет, какие элементы в источнике данных следует включить в результирующую последовательность.</span><span class="sxs-lookup"><span data-stu-id="0407f-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="0407f-123">В следующем примере включены только те клиенты, у которых есть адрес в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="0407f-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="0407f-124">Можно использовать логических `And` операторов, таких как `Or` `Where` и комбинировать выражения фильтра в оговорке.</span><span class="sxs-lookup"><span data-stu-id="0407f-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="0407f-125">Например, чтобы вернуть только тех клиентов, которые из Лондона и чье имя Девон, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0407f-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="0407f-126">Чтобы вернуть клиентов из Лондона или Парижа, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="0407f-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="0407f-127">Для получения дополнительной информации `Where` о том, как использовать положение в Visual Basic, см. [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0407f-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="0407f-128">Заказ данных (Заказ)</span><span class="sxs-lookup"><span data-stu-id="0407f-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="0407f-129">Часто удобно сортировать возвращенные данные в определенный заказ.</span><span class="sxs-lookup"><span data-stu-id="0407f-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="0407f-130">Это `Order By` положение приведет к тому, что элементы в возвращенной последовательности будут сортироваться по определенному полю или полям.</span><span class="sxs-lookup"><span data-stu-id="0407f-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="0407f-131">Например, следующий запрос сортирует `Name` результаты на основе свойства.</span><span class="sxs-lookup"><span data-stu-id="0407f-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="0407f-132">Поскольку `Name` строка является строкой, возвращенные данные будут отсортированы в алфавитном порядке, от А до Я.</span><span class="sxs-lookup"><span data-stu-id="0407f-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="0407f-133">Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="0407f-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="0407f-134">По `Ascending` умолчанию, `Ascending` `Descending` когда ни один и не указан.</span><span class="sxs-lookup"><span data-stu-id="0407f-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="0407f-135">Для получения дополнительной информации `Order By` о том, как использовать положение в Visual Basic, см. [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0407f-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="0407f-136">Выбор данных (выбрать)</span><span class="sxs-lookup"><span data-stu-id="0407f-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="0407f-137">В `Select` этом положении оговаривается форма и содержание возвращенных элементов.</span><span class="sxs-lookup"><span data-stu-id="0407f-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="0407f-138">Например, можно указать, будут ли `Customer` результаты `Customer` состоять из полных объектов, только одного свойства, подмноза свойств, комбинации свойств из различных источников данных или какого-либо нового типа результатов, основанного на вычислениях.</span><span class="sxs-lookup"><span data-stu-id="0407f-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="0407f-139">Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.</span><span class="sxs-lookup"><span data-stu-id="0407f-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="0407f-140">Чтобы получить коллекцию, состоящую из полных `Customer` объектов, выберите сам упор диапазона:</span><span class="sxs-lookup"><span data-stu-id="0407f-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="0407f-141">Если `Customer` экземпляр — это большой объект, который имеет много полей, и все, что вы хотите получить, это имя, вы можете выбрать, `cust.Name`как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0407f-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="0407f-142">Вывод локального типа признает, что это изменяет `Customer` тип результата из коллекции объектов в коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="0407f-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="0407f-143">Чтобы выбрать несколько полей из источника данных, у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="0407f-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="0407f-144">В `Select` пункте укажите поля, которые вы хотите включить в результат.</span><span class="sxs-lookup"><span data-stu-id="0407f-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="0407f-145">Компилятор определит анонимный тип, который имеет эти поля в качестве своих свойств.</span><span class="sxs-lookup"><span data-stu-id="0407f-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="0407f-146">Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="0407f-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="0407f-147">Поскольку возвращенные элементы в следующем примере являются экземплярами анонимного типа, вы не можете ссылаться на тип по имени в другом месте кода.</span><span class="sxs-lookup"><span data-stu-id="0407f-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="0407f-148">Имя, обозначенное компилятором для типа, содержит символы, которые не действительны в обычном базовом коде Visual.</span><span class="sxs-lookup"><span data-stu-id="0407f-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="0407f-149">В следующем примере элементы в коллекции, которые `londonCusts4` возвращаются запросом, являются экземплярами анонимного типа</span><span class="sxs-lookup"><span data-stu-id="0407f-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="0407f-150">-или-</span><span class="sxs-lookup"><span data-stu-id="0407f-150">-or-</span></span>  
  
- <span data-ttu-id="0407f-151">Определите тип имени, содержащий определенные поля, которые необходимо включить в результат, и создайте и инициализировать экземпляры типа в предложении. `Select`</span><span class="sxs-lookup"><span data-stu-id="0407f-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="0407f-152">Используйте эту опцию только в том случае, если вам необходимо использовать отдельные результаты за пределами коллекции, в которые они возвращаются, или если вы должны передать их в качестве параметров в вызовах метода.</span><span class="sxs-lookup"><span data-stu-id="0407f-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="0407f-153">Тип `londonCusts5` в следующем примере IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="0407f-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="0407f-154">Для получения дополнительной информации `Select` о том, как использовать положение в Visual Basic, см. [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0407f-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="0407f-155">Присоединение к данным (присоединение и присоединение к группе)</span><span class="sxs-lookup"><span data-stu-id="0407f-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="0407f-156">Можно объединить несколько источников `From` данных в пункте несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="0407f-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="0407f-157">Например, в следующем коде используются два источника данных и неявно сочетается свойства из обоих.</span><span class="sxs-lookup"><span data-stu-id="0407f-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="0407f-158">Запрос выбирает студентов, фамилии которых начинаются с гласной.</span><span class="sxs-lookup"><span data-stu-id="0407f-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="0407f-159">Вы можете запустить этот код со списком студентов, созданным в [Как: Создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="0407f-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="0407f-160">Ключевое `Join` слово эквивалентно `INNER JOIN` в S'L.</span><span class="sxs-lookup"><span data-stu-id="0407f-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="0407f-161">Он сочетает в себе две коллекции на основе сопоставления ключевых значений между элементами в двух коллекциях.</span><span class="sxs-lookup"><span data-stu-id="0407f-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="0407f-162">Запрос возвращает все или часть элементов коллекции, которые соответствуют ключевым значениям.</span><span class="sxs-lookup"><span data-stu-id="0407f-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="0407f-163">Например, следующий код дублирует действие предыдущего неявного соединения.</span><span class="sxs-lookup"><span data-stu-id="0407f-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="0407f-164">`Group Join`объединяет коллекции в единую иерархическую `LEFT JOIN` коллекцию, как и в S'L.</span><span class="sxs-lookup"><span data-stu-id="0407f-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="0407f-165">Для получения дополнительной информации [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) [см.](../../../../visual-basic/language-reference/queries/join-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0407f-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="0407f-166">Данные по группировке (группа by)</span><span class="sxs-lookup"><span data-stu-id="0407f-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="0407f-167">Можно добавить `Group By` пункт для группы элементов в результате запроса в соответствии с одним или несколько полями элементов.</span><span class="sxs-lookup"><span data-stu-id="0407f-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="0407f-168">Например, следующий код группирует студентов по годам занятий.</span><span class="sxs-lookup"><span data-stu-id="0407f-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="0407f-169">Если вы запустите этот код, используя список студентов, созданный в `For Each` [Как: Создать список элементов,](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)выход из оператора:</span><span class="sxs-lookup"><span data-stu-id="0407f-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="0407f-170">Год: Младший</span><span class="sxs-lookup"><span data-stu-id="0407f-170">Year: Junior</span></span>  
  
 <span data-ttu-id="0407f-171">Такер, Майкл</span><span class="sxs-lookup"><span data-stu-id="0407f-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="0407f-172">Гарсия, Хьюго</span><span class="sxs-lookup"><span data-stu-id="0407f-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="0407f-173">Гарсия, Дебра</span><span class="sxs-lookup"><span data-stu-id="0407f-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="0407f-174">Такер, Лэнс</span><span class="sxs-lookup"><span data-stu-id="0407f-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="0407f-175">Год: Старший</span><span class="sxs-lookup"><span data-stu-id="0407f-175">Year: Senior</span></span>  
  
 <span data-ttu-id="0407f-176">Омельченко, Светлана</span><span class="sxs-lookup"><span data-stu-id="0407f-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="0407f-177">Осада, Митико</span><span class="sxs-lookup"><span data-stu-id="0407f-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="0407f-178">Факхури, Фади</span><span class="sxs-lookup"><span data-stu-id="0407f-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="0407f-179">Фэн, Ханайинг</span><span class="sxs-lookup"><span data-stu-id="0407f-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="0407f-180">Адамс, Терри</span><span class="sxs-lookup"><span data-stu-id="0407f-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="0407f-181">Год: Первокурсник</span><span class="sxs-lookup"><span data-stu-id="0407f-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="0407f-182">Мортенсен, Свен</span><span class="sxs-lookup"><span data-stu-id="0407f-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="0407f-183">Гарсия, Сезар</span><span class="sxs-lookup"><span data-stu-id="0407f-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="0407f-184">Вариации, показанные в следующем коде, заказируют классные годы, а затем заказы студентов в течение каждого года по фамилии.</span><span class="sxs-lookup"><span data-stu-id="0407f-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="0407f-185">Для получения `Group By`дополнительной информации о , см. [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md)</span><span class="sxs-lookup"><span data-stu-id="0407f-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0407f-186">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0407f-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="0407f-187">Приступая к работе с LINQ в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0407f-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="0407f-188">Запросов</span><span class="sxs-lookup"><span data-stu-id="0407f-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="0407f-189">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0407f-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0407f-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="0407f-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
