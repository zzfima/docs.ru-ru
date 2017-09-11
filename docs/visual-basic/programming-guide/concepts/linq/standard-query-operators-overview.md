---
title: "Общие сведения о стандартных операторах (Visual Basic) | Документы Microsoft"
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
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229b63db761f2a1ed5333fd6f8e4eb9b5c0b75de
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="standard-query-operators-overview-visual-basic"></a><span data-ttu-id="ed7d1-102">Общие сведения о стандартных операторах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-102">Standard Query Operators Overview (Visual Basic)</span></span>
<span data-ttu-id="ed7d1-103">*Стандартные операторы запросов* методы, образующие шаблон LINQ.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="ed7d1-104">Большинство этих методов работают с последовательностями, где последовательность — это объект, тип которого реализует <xref:System.Collections.Generic.IEnumerable%601>интерфейс или <xref:System.Linq.IQueryable%601>интерфейса.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="ed7d1-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="ed7d1-105">Стандартные операторы запросов предоставляют возможности запроса, включая фильтрацию, проекцию, статистическую, сортировка и многое другое.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="ed7d1-106">Существует два набора стандартных операторов запросов LINQ, один, работающий с объектами типа <xref:System.Collections.Generic.IEnumerable%601>, а другой, работающий с объектами типа <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="ed7d1-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="ed7d1-107">Методы, которые составляют каждый набор являются статическими членами <xref:System.Linq.Enumerable>и <xref:System.Linq.Queryable>классы соответственно.</xref:System.Linq.Queryable> </xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="ed7d1-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="ed7d1-108">Они определяются как *методы расширения* типа, они работают.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="ed7d1-109">Это означает, что их можно вызывать с помощью синтаксиса статического метода или синтаксис метода экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-109">This means that they can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="ed7d1-110">Кроме того несколько методов стандартных операторов запросов работают с типами, отличными от тех, на основе <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="ed7d1-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="ed7d1-111"><xref:System.Linq.Enumerable>Тип определяет два метода, оба работают с объектами типа <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> </xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="ed7d1-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="ed7d1-112">Эти методы <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29>и <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, позволяют включить коллекцию без параметров или универсальным, должны запрашиваться в шаблоне LINQ.</xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> </xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29></span><span class="sxs-lookup"><span data-stu-id="ed7d1-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="ed7d1-113">Это делается путем создания строго типизированной коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-113">They do this by creating a strongly-typed collection of objects.</span></span> <span data-ttu-id="ed7d1-114"><xref:System.Linq.Queryable>Класс определяет два аналогичных методов <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29>и <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, которые работают с объектами типа <xref:System.Linq.Queryable>.</xref:System.Linq.Queryable> </xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> </xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="ed7d1-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="ed7d1-115">Стандартные операторы запросов отличаются по времени их выполнения, в зависимости от того, возвращают они одноэлементное значение или последовательность значений.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="ed7d1-116">Методы, возвращающие одноэлементное значение (например, <xref:System.Linq.Enumerable.Average%2A>и <xref:System.Linq.Enumerable.Sum%2A>) выполняются немедленно.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="ed7d1-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="ed7d1-117">Методы, которые возвращают последовательности отложить выполнение запроса и возвращает перечислимый объект.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="ed7d1-118">При использовании методов, которые работают с коллекциями в памяти, то есть те методы, которые расширяют <xref:System.Collections.Generic.IEnumerable%601>, возвращаемый перечисляемый объект захватывает аргументы, переданные в метод.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="ed7d1-118">In the case of the methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="ed7d1-119">При перечислении объекта используется логика оператора запроса применяется и возвращаются результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="ed7d1-120">Напротив, методы, расширяющие <xref:System.Linq.IQueryable%601>не реализуют поведение любого запроса, а строят дерево выражения, которое представляет выполняемый запрос.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="ed7d1-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="ed7d1-121">Обработка запросов проходит по источнику <xref:System.Linq.IQueryable%601>объекта.</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="ed7d1-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="ed7d1-122">Вызовы методов запроса могут быть объединены в один запрос, который позволяет выполнять запросы к усложнению.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="ed7d1-123">В следующем примере кода показано, как стандартные операторы запроса можно использовать для получения сведений о последовательности.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```vb  
Dim sentence = "the quick brown fox jumps over the lazy dog"  
' Split the string into individual words to create a collection.  
Dim words = sentence.Split(" "c)  
  
Dim query = From word In words   
            Group word.ToUpper() By word.Length Into gr = Group   
            Order By Length _  
            Select Length, GroupedWords = gr  
  
Dim output As New System.Text.StringBuilder  
For Each obj In query  
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))  
    For Each word As String In obj.GroupedWords  
        output.AppendLine(word)  
    Next  
Next  
  
'Display the output  
MsgBox(output.ToString())  
  
' This code example produces the following output:  
'  
' Words of length 3:  
' THE  
' FOX  
' THE  
' DOG  
' Words of length 4:  
' OVER  
' LAZY  
' Words of length 5:  
' QUICK  
' BROWN  
' JUMPS   
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="ed7d1-124">Синтаксис выражений запросов</span><span class="sxs-lookup"><span data-stu-id="ed7d1-124">Query Expression Syntax</span></span>  
 <span data-ttu-id="ed7d1-125">Некоторые из наиболее часто используемых стандартных операторов запросов имеют представление в C# и Visual Basic синтаксис ключевого слова языка, что позволяет им вызывается как часть *запроса* *выражение*.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="ed7d1-126">Дополнительные сведения о стандартных операторах запросов, обладающих выделенными ключевыми словами и их синтаксисе см. в разделе [синтаксис выражений запроса для стандартных операторов запросов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ed7d1-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="ed7d1-127">Расширение стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="ed7d1-127">Extending the Standard Query Operators</span></span>  
 <span data-ttu-id="ed7d1-128">Набор стандартных операторов запросов можно дополнить путем создания доменного методы, которые подходят для целевой предметной области или технологии.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="ed7d1-129">Можно также заменить стандартные операторы запросов собственными реализациями, предоставляющими дополнительную функциональность, например удаленное выполнение, преобразование запроса и оптимизации.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="ed7d1-130">В разделе <xref:System.Linq.Enumerable.AsEnumerable%2A>пример.</xref:System.Linq.Enumerable.AsEnumerable%2A></span><span class="sxs-lookup"><span data-stu-id="ed7d1-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ed7d1-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ed7d1-131">Related Sections</span></span>  
 <span data-ttu-id="ed7d1-132">Следующие ссылки, чтобы занять на разделы, содержащие дополнительные сведения о различных стандартных операторов запросов на основе функциональности.</span><span class="sxs-lookup"><span data-stu-id="ed7d1-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="ed7d1-133">Сортировка данных</span><span class="sxs-lookup"><span data-stu-id="ed7d1-133">Sorting Data</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)  
  
 [<span data-ttu-id="ed7d1-134">Набор операций (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-134">Set Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)  
  
 [<span data-ttu-id="ed7d1-135">Фильтрация данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-135">Filtering Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)  
  
 [<span data-ttu-id="ed7d1-136">Операции, использующие кванторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-136">Quantifier Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)  
  
 [<span data-ttu-id="ed7d1-137">Операции проецирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-137">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)  
  
 [<span data-ttu-id="ed7d1-138">Секционирование данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-138">Partitioning Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)  
  
 [<span data-ttu-id="ed7d1-139">Объединение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-139">Join Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)  
  
 [<span data-ttu-id="ed7d1-140">Группирование данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-140">Grouping Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)  
  
 [<span data-ttu-id="ed7d1-141">Операции создания (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-141">Generation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)  
  
 [<span data-ttu-id="ed7d1-142">Операции равенства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-142">Equality Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)  
  
 [<span data-ttu-id="ed7d1-143">Операции с элементами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-143">Element Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)  
  
 [<span data-ttu-id="ed7d1-144">Преобразование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-144">Converting Data Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)  
  
 [<span data-ttu-id="ed7d1-145">Операции объединения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-145">Concatenation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)  
  
 [<span data-ttu-id="ed7d1-146">Операции статистической обработки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-146">Aggregation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed7d1-147">См. также</span><span class="sxs-lookup"><span data-stu-id="ed7d1-147">See Also</span></span>  
 <span data-ttu-id="ed7d1-148"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="ed7d1-148"><xref:System.Linq.Enumerable></span></span>   
 <span data-ttu-id="ed7d1-149"><xref:System.Linq.Queryable></xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="ed7d1-149"><xref:System.Linq.Queryable></span></span>   
<span data-ttu-id="ed7d1-150"> [Введение в LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="ed7d1-150"> [Introduction to LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="ed7d1-151"> [Синтаксис выражений запроса для стандартных операторов запросов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md) </span><span class="sxs-lookup"><span data-stu-id="ed7d1-151"> [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md) </span></span>  
<span data-ttu-id="ed7d1-152"> [Классификация стандартных операторов запросов по способу выполнения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md) </span><span class="sxs-lookup"><span data-stu-id="ed7d1-152"> [Classification of Standard Query Operators by Manner of Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md) </span></span>  
<span data-ttu-id="ed7d1-153"> [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="ed7d1-153"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
