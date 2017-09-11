---
title: "Основные операции запроса (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1ced446d6646bd26b9169f5894138e12a38efde7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="35314-102">Основные операции запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35314-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="35314-103">В этом разделе приводится краткое введение в [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] выражения в Visual Basic и некоторых типичных операций, выполняемых в запросе.</span><span class="sxs-lookup"><span data-stu-id="35314-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="35314-104">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="35314-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="35314-105">Введение в LINQ в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35314-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="35314-106">Запросы</span><span class="sxs-lookup"><span data-stu-id="35314-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="35314-107">: Пошаговое руководство</span><span class="sxs-lookup"><span data-stu-id="35314-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="35314-108">Указание источника данных (от)</span><span class="sxs-lookup"><span data-stu-id="35314-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="35314-109">В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запрос, первым делом следует указать источник данных, который требуется запросить.</span><span class="sxs-lookup"><span data-stu-id="35314-109">In a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="35314-110">Таким образом `From` предложения в запросе всегда идет первым.</span><span class="sxs-lookup"><span data-stu-id="35314-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="35314-111">Операторы запросов выберите и формирование результатов в зависимости от типа источника.</span><span class="sxs-lookup"><span data-stu-id="35314-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 <span data-ttu-id="35314-112">[!code-vb[VbLINQBasicOps&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-112">[!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="35314-113">`From` Предложение указывает источник данных, `customers`и *переменной диапазона*, `cust`.</span><span class="sxs-lookup"><span data-stu-id="35314-113">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="35314-114">Переменная диапазона схожа с переменной итерации цикла, за исключением того, что в выражении запроса не происходит фактической итерации.</span><span class="sxs-lookup"><span data-stu-id="35314-114">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="35314-115">Когда запрос выполняется часто с помощью `For Each` цикла, переменная диапазона используется как ссылка на каждый последующий элемент в `customers`.</span><span class="sxs-lookup"><span data-stu-id="35314-115">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="35314-116">Поскольку компилятор может вывести тип `cust`, необходимо явно указать.</span><span class="sxs-lookup"><span data-stu-id="35314-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="35314-117">Примеры запросов, написанные с использованием и без явного ввода см. [связи типов в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="35314-117">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="35314-118">Дополнительные сведения об использовании `From` предложение в Visual Basic в разделе [предложение From](../../../../visual-basic/language-reference/queries/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35314-118">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="35314-119">Фильтрация данных (Where)</span><span class="sxs-lookup"><span data-stu-id="35314-119">Filtering Data (Where)</span></span>  
 <span data-ttu-id="35314-120">Вероятно, наиболее распространенной операцией запроса является применение фильтра в форме логического выражения.</span><span class="sxs-lookup"><span data-stu-id="35314-120">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="35314-121">Запрос возвращает только те элементы, для которых выражение истинно.</span><span class="sxs-lookup"><span data-stu-id="35314-121">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="35314-122">Объект `Where` для выполнения фильтрации используется предложение.</span><span class="sxs-lookup"><span data-stu-id="35314-122">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="35314-123">Фильтр указывает элементы в источнике данных, чтобы включить в результирующую последовательность.</span><span class="sxs-lookup"><span data-stu-id="35314-123">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="35314-124">В следующем примере включаются только заказчики, находящиеся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="35314-124">In the following example, only those customers who have an address in London are included.</span></span>  
  
 <span data-ttu-id="35314-125">[!code-vb[VbLINQBasicOps&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-125">[!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span></span>  
  
 <span data-ttu-id="35314-126">Можно использовать логические операторы, такие как `And` и `Or` для объединения критериев фильтров в `Where` предложения.</span><span class="sxs-lookup"><span data-stu-id="35314-126">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="35314-127">Например для получения только заказчиков из Лондона с именем Devon, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="35314-127">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="35314-128">Для получения заказчиков из Лондона или Парижа, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="35314-128">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="35314-129">Дополнительные сведения об использовании `Where` предложение в Visual Basic в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35314-129">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="35314-130">Упорядочение данных (Order By)</span><span class="sxs-lookup"><span data-stu-id="35314-130">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="35314-131">Часто бывает удобно упорядочить возвращенные данные в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="35314-131">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="35314-132">`Order By` Предложение сортирует элементы в возвращаемой последовательности должны быть отсортированы по указанному полю или полям.</span><span class="sxs-lookup"><span data-stu-id="35314-132">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="35314-133">Например, следующий запрос сортирует результаты на основе `Name` свойство.</span><span class="sxs-lookup"><span data-stu-id="35314-133">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="35314-134">Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке от А до я.</span><span class="sxs-lookup"><span data-stu-id="35314-134">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 <span data-ttu-id="35314-135">[!code-vb[VbLINQBasicOps&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-135">[!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span></span>  
  
 <span data-ttu-id="35314-136">Чтобы упорядочить результаты в обратном порядке от я до А, используйте `Order By...Descending` предложения.</span><span class="sxs-lookup"><span data-stu-id="35314-136">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="35314-137">Значение по умолчанию — `Ascending` при ни `Ascending` , ни `Descending` указано.</span><span class="sxs-lookup"><span data-stu-id="35314-137">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="35314-138">Дополнительные сведения об использовании `Order By` предложение в Visual Basic в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35314-138">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="35314-139">Выбор данных (Выбор)</span><span class="sxs-lookup"><span data-stu-id="35314-139">Selecting Data (Select)</span></span>  
 <span data-ttu-id="35314-140">`Select` Предложение определяет форму и содержимое возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="35314-140">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="35314-141">Например, можно указать, будут ли результаты состоять из полных `Customer` объектов лишь один `Customer` свойство, подмножества свойств, сочетания свойств из различных источников данных или некоторых новых типов в зависимости от вычислений.</span><span class="sxs-lookup"><span data-stu-id="35314-141">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="35314-142">Когда `Select` предложение создает нечто, отличное от копии исходного элемента, операция называется *проекции*.</span><span class="sxs-lookup"><span data-stu-id="35314-142">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="35314-143">Чтобы извлечь коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:</span><span class="sxs-lookup"><span data-stu-id="35314-143">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 <span data-ttu-id="35314-144">[!code-vb[VbLINQBasicOps&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-144">[!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span></span>  
  
 <span data-ttu-id="35314-145">Если `Customer` экземпляра является большим объектом и содержит много полей, и все, что необходимо получить имя, можно выбрать `cust.Name`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="35314-145">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="35314-146">Вывод локального типа распознает и изменит тип результата из коллекции `Customer` объектов коллекции строк.</span><span class="sxs-lookup"><span data-stu-id="35314-146">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 <span data-ttu-id="35314-147">[!code-vb[VbLINQBasicOps&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-147">[!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span></span>  
  
 <span data-ttu-id="35314-148">Чтобы выбрать несколько полей из источника данных, имеется два варианта:</span><span class="sxs-lookup"><span data-stu-id="35314-148">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="35314-149">В `Select` предложение, укажите поля, которые нужно включить в результат.</span><span class="sxs-lookup"><span data-stu-id="35314-149">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="35314-150">Компилятор определит анонимный тип, имеющий эти поля как свойства.</span><span class="sxs-lookup"><span data-stu-id="35314-150">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="35314-151">Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="35314-151">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="35314-152">Поскольку возвращенные элементы в следующем примере являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в другом месте в коде.</span><span class="sxs-lookup"><span data-stu-id="35314-152">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="35314-153">Имя компилятором для типа содержит символы, которые являются недопустимыми в обычном коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35314-153">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="35314-154">В следующем примере элементы в коллекции, возвращенные запросом в `londonCusts4` экземпляров анонимного типа</span><span class="sxs-lookup"><span data-stu-id="35314-154">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     <span data-ttu-id="35314-155">[!code-vb[VbLINQBasicOps №&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-155">[!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span></span>  
  
     <span data-ttu-id="35314-156">-или-</span><span class="sxs-lookup"><span data-stu-id="35314-156">-or-</span></span>  
  
-   <span data-ttu-id="35314-157">Определите именованный тип, содержащий конкретные поля, которые требуется включить в результат, создайте и инициализируйте экземпляры типа в `Select` предложения.</span><span class="sxs-lookup"><span data-stu-id="35314-157">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="35314-158">Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты за пределами коллекции, в котором они возвращаются, или если необходимо передавать их в качестве параметров при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="35314-158">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="35314-159">Тип `londonCusts5` в следующем примере является IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="35314-159">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     <span data-ttu-id="35314-160">[!code-vb[VbLINQBasicOps&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-160">[!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span></span>  
  
     <span data-ttu-id="35314-161">[!code-vb[VbLINQBasicOps №&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-161">[!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span></span>  
  
 <span data-ttu-id="35314-162">Дополнительные сведения об использовании `Select` предложение в Visual Basic в разделе [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35314-162">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="35314-163">Данные соединения (соединения и Group Join)</span><span class="sxs-lookup"><span data-stu-id="35314-163">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="35314-164">Можно объединить несколько источников данных в `From` предложение несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="35314-164">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="35314-165">Например следующий код использует два источника данных и неявно объединяет свойства их в результат.</span><span class="sxs-lookup"><span data-stu-id="35314-165">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="35314-166">Запрос выбирает студентов, чьи фамилии начинаются с гласной.</span><span class="sxs-lookup"><span data-stu-id="35314-166">The query selects students whose last names start with a vowel.</span></span>  
  
 <span data-ttu-id="35314-167">[!code-vb[VbLINQBasicOps №&9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-167">[!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35314-168">Этот код можно выполнить со списком студентов, созданным в [Практическое руководство: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="35314-168">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="35314-169">`Join` Ключевое слово является эквивалентом `INNER JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="35314-169">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="35314-170">Он объединяет две коллекции на основании совпадающих значений ключей между элементами в двух коллекциях.</span><span class="sxs-lookup"><span data-stu-id="35314-170">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="35314-171">Запрос возвращает все или часть элементов коллекции с совпадающими значениями ключей.</span><span class="sxs-lookup"><span data-stu-id="35314-171">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="35314-172">Например следующий код дублирует действие предыдущего неявного объединения.</span><span class="sxs-lookup"><span data-stu-id="35314-172">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 <span data-ttu-id="35314-173">[!code-vb[VbLINQBasicOps&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-173">[!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span></span>  
  
 <span data-ttu-id="35314-174">`Group Join`объединяет коллекции в одну иерархическую коллекцию аналогично `LEFT JOIN` в SQL.</span><span class="sxs-lookup"><span data-stu-id="35314-174">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="35314-175">Дополнительные сведения см. в разделе [предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложение Join группы](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35314-175">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="35314-176">Группирование данных (Group By)</span><span class="sxs-lookup"><span data-stu-id="35314-176">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="35314-177">Можно добавить `Group By` предложение для группировки элементов в результатах запроса по полям один или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="35314-177">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="35314-178">Например следующий код группирует студентов по курсам.</span><span class="sxs-lookup"><span data-stu-id="35314-178">For example, the following code groups students by class year.</span></span>  
  
 <span data-ttu-id="35314-179">[!code-vb[VbLINQBasicOps&11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-179">[!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span></span>  
  
 <span data-ttu-id="35314-180">При выполнении этого кода, используя список студентов, созданный в [Практическое руководство: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), вывод `For Each` инструкция:</span><span class="sxs-lookup"><span data-stu-id="35314-180">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="35314-181">Год: молодых</span><span class="sxs-lookup"><span data-stu-id="35314-181">Year: Junior</span></span>  
  
 <span data-ttu-id="35314-182">Такер Майкл</span><span class="sxs-lookup"><span data-stu-id="35314-182">Tucker, Michael</span></span>  
  
 <span data-ttu-id="35314-183">Орехов, Алексей</span><span class="sxs-lookup"><span data-stu-id="35314-183">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="35314-184">Орехов, Дина</span><span class="sxs-lookup"><span data-stu-id="35314-184">Garcia, Debra</span></span>  
  
 <span data-ttu-id="35314-185">Гладких, Андрей</span><span class="sxs-lookup"><span data-stu-id="35314-185">Tucker, Lance</span></span>  
  
 <span data-ttu-id="35314-186">Год: старший</span><span class="sxs-lookup"><span data-stu-id="35314-186">Year: Senior</span></span>  
  
 <span data-ttu-id="35314-187">Omelchenko Svetlana</span><span class="sxs-lookup"><span data-stu-id="35314-187">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="35314-188">Osada Michiko</span><span class="sxs-lookup"><span data-stu-id="35314-188">Osada, Michiko</span></span>  
  
 <span data-ttu-id="35314-189">Грачев, Николай</span><span class="sxs-lookup"><span data-stu-id="35314-189">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="35314-190">Ожогина, Инна</span><span class="sxs-lookup"><span data-stu-id="35314-190">Feng, Hanying</span></span>  
  
 <span data-ttu-id="35314-191">Александр Шабалин</span><span class="sxs-lookup"><span data-stu-id="35314-191">Adams, Terry</span></span>  
  
 <span data-ttu-id="35314-192">Год: обучения</span><span class="sxs-lookup"><span data-stu-id="35314-192">Year: Freshman</span></span>  
  
 <span data-ttu-id="35314-193">Mortensen Свен</span><span class="sxs-lookup"><span data-stu-id="35314-193">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="35314-194">Орехов, Владимир</span><span class="sxs-lookup"><span data-stu-id="35314-194">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="35314-195">Вариант, показанный в следующем коде, упорядочивает годы обучения и упорядочивает студентов каждого курса по фамилиям.</span><span class="sxs-lookup"><span data-stu-id="35314-195">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 <span data-ttu-id="35314-196">[!code-vb[VbLINQBasicOps&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="35314-196">[!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span></span>  
  
 <span data-ttu-id="35314-197">Дополнительные сведения о `Group By`, в разделе [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="35314-197">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35314-198">См. также</span><span class="sxs-lookup"><span data-stu-id="35314-198">See Also</span></span>  
 <span data-ttu-id="35314-199"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="35314-199"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="35314-200"> [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="35314-200"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="35314-201"> [Запросы](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="35314-201"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="35314-202"> [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="35314-202"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="35314-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="35314-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span></span>
