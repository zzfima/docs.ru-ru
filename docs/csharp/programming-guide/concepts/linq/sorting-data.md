---
title: "Сортировка данных (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ff6ef81486074f2e738b62ce37e6cb58bff49bf8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="sorting-data-c"></a><span data-ttu-id="b8d81-102">Сортировка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="b8d81-102">Sorting Data (C#)</span></span>
<span data-ttu-id="b8d81-103">Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b8d81-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="b8d81-104">Первый критерий сортировки выполняет первичную сортировку элементов.</span><span class="sxs-lookup"><span data-stu-id="b8d81-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="b8d81-105">Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="b8d81-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="b8d81-106">На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="b8d81-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="b8d81-107">![Операции сортировки LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="b8d81-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="b8d81-108">Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.</span><span class="sxs-lookup"><span data-stu-id="b8d81-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8d81-109">Методы</span><span class="sxs-lookup"><span data-stu-id="b8d81-109">Methods</span></span>  
  
|<span data-ttu-id="b8d81-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="b8d81-110">Method Name</span></span>|<span data-ttu-id="b8d81-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b8d81-111">Description</span></span>|<span data-ttu-id="b8d81-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="b8d81-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="b8d81-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b8d81-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b8d81-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="b8d81-114">OrderBy</span></span>|<span data-ttu-id="b8d81-115">Сортировка значений в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="b8d81-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="b8d81-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="b8d81-116">OrderByDescending</span></span>|<span data-ttu-id="b8d81-117">Сортировка значений в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="b8d81-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="b8d81-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="b8d81-118">ThenBy</span></span>|<span data-ttu-id="b8d81-119">Дополнительная сортировка по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="b8d81-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="b8d81-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="b8d81-120">ThenByDescending</span></span>|<span data-ttu-id="b8d81-121">Дополнительная сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="b8d81-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="b8d81-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="b8d81-122">Reverse</span></span>|<span data-ttu-id="b8d81-123">Изменение порядка элементов в коллекции на обратный.</span><span class="sxs-lookup"><span data-stu-id="b8d81-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="b8d81-124">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b8d81-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="b8d81-125">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="b8d81-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="b8d81-126">Примеры основной сортировки</span><span class="sxs-lookup"><span data-stu-id="b8d81-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="b8d81-127">Основная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="b8d81-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="b8d81-128">В следующем примере показано использование предложения `orderby` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="b8d81-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="b8d81-129">Основная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="b8d81-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="b8d81-130">В следующем примере показано использование предложения `orderby``descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="b8d81-130">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="b8d81-131">Примеры дополнительной сортировки</span><span class="sxs-lookup"><span data-stu-id="b8d81-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="b8d81-132">Дополнительная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="b8d81-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="b8d81-133">В следующем примере показано использование предложения `orderby` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="b8d81-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="b8d81-134">Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="b8d81-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="b8d81-135">Дополнительная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="b8d81-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="b8d81-136">В следующем примере показано использование предложения `orderby``descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="b8d81-136">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="b8d81-137">Строки сортируются основным образом по длине и дополнительно — по первой букве строки.</span><span class="sxs-lookup"><span data-stu-id="b8d81-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b8d81-138">См. также</span><span class="sxs-lookup"><span data-stu-id="b8d81-138">See Also</span></span>  
 <span data-ttu-id="b8d81-139"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="b8d81-139"><xref:System.Linq></span></span>   
 <span data-ttu-id="b8d81-140">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b8d81-140">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="b8d81-141">[Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="b8d81-141">[orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md) </span></span>  
 <span data-ttu-id="b8d81-142">[Практическое руководство. Упорядочение результатов предложения соединения](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="b8d81-142">[How to: Order the Results of a Join Clause](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span></span>  
 [<span data-ttu-id="b8d81-143">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b8d81-143">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

