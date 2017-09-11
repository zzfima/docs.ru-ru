---
title: "Сортировка данных (Visual Basic) | Документы Microsoft"
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
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
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
ms.openlocfilehash: 1870d401ffdeeb2452ace1b74a8fb70e19c9b9ed
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="f8e36-102">Сортировка данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8e36-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="f8e36-103">Операция сортировки упорядочивает элементы последовательности на основе одного или нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f8e36-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="f8e36-104">Первый критерий сортировки выполняет первичную сортировку элементов.</span><span class="sxs-lookup"><span data-stu-id="f8e36-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="f8e36-105">Указав второй критерий поиска, можно сортировать элементы внутри каждой группы первичной сортировки.</span><span class="sxs-lookup"><span data-stu-id="f8e36-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="f8e36-106">Ниже показаны результаты операции сортировки в алфавитном порядке в последовательность символов.</span><span class="sxs-lookup"><span data-stu-id="f8e36-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="f8e36-107">![Операции сортировки LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="f8e36-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="f8e36-108">В следующем разделе перечислены методы стандартных операторов запросов, сортировка данных.</span><span class="sxs-lookup"><span data-stu-id="f8e36-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8e36-109">Методы</span><span class="sxs-lookup"><span data-stu-id="f8e36-109">Methods</span></span>  
  
|<span data-ttu-id="f8e36-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="f8e36-110">Method Name</span></span>|<span data-ttu-id="f8e36-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f8e36-111">Description</span></span>|<span data-ttu-id="f8e36-112">Синтаксис выражения запроса для Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8e36-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="f8e36-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f8e36-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="f8e36-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="f8e36-114">OrderBy</span></span>|<span data-ttu-id="f8e36-115">Сортировка значений в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="f8e36-115">Sorts values in ascending order.</span></span>|`Order By`|<span data-ttu-id="f8e36-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f8e36-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f8e36-118">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="f8e36-118">OrderByDescending</span></span>|<span data-ttu-id="f8e36-119">Сортировка значений в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="f8e36-119">Sorts values in descending order.</span></span>|`Order By … Descending`|<span data-ttu-id="f8e36-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f8e36-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f8e36-122">ThenBy</span><span class="sxs-lookup"><span data-stu-id="f8e36-122">ThenBy</span></span>|<span data-ttu-id="f8e36-123">Дополнительная сортировка по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="f8e36-123">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<span data-ttu-id="f8e36-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f8e36-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f8e36-126">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="f8e36-126">ThenByDescending</span></span>|<span data-ttu-id="f8e36-127">Дополнительная сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="f8e36-127">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<span data-ttu-id="f8e36-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f8e36-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f8e36-130">Reverse</span><span class="sxs-lookup"><span data-stu-id="f8e36-130">Reverse</span></span>|<span data-ttu-id="f8e36-131">Изменяет порядок элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="f8e36-131">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="f8e36-132">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="f8e36-132">Not applicable.</span></span>|<span data-ttu-id="f8e36-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f8e36-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8e36-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f8e36-135">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="f8e36-135">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="f8e36-136">Примеры основной сортировки</span><span class="sxs-lookup"><span data-stu-id="f8e36-136">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="f8e36-137">Основная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="f8e36-137">Primary Ascending Sort</span></span>  
 <span data-ttu-id="f8e36-138">В следующем примере демонстрируется использование `Order By` предложение в запросе LINQ для сортировки строк в массиве по длине строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="f8e36-138">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="f8e36-139">Основная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="f8e36-139">Primary Descending Sort</span></span>  
 <span data-ttu-id="f8e36-140">В следующем примере демонстрируется использование `Order By Descending` предложение в запросе LINQ для сортировки строк по их первой букве в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="f8e36-140">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="f8e36-141">Примеры дополнительной сортировки</span><span class="sxs-lookup"><span data-stu-id="f8e36-141">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="f8e36-142">Дополнительная сортировка по возрастанию</span><span class="sxs-lookup"><span data-stu-id="f8e36-142">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="f8e36-143">В следующем примере демонстрируется использование `Order By` предложение в запросе LINQ для выполнения основной и дополнительной сортировки строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="f8e36-143">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="f8e36-144">Строки сортируются основным образом по длине и дополнительным — по первой букве строки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="f8e36-144">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="f8e36-145">Дополнительная сортировка по убыванию</span><span class="sxs-lookup"><span data-stu-id="f8e36-145">Secondary Descending Sort</span></span>  
 <span data-ttu-id="f8e36-146">В следующем примере демонстрируется использование `Order By Descending` предложение в запросе LINQ для выполнения основной сортировки в возрастающем порядке, а дополнительная Сортировка по убыванию.</span><span class="sxs-lookup"><span data-stu-id="f8e36-146">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="f8e36-147">Строки сортируются основным образом по длине и дополнительным — по первой букве строки.</span><span class="sxs-lookup"><span data-stu-id="f8e36-147">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8e36-148">См. также</span><span class="sxs-lookup"><span data-stu-id="f8e36-148">See Also</span></span>  
 <span data-ttu-id="f8e36-149"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f8e36-149"><xref:System.Linq></span></span>   
<span data-ttu-id="f8e36-150"> [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f8e36-150"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="f8e36-151"> [Предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="f8e36-151"> [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="f8e36-152"> [Практическое руководство: сортировка результатов запроса](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f8e36-152"> [How to: Sort Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="f8e36-153"> [Практическое руководство: сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f8e36-153"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
