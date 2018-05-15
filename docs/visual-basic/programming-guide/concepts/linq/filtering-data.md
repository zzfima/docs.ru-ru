---
title: Фильтрация данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: d3f44d0b6478103a10fb731988aeebc005cde82e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="1cf94-102">Фильтрация данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cf94-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="1cf94-103">Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию.</span><span class="sxs-lookup"><span data-stu-id="1cf94-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="1cf94-104">Это также называется выборкой.</span><span class="sxs-lookup"><span data-stu-id="1cf94-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="1cf94-105">На следующем рисунке показаны результаты операции фильтрации последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="1cf94-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="1cf94-106">Предикат для операции фильтрации указывает, что символ должен быть "A".</span><span class="sxs-lookup"><span data-stu-id="1cf94-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="1cf94-107">![Операция фильтрации LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="1cf94-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="1cf94-108">Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="1cf94-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1cf94-109">Методы</span><span class="sxs-lookup"><span data-stu-id="1cf94-109">Methods</span></span>  
  
|<span data-ttu-id="1cf94-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="1cf94-110">Method Name</span></span>|<span data-ttu-id="1cf94-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1cf94-111">Description</span></span>|<span data-ttu-id="1cf94-112">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cf94-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="1cf94-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="1cf94-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="1cf94-114">OfType</span><span class="sxs-lookup"><span data-stu-id="1cf94-114">OfType</span></span>|<span data-ttu-id="1cf94-115">Выбирает значения в зависимости от возможности приведения их к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="1cf94-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="1cf94-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="1cf94-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1cf94-117">Where</span><span class="sxs-lookup"><span data-stu-id="1cf94-117">Where</span></span>|<span data-ttu-id="1cf94-118">Выбирает значения, основанные на функции предиката.</span><span class="sxs-lookup"><span data-stu-id="1cf94-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="1cf94-119">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="1cf94-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="1cf94-120">В следующем примере используется `Where` для выбора из массива строк, имеющих определенную длину.</span><span class="sxs-lookup"><span data-stu-id="1cf94-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1cf94-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1cf94-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="1cf94-122">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cf94-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="1cf94-123">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="1cf94-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)  
 <span data-ttu-id="1cf94-124">[How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) (Практическое руководство. Фильтрование результатов запроса)</span><span class="sxs-lookup"><span data-stu-id="1cf94-124">[How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)</span></span>  
 [<span data-ttu-id="1cf94-125">Как: запрос к метаданным сборки при помощи отражения (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cf94-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [<span data-ttu-id="1cf94-126">Как: запрос файлов с помощью указанного атрибута или имени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cf94-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [<span data-ttu-id="1cf94-127">Как: сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cf94-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
