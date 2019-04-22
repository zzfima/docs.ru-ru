---
title: Сортировка данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: ad39aca6a53221f077a6b8313262d508744ff5ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819090"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="721bb-102">Сортировка данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="721bb-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="721bb-103">Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="721bb-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="721bb-104">Первый критерий сортировки выполняет первичную сортировку элементов.</span><span class="sxs-lookup"><span data-stu-id="721bb-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="721bb-105">Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="721bb-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="721bb-106">На следующем рисунке показаны результаты операции сортировки в алфавитном порядке в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="721bb-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 ![Рисунок с операциями сортировки в алфавитном порядке.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="721bb-108">Далее перечислены методы стандартных операторов запроса, которые выполняют сортировку данных.</span><span class="sxs-lookup"><span data-stu-id="721bb-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="721bb-109">Методы</span><span class="sxs-lookup"><span data-stu-id="721bb-109">Methods</span></span>  
  
|<span data-ttu-id="721bb-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="721bb-110">Method Name</span></span>|<span data-ttu-id="721bb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="721bb-111">Description</span></span>|<span data-ttu-id="721bb-112">Синтаксис выражений запросов Visual Basic</span><span class="sxs-lookup"><span data-stu-id="721bb-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="721bb-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="721bb-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="721bb-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="721bb-114">OrderBy</span></span>|<span data-ttu-id="721bb-115">Сортировка значений в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="721bb-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="721bb-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="721bb-116">OrderByDescending</span></span>|<span data-ttu-id="721bb-117">Сортировка значений в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="721bb-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="721bb-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="721bb-118">ThenBy</span></span>|<span data-ttu-id="721bb-119">Дополнительная сортировка по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="721bb-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="721bb-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="721bb-120">ThenByDescending</span></span>|<span data-ttu-id="721bb-121">Дополнительная сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="721bb-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="721bb-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="721bb-122">Reverse</span></span>|<span data-ttu-id="721bb-123">Изменение порядка элементов в коллекции на обратный.</span><span class="sxs-lookup"><span data-stu-id="721bb-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="721bb-124">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="721bb-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="721bb-125">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="721bb-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="721bb-126">Примеры основной сортировки</span><span class="sxs-lookup"><span data-stu-id="721bb-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="721bb-127">Основная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="721bb-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="721bb-128">В следующем примере показано использование предложения `Order By` в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="721bb-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
' quick  
' brown  
' jumps  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="721bb-129">Основная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="721bb-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="721bb-130">В следующем примере показано использование предложения `Order By Descending` в запросе LINQ для сортировки строк по их первой букве в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="721bb-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' quick  
' jumps  
' fox  
' brown  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="721bb-131">Примеры дополнительной сортировки</span><span class="sxs-lookup"><span data-stu-id="721bb-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="721bb-132">Дополнительная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="721bb-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="721bb-133">В следующем примере показано использование предложения `Order By` в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="721bb-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="721bb-134">Строки сортируются основным образом по длине и дополнительно — по первой букве строки; в обоих случаях в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="721bb-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1)   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' brown  
' jumps  
' quick  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="721bb-135">Дополнительная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="721bb-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="721bb-136">В следующем примере показано использование предложения `Order By Descending` в запросе LINQ для выполнения основной сортировки по возрастанию и дополнительной сортировки по убыванию.</span><span class="sxs-lookup"><span data-stu-id="721bb-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="721bb-137">Строки сортируются основным образом по длине и дополнительно — по первой букве строки.</span><span class="sxs-lookup"><span data-stu-id="721bb-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' quick  
' jumps  
' brown  
```  
  
## <a name="see-also"></a><span data-ttu-id="721bb-138">См. также</span><span class="sxs-lookup"><span data-stu-id="721bb-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="721bb-139">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="721bb-139">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="721bb-140">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="721bb-140">Order By Clause</span></span>](../../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="721bb-141">Практическое руководство. Сортировка результатов запроса</span><span class="sxs-lookup"><span data-stu-id="721bb-141">How to: Sort Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [<span data-ttu-id="721bb-142">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="721bb-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
