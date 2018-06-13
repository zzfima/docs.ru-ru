---
title: Основные операции запроса (Visual Basic)
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
ms.openlocfilehash: 5587a60e97464324659b325e38a18ac25488d30d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644125"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="6fac9-102">Основные операции запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fac9-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="6fac9-103">В этом разделе приводится краткое введение в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] выражения на языке Visual Basic и некоторых типичных операций, выполняемых в запросе.</span><span class="sxs-lookup"><span data-stu-id="6fac9-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="6fac9-104">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="6fac9-104">For more information, see the following topics:</span></span>  
  
 <span data-ttu-id="6fac9-105">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fac9-105">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
  
 [<span data-ttu-id="6fac9-106">Запросы</span><span class="sxs-lookup"><span data-stu-id="6fac9-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="6fac9-107">Пошаговое руководство: Написание запросов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6fac9-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="6fac9-108">Указание источника данных (от)</span><span class="sxs-lookup"><span data-stu-id="6fac9-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="6fac9-109">В [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса, первым шагом является указание источника данных, необходимо выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="6fac9-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="6fac9-110">Таким образом `From` предложения в запросе всегда идет первым.</span><span class="sxs-lookup"><span data-stu-id="6fac9-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="6fac9-111">Операторы запросов выберите и формирование результатов в зависимости от типа источника.</span><span class="sxs-lookup"><span data-stu-id="6fac9-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 <span data-ttu-id="6fac9-112">`From` Предложение указывает источник данных, `customers`и *переменной диапазона*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="6fac9-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="6fac9-113">Переменная диапазона является как переменная итерации цикла, за исключением того, что в выражении запроса не происходит фактической итерации.</span><span class="sxs-lookup"><span data-stu-id="6fac9-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="6fac9-114">При выполнении запроса, обычно с помощью `For Each` цикла, переменная диапазона используется как ссылка на каждый последующий элемент в `customers`.</span><span class="sxs-lookup"><span data-stu-id="6fac9-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="6fac9-115">Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде.</span><span class="sxs-lookup"><span data-stu-id="6fac9-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="6fac9-116">Примеры запросов, написанные с использованием и без явную типизацию см. в разделе [связи между типами в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="6fac9-117">Дополнительные сведения об использовании `From` предложение в Visual Basic. в разделе [предложения From](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="6fac9-118">Фильтрация данных (где)</span><span class="sxs-lookup"><span data-stu-id="6fac9-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="6fac9-119">Возможно, наиболее распространенной операцией запроса является применение фильтра в форме логического выражения.</span><span class="sxs-lookup"><span data-stu-id="6fac9-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="6fac9-120">Запрос возвращает только те элементы, для которых выражение имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="6fac9-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="6fac9-121">Объект `Where` предложение используется для выполнения фильтрации.</span><span class="sxs-lookup"><span data-stu-id="6fac9-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="6fac9-122">Фильтр указывает элементы в источнике данных для включения в результирующей последовательности.</span><span class="sxs-lookup"><span data-stu-id="6fac9-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="6fac9-123">В следующем примере включаются только клиенты, находящиеся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="6fac9-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 <span data-ttu-id="6fac9-124">Можно использовать логические операторы, такие как `And` и `Or` для объединения выражений фильтра в `Where` предложения.</span><span class="sxs-lookup"><span data-stu-id="6fac9-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="6fac9-125">Например чтобы вернуть только клиентов из Лондона с именем Devon, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="6fac9-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="6fac9-126">Чтобы вернуть клиентов из Лондона или Парижа, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="6fac9-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="6fac9-127">Дополнительные сведения об использовании `Where` предложение в Visual Basic. в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="6fac9-128">Упорядочение данных (Order By)</span><span class="sxs-lookup"><span data-stu-id="6fac9-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="6fac9-129">Часто бывает удобно упорядочить возвращенные данные в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="6fac9-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="6fac9-130">`Order By` Предложение сортирует элементы в возвращаемой последовательности должны быть отсортированы в указанном поле или поля.</span><span class="sxs-lookup"><span data-stu-id="6fac9-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="6fac9-131">Например, следующий запрос сортирует результаты на основе `Name` свойство.</span><span class="sxs-lookup"><span data-stu-id="6fac9-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="6fac9-132">Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке, от A до Z.</span><span class="sxs-lookup"><span data-stu-id="6fac9-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 <span data-ttu-id="6fac9-133">Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="6fac9-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="6fac9-134">Значение по умолчанию — `Ascending` при ни `Ascending` , ни `Descending` указано.</span><span class="sxs-lookup"><span data-stu-id="6fac9-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="6fac9-135">Дополнительные сведения об использовании `Order By` предложение в Visual Basic. в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="6fac9-136">Выбор данных (Выбор)</span><span class="sxs-lookup"><span data-stu-id="6fac9-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="6fac9-137">`Select` Предложение определяет форму и содержимое возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="6fac9-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="6fac9-138">Например, можно указать, будут ли результаты состоять из полных `Customer` объектов только один `Customer` свойство, подмножество свойств, сочетания свойств из различных источников данных или некоторых новых типов в соответствии с вычисленными.</span><span class="sxs-lookup"><span data-stu-id="6fac9-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="6fac9-139">Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.</span><span class="sxs-lookup"><span data-stu-id="6fac9-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="6fac9-140">Чтобы получить коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:</span><span class="sxs-lookup"><span data-stu-id="6fac9-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 <span data-ttu-id="6fac9-141">Если `Customer` экземпляра является большим объектом и содержит много полей и все, что требуется извлечь имя, можно выбрать `cust.Name`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6fac9-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="6fac9-142">Вывод локального типа распознает и изменит тип результата из коллекции `Customer` объекты в коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="6fac9-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 <span data-ttu-id="6fac9-143">Чтобы выбрать несколько полей из источника данных, есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="6fac9-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="6fac9-144">В `Select` предложение, укажите поля, которые необходимо включить в результат.</span><span class="sxs-lookup"><span data-stu-id="6fac9-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="6fac9-145">Компилятор будет определить анонимный тип, имеющий эти поля как свойства.</span><span class="sxs-lookup"><span data-stu-id="6fac9-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="6fac9-146">Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="6fac9-147">Поскольку возвращенные элементы в следующем примере являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в другом месте в коде.</span><span class="sxs-lookup"><span data-stu-id="6fac9-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="6fac9-148">Имя компилятором для типа содержит символы, которые являются недопустимыми в обычном коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6fac9-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="6fac9-149">В следующем примере элементы в коллекции, возвращенные запросом в `londonCusts4` являются экземплярами анонимного типа</span><span class="sxs-lookup"><span data-stu-id="6fac9-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     <span data-ttu-id="6fac9-150">- или -</span><span class="sxs-lookup"><span data-stu-id="6fac9-150">-or-</span></span>  
  
-   <span data-ttu-id="6fac9-151">Определите именованный тип, содержащий конкретные поля, которые требуется включить в результат, создайте и инициализируйте экземпляры типа в `Select` предложения.</span><span class="sxs-lookup"><span data-stu-id="6fac9-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="6fac9-152">Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты за пределами коллекции, в котором они возвращаются, или если нужно передать их в качестве параметров при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="6fac9-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="6fac9-153">Тип `londonCusts5` в следующем примере является IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="6fac9-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 <span data-ttu-id="6fac9-154">Дополнительные сведения об использовании `Select` предложение в Visual Basic. в разделе [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="6fac9-155">Присоединяемый данных (соединения и соединения)</span><span class="sxs-lookup"><span data-stu-id="6fac9-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="6fac9-156">Можно объединить несколько источников данных, в `From` предложение несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="6fac9-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="6fac9-157">Например следующий код использует два источника данных и неявно объединяет свойства их в результат.</span><span class="sxs-lookup"><span data-stu-id="6fac9-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="6fac9-158">Запрос выбирает студентов, чьи фамилии начинаются с гласные.</span><span class="sxs-lookup"><span data-stu-id="6fac9-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="6fac9-159">Этот код можно выполнить со списком студентов, созданным в [как: создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="6fac9-160">`Join` Ключевое слово является эквивалентом `INNER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="6fac9-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="6fac9-161">Он объединяет две коллекции на основании совпадающих значений ключей между элементами в двух коллекциях.</span><span class="sxs-lookup"><span data-stu-id="6fac9-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="6fac9-162">Запрос возвращает все или часть элементов коллекции с совпадающими значениями ключей.</span><span class="sxs-lookup"><span data-stu-id="6fac9-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="6fac9-163">Например следующий код дублирует действие предыдущего неявного объединения.</span><span class="sxs-lookup"><span data-stu-id="6fac9-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 <span data-ttu-id="6fac9-164">`Group Join` объединяет коллекции в одну иерархическую коллекцию, так же, как `LEFT JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="6fac9-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="6fac9-165">Дополнительные сведения см. в разделе [предложения Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложения Join группы](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="6fac9-166">Группирование данных (Group By)</span><span class="sxs-lookup"><span data-stu-id="6fac9-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="6fac9-167">Можно добавить `Group By` предложение для группировки элементов в результатах запроса по полям один или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="6fac9-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="6fac9-168">Например следующий код группирует студентов по годам класса.</span><span class="sxs-lookup"><span data-stu-id="6fac9-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 <span data-ttu-id="6fac9-169">При выполнении этого кода, используя список студентов, созданный в [как: создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), выходные данные `For Each` инструкции:</span><span class="sxs-lookup"><span data-stu-id="6fac9-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="6fac9-170">Год: молодых</span><span class="sxs-lookup"><span data-stu-id="6fac9-170">Year: Junior</span></span>  
  
 <span data-ttu-id="6fac9-171">Гладких, Майкл</span><span class="sxs-lookup"><span data-stu-id="6fac9-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="6fac9-172">Орехов, Алексей</span><span class="sxs-lookup"><span data-stu-id="6fac9-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="6fac9-173">Орехов, Дина</span><span class="sxs-lookup"><span data-stu-id="6fac9-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="6fac9-174">Гладких, Андрей</span><span class="sxs-lookup"><span data-stu-id="6fac9-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="6fac9-175">Год: старший</span><span class="sxs-lookup"><span data-stu-id="6fac9-175">Year: Senior</span></span>  
  
 <span data-ttu-id="6fac9-176">Omelchenko Svetlana</span><span class="sxs-lookup"><span data-stu-id="6fac9-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="6fac9-177">Osada Michiko</span><span class="sxs-lookup"><span data-stu-id="6fac9-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="6fac9-178">Грачев, Николай</span><span class="sxs-lookup"><span data-stu-id="6fac9-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="6fac9-179">Ожогина, Инна</span><span class="sxs-lookup"><span data-stu-id="6fac9-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="6fac9-180">Шабалин, Александр</span><span class="sxs-lookup"><span data-stu-id="6fac9-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="6fac9-181">Год: обучения</span><span class="sxs-lookup"><span data-stu-id="6fac9-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="6fac9-182">Mortensen Свен</span><span class="sxs-lookup"><span data-stu-id="6fac9-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="6fac9-183">Орехов, Владимир</span><span class="sxs-lookup"><span data-stu-id="6fac9-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="6fac9-184">Вариант, показанный в следующем коде упорядочивает годы обучения и упорядочивает учащихся в течение каждого года по фамилии.</span><span class="sxs-lookup"><span data-stu-id="6fac9-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 <span data-ttu-id="6fac9-185">Дополнительные сведения о `Group By`, в разделе [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6fac9-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fac9-186">См. также</span><span class="sxs-lookup"><span data-stu-id="6fac9-186">See Also</span></span>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="6fac9-187">Приступая к работе с LINQ в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6fac9-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="6fac9-188">Запросы</span><span class="sxs-lookup"><span data-stu-id="6fac9-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="6fac9-189">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fac9-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="6fac9-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="6fac9-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
