---
title: Сортировка данных (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 8db5ab2ead0e59b8d41d83704ff237d4493155c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346456"
---
# <a name="sorting-data-c"></a><span data-ttu-id="e847d-102">Сортировка данных (C#)</span><span class="sxs-lookup"><span data-stu-id="e847d-102">Sorting Data (C#)</span></span>
<span data-ttu-id="e847d-103">Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e847d-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="e847d-104">Первый критерий сортировки выполняет первичную сортировку элементов.</span><span class="sxs-lookup"><span data-stu-id="e847d-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="e847d-105">Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="e847d-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="e847d-106">На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов:</span><span class="sxs-lookup"><span data-stu-id="e847d-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span> 
  
 ![Рисунок с операциями сортировки в алфавитном порядке.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="e847d-108">Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.</span><span class="sxs-lookup"><span data-stu-id="e847d-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e847d-109">Методы</span><span class="sxs-lookup"><span data-stu-id="e847d-109">Methods</span></span>  
  
|<span data-ttu-id="e847d-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="e847d-110">Method Name</span></span>|<span data-ttu-id="e847d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e847d-111">Description</span></span>|<span data-ttu-id="e847d-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="e847d-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="e847d-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e847d-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="e847d-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="e847d-114">OrderBy</span></span>|<span data-ttu-id="e847d-115">Сортировка значений в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="e847d-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e847d-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="e847d-116">OrderByDescending</span></span>|<span data-ttu-id="e847d-117">Сортировка значений в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="e847d-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e847d-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="e847d-118">ThenBy</span></span>|<span data-ttu-id="e847d-119">Дополнительная сортировка по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="e847d-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e847d-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="e847d-120">ThenByDescending</span></span>|<span data-ttu-id="e847d-121">Дополнительная сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="e847d-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e847d-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="e847d-122">Reverse</span></span>|<span data-ttu-id="e847d-123">Изменение порядка элементов в коллекции на обратный.</span><span class="sxs-lookup"><span data-stu-id="e847d-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="e847d-124">Не применяется</span><span class="sxs-lookup"><span data-stu-id="e847d-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="e847d-125">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="e847d-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="e847d-126">Примеры основной сортировки</span><span class="sxs-lookup"><span data-stu-id="e847d-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="e847d-127">Основная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="e847d-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="e847d-128">В следующем примере показано использование предложения `orderby` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="e847d-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="e847d-129">Основная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="e847d-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="e847d-130">В следующем примере показано использование предложения `orderby descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="e847d-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="e847d-131">Примеры дополнительной сортировки</span><span class="sxs-lookup"><span data-stu-id="e847d-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="e847d-132">Дополнительная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="e847d-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="e847d-133">В следующем примере показано использование предложения `orderby` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="e847d-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="e847d-134">Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="e847d-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="e847d-135">Дополнительная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="e847d-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="e847d-136">В следующем примере показано использование предложения `orderby descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="e847d-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="e847d-137">Строки сортируются основным образом по длине и дополнительно — по первой букве строки.</span><span class="sxs-lookup"><span data-stu-id="e847d-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e847d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="e847d-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="e847d-139">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="e847d-139">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="e847d-140">предложение orderby</span><span class="sxs-lookup"><span data-stu-id="e847d-140">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="e847d-141">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="e847d-141">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="e847d-142">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="e847d-142">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
