---
title: Фильтрация данных
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 81e207e451055fb2952e4bf393db067f0851afb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353489"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="b9f64-102">Filtering Data (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9f64-102">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="b9f64-103">Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию.</span><span class="sxs-lookup"><span data-stu-id="b9f64-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="b9f64-104">Это также называется выборкой.</span><span class="sxs-lookup"><span data-stu-id="b9f64-104">It is also known as selection.</span></span>

<span data-ttu-id="b9f64-105">На следующем рисунке показаны результаты операции фильтрации последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="b9f64-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="b9f64-106">Предикат для операции фильтрации указывает, что символ должен быть "A".</span><span class="sxs-lookup"><span data-stu-id="b9f64-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![Схема, иллюстрирующая операцию фильтрации LINQ](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="b9f64-108">Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="b9f64-108">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="b9f64-109">Методы</span><span class="sxs-lookup"><span data-stu-id="b9f64-109">Methods</span></span>

|<span data-ttu-id="b9f64-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="b9f64-110">Method Name</span></span>|<span data-ttu-id="b9f64-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b9f64-111">Description</span></span>|<span data-ttu-id="b9f64-112">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="b9f64-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="b9f64-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b9f64-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="b9f64-114">OfType</span><span class="sxs-lookup"><span data-stu-id="b9f64-114">OfType</span></span>|<span data-ttu-id="b9f64-115">Выбирает значения в зависимости от возможности приведения их к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="b9f64-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="b9f64-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b9f64-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b9f64-117">Where</span><span class="sxs-lookup"><span data-stu-id="b9f64-117">Where</span></span>|<span data-ttu-id="b9f64-118">Выбирает значения, основанные на функции предиката.</span><span class="sxs-lookup"><span data-stu-id="b9f64-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="b9f64-119">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="b9f64-119">Query Expression Syntax Example</span></span>

<span data-ttu-id="b9f64-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span><span class="sxs-lookup"><span data-stu-id="b9f64-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b9f64-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b9f64-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b9f64-122">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9f64-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b9f64-123">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="b9f64-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- <span data-ttu-id="b9f64-124">[How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) (Практическое руководство. Фильтрование результатов запроса)</span><span class="sxs-lookup"><span data-stu-id="b9f64-124">[How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)</span></span>
- [<span data-ttu-id="b9f64-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9f64-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="b9f64-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9f64-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="b9f64-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9f64-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
