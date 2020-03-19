---
title: Общие сведения о стандартных операторах запроса (C#)
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 76c2c4684f33c3fb30748b5f08efd215548661ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167859"
---
# <a name="standard-query-operators-overview-c"></a><span data-ttu-id="799eb-102">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-102">Standard Query Operators Overview (C#)</span></span>
<span data-ttu-id="799eb-103">*Стандартные операторы запросов* — это методы, формирующие шаблон LINQ.</span><span class="sxs-lookup"><span data-stu-id="799eb-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="799eb-104">Большинство этих методов работают с последовательностями. В данном контексте последовательность — это объект, тип которого реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="799eb-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="799eb-105">Функциональные возможности стандартных операторов запросов включают фильтрацию, проекцию, статистическую обработку, сортировку и многие другие.</span><span class="sxs-lookup"><span data-stu-id="799eb-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="799eb-106">Существует два набора стандартных операторов запросов LINQ, один из них работает с объектами типа <xref:System.Collections.Generic.IEnumerable%601>, а другой — с объектами типа <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="799eb-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="799eb-107">Методы, входящие в каждый из наборов, являются статическими членами классов <xref:System.Linq.Enumerable> и <xref:System.Linq.Queryable> соответственно.</span><span class="sxs-lookup"><span data-stu-id="799eb-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="799eb-108">Они определяются как *методы расширения* типа, к которому применяются.</span><span class="sxs-lookup"><span data-stu-id="799eb-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="799eb-109">Это означает, что их можно вызывать, используя либо синтаксис статического метода, либо синтаксис метода экземпляра.</span><span class="sxs-lookup"><span data-stu-id="799eb-109">This means that they can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="799eb-110">Кроме того, несколько стандартных методов операторов запроса работают с типами, отличными от основанных на <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="799eb-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="799eb-111">Тип <xref:System.Linq.Enumerable> определяет два таких метода, которые работают с объектами типа <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="799eb-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="799eb-112">Эти методы (<xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> и <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>) позволяют выполнять запрос к непараметризованным или не являющимся универсальными коллекциям с использованием шаблона LINQ.</span><span class="sxs-lookup"><span data-stu-id="799eb-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="799eb-113">Для этого создается строго типизированная коллекция объектов.</span><span class="sxs-lookup"><span data-stu-id="799eb-113">They do this by creating a strongly-typed collection of objects.</span></span> <span data-ttu-id="799eb-114">Класс <xref:System.Linq.Queryable> определяет два схожих метода (<xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> и <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>), которые работают с объектами типа <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="799eb-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="799eb-115">Стандартные операторы запросов имеют различное время выполнения, которое зависит от того, возвращают они одноэлементное значение или последовательность значений.</span><span class="sxs-lookup"><span data-stu-id="799eb-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="799eb-116">Методы, возвращающие одноэлементное значение (например, <xref:System.Linq.Enumerable.Average%2A> и <xref:System.Linq.Enumerable.Sum%2A>), выполняются одновременно.</span><span class="sxs-lookup"><span data-stu-id="799eb-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="799eb-117">Методы, которые возвращают последовательность, откладывают выполнение запроса и возвращают перечисляемый объект.</span><span class="sxs-lookup"><span data-stu-id="799eb-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="799eb-118">При использовании методов, которые применяются к коллекциям, т. е. методов, которые расширяют <xref:System.Collections.Generic.IEnumerable%601>, возвращаемый перечисляемый объект захватывает переданные в этот метод аргументы.</span><span class="sxs-lookup"><span data-stu-id="799eb-118">In the case of the methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="799eb-119">При перечислении этого объекта задействуется логика оператора запросов и возвращаются результаты запросов.</span><span class="sxs-lookup"><span data-stu-id="799eb-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="799eb-120">При этом методы, расширяющие <xref:System.Linq.IQueryable%601>, не реализуют поведение запросов, но формируют дерево выражения, представляющее выполняемый запрос.</span><span class="sxs-lookup"><span data-stu-id="799eb-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="799eb-121">Запрос обрабатывается объектом <xref:System.Linq.IQueryable%601> источника.</span><span class="sxs-lookup"><span data-stu-id="799eb-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="799eb-122">Вызовы методов запросов можно объединять в один запрос, в результате чего запросы могут становиться довольно сложными.</span><span class="sxs-lookup"><span data-stu-id="799eb-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="799eb-123">В следующем примере кода показано, как использовать стандартные операторы запросов для получения сведений о последовательности.</span><span class="sxs-lookup"><span data-stu-id="799eb-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="799eb-124">Синтаксис выражений запросов</span><span class="sxs-lookup"><span data-stu-id="799eb-124">Query Expression Syntax</span></span>  
 <span data-ttu-id="799eb-125">Некоторые из наиболее часто используемых стандартных операторов запросов имеют представление в виде ключевых слов в синтаксисе языка C# и Visual Basic, что позволяет вызывать их как часть *выражения* *запроса*.</span><span class="sxs-lookup"><span data-stu-id="799eb-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="799eb-126">Дополнительные сведения о стандартных операторах запросов с выделенными ключевыми словами и соответствующим синтаксисом см. в разделе [Синтаксис выражений запросов для стандартных операторов запросов (C#)](./query-expression-syntax-for-standard-query-operators.md).</span><span class="sxs-lookup"><span data-stu-id="799eb-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (C#)](./query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="799eb-127">Расширение стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="799eb-127">Extending the Standard Query Operators</span></span>  
 <span data-ttu-id="799eb-128">Набор стандартных операторов запросов можно дополнить, создав специальные методы, соответствующие вашему целевому домену или технологии.</span><span class="sxs-lookup"><span data-stu-id="799eb-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="799eb-129">Кроме того, можно заменить стандартные операторы запросов на собственные реализации, предоставляющие дополнительные услуги, такие как удаленное вычисление, перевод запросов и оптимизация.</span><span class="sxs-lookup"><span data-stu-id="799eb-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="799eb-130">Пример см. в разделе <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="799eb-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="799eb-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="799eb-131">Related Sections</span></span>  
 <span data-ttu-id="799eb-132">Следующие ссылки адресуют к разделам, содержащим дополнительные сведения о различных стандартных операторах запросов в зависимости от их функциональности.</span><span class="sxs-lookup"><span data-stu-id="799eb-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="799eb-133">Сортировка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-133">Sorting Data (C#)</span></span>](./sorting-data.md)  
  
 [<span data-ttu-id="799eb-134">Операции над множествами (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-134">Set Operations (C#)</span></span>](./set-operations.md)  
  
 [<span data-ttu-id="799eb-135">Фильтрация данных (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-135">Filtering Data (C#)</span></span>](./filtering-data.md)  
  
 [<span data-ttu-id="799eb-136">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-136">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)  
  
 [<span data-ttu-id="799eb-137">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-137">Projection Operations (C#)</span></span>](./projection-operations.md)  
  
 [<span data-ttu-id="799eb-138">Секционирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-138">Partitioning Data (C#)</span></span>](./partitioning-data.md)  
  
 [<span data-ttu-id="799eb-139">Операции соединения (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-139">Join Operations (C#)</span></span>](./join-operations.md)  
  
 [<span data-ttu-id="799eb-140">Группирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-140">Grouping Data (C#)</span></span>](./grouping-data.md)  
  
 [<span data-ttu-id="799eb-141">Операции создания (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-141">Generation Operations (C#)</span></span>](./generation-operations.md)  
  
 [<span data-ttu-id="799eb-142">Операции сравнения (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-142">Equality Operations (C#)</span></span>](./equality-operations.md)  
  
 [<span data-ttu-id="799eb-143">Операции с элементами (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-143">Element Operations (C#)</span></span>](./element-operations.md)  
  
 [<span data-ttu-id="799eb-144">Преобразование типов данных (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-144">Converting Data Types (C#)</span></span>](./converting-data-types.md)  
  
 [<span data-ttu-id="799eb-145">Операции объединения (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-145">Concatenation Operations (C#)</span></span>](./concatenation-operations.md)  
  
 [<span data-ttu-id="799eb-146">Операции агрегирования (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-146">Aggregation Operations (C#)</span></span>](./aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="799eb-147">См. также</span><span class="sxs-lookup"><span data-stu-id="799eb-147">See also</span></span>

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [<span data-ttu-id="799eb-148">Введение в запросы LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-148">Introduction to LINQ Queries (C#)</span></span>](./introduction-to-linq-queries.md)
- [<span data-ttu-id="799eb-149">Синтаксис выражений запроса для стандартных операторов запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-149">Query Expression Syntax for Standard Query Operators (C#)</span></span>](./query-expression-syntax-for-standard-query-operators.md)
- [<span data-ttu-id="799eb-150">Классификация стандартных операторов запросов по способу выполнения (C#)</span><span class="sxs-lookup"><span data-stu-id="799eb-150">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](./classification-of-standard-query-operators-by-manner-of-execution.md)
- [<span data-ttu-id="799eb-151">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="799eb-151">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
