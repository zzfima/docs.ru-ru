---
title: "Фильтрация данных (Visual Basic) | Документы Microsoft"
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
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fa2d3b6c5b81f137ab3a81f9b18707bb2da91f6e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="2ef56-102">Фильтрация данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ef56-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="2ef56-103">Фильтрация — это операция по ограничению значений в результирующем наборе содержат только те элементы, которые удовлетворяют указанному условию.</span><span class="sxs-lookup"><span data-stu-id="2ef56-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="2ef56-104">Это также называется выбора.</span><span class="sxs-lookup"><span data-stu-id="2ef56-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="2ef56-105">Ниже показаны результаты фильтрации последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="2ef56-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="2ef56-106">Предикат для операции фильтрации указывает, что символ должен быть «A».</span><span class="sxs-lookup"><span data-stu-id="2ef56-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="2ef56-107">![Операция фильтрации LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="2ef56-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="2ef56-108">В следующем разделе перечислены методы стандартных операторов запросов, выполняющие выбора.</span><span class="sxs-lookup"><span data-stu-id="2ef56-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ef56-109">Методы</span><span class="sxs-lookup"><span data-stu-id="2ef56-109">Methods</span></span>  
  
|<span data-ttu-id="2ef56-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="2ef56-110">Method Name</span></span>|<span data-ttu-id="2ef56-111">Описание</span><span class="sxs-lookup"><span data-stu-id="2ef56-111">Description</span></span>|<span data-ttu-id="2ef56-112">Синтаксис выражения запроса для Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ef56-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="2ef56-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2ef56-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="2ef56-114">OfType</span><span class="sxs-lookup"><span data-stu-id="2ef56-114">OfType</span></span>|<span data-ttu-id="2ef56-115">Выбирает значения в зависимости от их возможности приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="2ef56-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="2ef56-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="2ef56-116">Not applicable.</span></span>|<span data-ttu-id="2ef56-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2ef56-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2ef56-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2ef56-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="2ef56-119">Where</span><span class="sxs-lookup"><span data-stu-id="2ef56-119">Where</span></span>|<span data-ttu-id="2ef56-120">Выбирает значения, основанные на функции предиката.</span><span class="sxs-lookup"><span data-stu-id="2ef56-120">Selects values that are based on a predicate function.</span></span>|`Where`|<span data-ttu-id="2ef56-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2ef56-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2ef56-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2ef56-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="2ef56-123">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="2ef56-123">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="2ef56-124">В следующем примере используется `Where` для выбора из массива строк, имеющих определенную длину.</span><span class="sxs-lookup"><span data-stu-id="2ef56-124">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
```vb  
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim query = From word In words   
            Where word.Length = 3   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ef56-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2ef56-125">See Also</span></span>  
 <span data-ttu-id="2ef56-126"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="2ef56-126"><xref:System.Linq></span></span>   
<span data-ttu-id="2ef56-127"> [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="2ef56-127"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="2ef56-128"> [Где предложения](../../../../visual-basic/language-reference/queries/where-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2ef56-128"> [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md) </span></span>  
<span data-ttu-id="2ef56-129"> [Практическое руководство: фильтрацию результатов запроса](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="2ef56-129"> [How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="2ef56-130"> [Практическое руководство: запрос сборки метаданных с помощью отражения (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span><span class="sxs-lookup"><span data-stu-id="2ef56-130"> [How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span></span>  
<span data-ttu-id="2ef56-131"> [Практическое руководство: запрос файлов с указанными атрибутами или именем (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span><span class="sxs-lookup"><span data-stu-id="2ef56-131"> [How to: Query for Files with a Specified Attribute or Name (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span></span>  
<span data-ttu-id="2ef56-132"> [Практическое руководство: сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="2ef56-132"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
