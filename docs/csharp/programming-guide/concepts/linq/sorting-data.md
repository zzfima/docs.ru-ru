---
title: Сортировка данных (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: dfa0a4a030cab8ec33c90d8edaef0d6070755034
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722023"
---
# <a name="sorting-data-c"></a><span data-ttu-id="90b27-102">Сортировка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="90b27-102">Sorting Data (C#)</span></span>
<span data-ttu-id="90b27-103">Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="90b27-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="90b27-104">Первый критерий сортировки выполняет первичную сортировку элементов.</span><span class="sxs-lookup"><span data-stu-id="90b27-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="90b27-105">Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="90b27-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="90b27-106">На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="90b27-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="90b27-107">![Операции сортировки LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="90b27-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="90b27-108">Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.</span><span class="sxs-lookup"><span data-stu-id="90b27-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90b27-109">Методы</span><span class="sxs-lookup"><span data-stu-id="90b27-109">Methods</span></span>  
  
|<span data-ttu-id="90b27-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="90b27-110">Method Name</span></span>|<span data-ttu-id="90b27-111">Описание</span><span class="sxs-lookup"><span data-stu-id="90b27-111">Description</span></span>|<span data-ttu-id="90b27-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="90b27-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="90b27-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="90b27-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="90b27-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="90b27-114">OrderBy</span></span>|<span data-ttu-id="90b27-115">Сортировка значений в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="90b27-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="90b27-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="90b27-116">OrderByDescending</span></span>|<span data-ttu-id="90b27-117">Сортировка значений в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="90b27-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="90b27-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="90b27-118">ThenBy</span></span>|<span data-ttu-id="90b27-119">Дополнительная сортировка по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="90b27-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="90b27-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="90b27-120">ThenByDescending</span></span>|<span data-ttu-id="90b27-121">Дополнительная сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="90b27-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="90b27-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="90b27-122">Reverse</span></span>|<span data-ttu-id="90b27-123">Изменение порядка элементов в коллекции на обратный.</span><span class="sxs-lookup"><span data-stu-id="90b27-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="90b27-124">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="90b27-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="90b27-125">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="90b27-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="90b27-126">Примеры основной сортировки</span><span class="sxs-lookup"><span data-stu-id="90b27-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="90b27-127">Основная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="90b27-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="90b27-128">В следующем примере показано использование предложения `orderby` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="90b27-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="90b27-129">Основная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="90b27-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="90b27-130">В следующем примере показано использование предложения `orderby descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="90b27-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="90b27-131">Примеры дополнительной сортировки</span><span class="sxs-lookup"><span data-stu-id="90b27-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="90b27-132">Дополнительная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="90b27-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="90b27-133">В следующем примере показано использование предложения `orderby` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="90b27-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="90b27-134">Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="90b27-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="90b27-135">Дополнительная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="90b27-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="90b27-136">В следующем примере показано использование предложения `orderby descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="90b27-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="90b27-137">Строки сортируются основным образом по длине и дополнительно — по первой букве строки.</span><span class="sxs-lookup"><span data-stu-id="90b27-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="90b27-138">См. также</span><span class="sxs-lookup"><span data-stu-id="90b27-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="90b27-139">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="90b27-139">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="90b27-140">предложение orderby</span><span class="sxs-lookup"><span data-stu-id="90b27-140">orderby clause</span></span>](../../../../csharp/language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="90b27-141">Практическое руководство. Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="90b27-141">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="90b27-142">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="90b27-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
