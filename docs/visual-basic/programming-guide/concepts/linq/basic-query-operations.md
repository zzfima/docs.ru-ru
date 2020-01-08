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
ms.openlocfilehash: b9216dba23f49e4d9fd99687e38f5c13addde8fb
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636878"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="5a659-102">Основные операции запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a659-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="5a659-103">В этом разделе приведены краткие сведения о выражениях LINQ в Visual Basic и некоторых типичных операциях, выполняемых в запросе.</span><span class="sxs-lookup"><span data-stu-id="5a659-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="5a659-104">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="5a659-104">For more information, see the following topics:</span></span>  
  
 <span data-ttu-id="5a659-105">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a659-105">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
  
 [<span data-ttu-id="5a659-106">Запросы</span><span class="sxs-lookup"><span data-stu-id="5a659-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="5a659-107">Пошаговое руководство. Написание запросов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a659-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="5a659-108">Указание источника данных (из)</span><span class="sxs-lookup"><span data-stu-id="5a659-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="5a659-109">В запросе LINQ первым шагом является указание источника данных, к которому необходимо выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="5a659-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="5a659-110">Таким образом, предложение `From` в запросе всегда происходит первым.</span><span class="sxs-lookup"><span data-stu-id="5a659-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="5a659-111">Операторы запросов выбирают и формируют результат на основе типа источника.</span><span class="sxs-lookup"><span data-stu-id="5a659-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="5a659-112">В предложении `From` указываются источник данных, `customers`и *переменная диапазона*`cust`.</span><span class="sxs-lookup"><span data-stu-id="5a659-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="5a659-113">Переменная диапазона похожа на переменную итерации цикла, за исключением того, что в выражении запроса фактическая итерация не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5a659-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="5a659-114">При выполнении запроса, часто с помощью цикла `For Each`, переменная диапазона служит ссылкой на каждый последовательный элемент в `customers`.</span><span class="sxs-lookup"><span data-stu-id="5a659-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="5a659-115">Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде.</span><span class="sxs-lookup"><span data-stu-id="5a659-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="5a659-116">Примеры запросов, написанных с неявной типизацией и без них, см. [в разделе связи типов в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="5a659-117">Дополнительные сведения об использовании предложения `From` в Visual Basic см. в разделе [предложение from](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="5a659-118">Фильтрация данных (где)</span><span class="sxs-lookup"><span data-stu-id="5a659-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="5a659-119">Возможно, наиболее распространенной операцией запроса является применение фильтра в виде логического выражения.</span><span class="sxs-lookup"><span data-stu-id="5a659-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="5a659-120">Затем запрос возвращает только те элементы, для которых выражение имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="5a659-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="5a659-121">Для выполнения фильтрации используется предложение `Where`.</span><span class="sxs-lookup"><span data-stu-id="5a659-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="5a659-122">Фильтр указывает, какие элементы в источнике данных включить в результирующую последовательность.</span><span class="sxs-lookup"><span data-stu-id="5a659-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="5a659-123">В следующем примере включаются только клиенты, имеющие адрес в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="5a659-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="5a659-124">Для объединения выражений фильтра в предложении `Where` можно использовать логические операторы, такие как `And` и `Or`.</span><span class="sxs-lookup"><span data-stu-id="5a659-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="5a659-125">Например, чтобы возвратить только тех клиентов из Лондона, имя которых — Девон, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="5a659-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="5a659-126">Чтобы вернуть клиентов из Лондона или Париж, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="5a659-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="5a659-127">Дополнительные сведения об использовании предложения `Where` в Visual Basic см. в разделе [предложение WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="5a659-128">Упорядочение данных (ORDER BY)</span><span class="sxs-lookup"><span data-stu-id="5a659-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="5a659-129">Часто бывает удобно сортировать возвращаемые данные в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="5a659-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="5a659-130">Предложение `Order By` приведет к сортировке элементов в возвращаемой последовательности по указанному полю или полям.</span><span class="sxs-lookup"><span data-stu-id="5a659-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="5a659-131">Например, следующий запрос сортирует результаты на основе свойства `Name`.</span><span class="sxs-lookup"><span data-stu-id="5a659-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="5a659-132">Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке от а до я.</span><span class="sxs-lookup"><span data-stu-id="5a659-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="5a659-133">Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`.</span><span class="sxs-lookup"><span data-stu-id="5a659-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="5a659-134">Значение по умолчанию — `Ascending`, если не указано ни `Ascending`, ни `Descending`.</span><span class="sxs-lookup"><span data-stu-id="5a659-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="5a659-135">Дополнительные сведения об использовании предложения `Order By` в Visual Basic см. в разделе [предложение ORDER BY](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="5a659-136">Выбор данных (выбор)</span><span class="sxs-lookup"><span data-stu-id="5a659-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="5a659-137">Предложение `Select` задает форму и содержимое возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="5a659-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="5a659-138">Например, можно указать, будут ли результаты состоять из полных `Customer` объектов, всего одного `Customer` свойства, подмножества свойств, сочетания свойств из различных источников данных или какого-либо нового типа результата на основе вычислений.</span><span class="sxs-lookup"><span data-stu-id="5a659-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="5a659-139">Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.</span><span class="sxs-lookup"><span data-stu-id="5a659-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="5a659-140">Чтобы получить коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:</span><span class="sxs-lookup"><span data-stu-id="5a659-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="5a659-141">Если `Customer` экземпляр представляет собой большой объект, который содержит много полей, и все, что требуется получить, — это имя, можно выбрать `cust.Name`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5a659-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="5a659-142">Определение локального типа распознает, что это изменяет тип результата из коллекции `Customer` объектов на коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="5a659-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="5a659-143">Чтобы выбрать несколько полей из источника данных, доступны два варианта:</span><span class="sxs-lookup"><span data-stu-id="5a659-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="5a659-144">В предложении `Select` укажите поля, которые необходимо включить в результат.</span><span class="sxs-lookup"><span data-stu-id="5a659-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="5a659-145">Компилятор определит анонимный тип, в котором эти поля являются свойствами.</span><span class="sxs-lookup"><span data-stu-id="5a659-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="5a659-146">Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="5a659-147">Поскольку возвращаемые элементы в следующем примере являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в любом расположении в коде.</span><span class="sxs-lookup"><span data-stu-id="5a659-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="5a659-148">Имя типа, назначенное компилятором, содержит символы, недопустимые в стандартном коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5a659-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="5a659-149">В следующем примере элементы в коллекции, возвращаемые запросом в `londonCusts4`, являются экземплярами анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="5a659-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="5a659-150">\- или -</span><span class="sxs-lookup"><span data-stu-id="5a659-150">-or-</span></span>  
  
- <span data-ttu-id="5a659-151">Определите именованный тип, содержащий определенные поля, которые необходимо включить в результат, и создайте и инициализируйте экземпляры типа в предложении `Select`.</span><span class="sxs-lookup"><span data-stu-id="5a659-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="5a659-152">Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты вне коллекции, в которой они возвращаются, или если необходимо передать их в качестве параметров в вызовы метода.</span><span class="sxs-lookup"><span data-stu-id="5a659-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="5a659-153">Тип `londonCusts5` в следующем примере — IEnumerable (Of Намефоне).</span><span class="sxs-lookup"><span data-stu-id="5a659-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="5a659-154">Дополнительные сведения об использовании предложения `Select` в Visual Basic см. в разделе [предложение SELECT](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="5a659-155">Соединение данных (присоединение и объединение групп)</span><span class="sxs-lookup"><span data-stu-id="5a659-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="5a659-156">В предложении `From` можно объединить более одного источника данных несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="5a659-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="5a659-157">Например, следующий код использует два источника данных и неявно объединяет свойства обоих из них в результате.</span><span class="sxs-lookup"><span data-stu-id="5a659-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="5a659-158">Запрос выбирает учащихся, чьи фамилии начинаются с гласной.</span><span class="sxs-lookup"><span data-stu-id="5a659-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="5a659-159">Этот код можно запустить со списком учащихся, созданных в ходе [создания списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="5a659-160">Ключевое слово `Join` эквивалентно `INNER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="5a659-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="5a659-161">Он объединяет две коллекции на основе совпадающих значений ключей между элементами в двух коллекциях.</span><span class="sxs-lookup"><span data-stu-id="5a659-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="5a659-162">Запрос возвращает все элементы коллекции, имеющие совпадающие значения ключей, или часть ее элементов.</span><span class="sxs-lookup"><span data-stu-id="5a659-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="5a659-163">Например, следующий код дублирует действие предыдущего неявного объединения.</span><span class="sxs-lookup"><span data-stu-id="5a659-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="5a659-164">`Group Join` объединяет коллекции в одну иерархическую коллекцию, как и `LEFT JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="5a659-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="5a659-165">Дополнительные сведения см. в разделе [предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="5a659-166">Группирование данных (Group By)</span><span class="sxs-lookup"><span data-stu-id="5a659-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="5a659-167">Можно добавить предложение `Group By`, чтобы сгруппировать элементы в результатах запроса в соответствии с одним или несколькими полями элементов.</span><span class="sxs-lookup"><span data-stu-id="5a659-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="5a659-168">Например, следующий код группирует учащихся по классу year.</span><span class="sxs-lookup"><span data-stu-id="5a659-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="5a659-169">Если запустить этот код с помощью списка учащихся, созданных в [инструкции по созданию списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), выходные данные инструкции `For Each` будут:</span><span class="sxs-lookup"><span data-stu-id="5a659-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="5a659-170">Год: младшие</span><span class="sxs-lookup"><span data-stu-id="5a659-170">Year: Junior</span></span>  
  
 <span data-ttu-id="5a659-171">Туккер, Майкл</span><span class="sxs-lookup"><span data-stu-id="5a659-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="5a659-172">Гарсиа, Хьюго</span><span class="sxs-lookup"><span data-stu-id="5a659-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="5a659-173">Garcia, Debra</span><span class="sxs-lookup"><span data-stu-id="5a659-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="5a659-174">Туккер, Лэнс</span><span class="sxs-lookup"><span data-stu-id="5a659-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="5a659-175">Год: старший</span><span class="sxs-lookup"><span data-stu-id="5a659-175">Year: Senior</span></span>  
  
 <span data-ttu-id="5a659-176">Омелченко, Светлана</span><span class="sxs-lookup"><span data-stu-id="5a659-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="5a659-177">Осада, Мичико</span><span class="sxs-lookup"><span data-stu-id="5a659-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="5a659-178">Фахури, Фэди</span><span class="sxs-lookup"><span data-stu-id="5a659-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="5a659-179">Фенг, Ханинг</span><span class="sxs-lookup"><span data-stu-id="5a659-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="5a659-180">Адамс, Терри</span><span class="sxs-lookup"><span data-stu-id="5a659-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="5a659-181">Year: свежая</span><span class="sxs-lookup"><span data-stu-id="5a659-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="5a659-182">Мортенсен, Свен</span><span class="sxs-lookup"><span data-stu-id="5a659-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="5a659-183">Гарсиа, Сезар</span><span class="sxs-lookup"><span data-stu-id="5a659-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="5a659-184">Вариант, показанный в следующем коде, упорядочивает класс years, а затем упорядочивает учащихся в каждом году по фамилии.</span><span class="sxs-lookup"><span data-stu-id="5a659-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="5a659-185">Дополнительные сведения о `Group By`см. в разделе [предложение GROUP BY](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5a659-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a659-186">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a659-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="5a659-187">Приступая к работе с LINQ в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a659-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="5a659-188">Запросы</span><span class="sxs-lookup"><span data-stu-id="5a659-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5a659-189">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a659-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="5a659-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="5a659-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
