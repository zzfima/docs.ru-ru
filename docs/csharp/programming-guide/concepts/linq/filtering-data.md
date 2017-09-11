---
title: "Фильтрация данных (C#)"
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
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: defa6716f677c44da5dd27cb64b3b1d140a65272
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="filtering-data-c"></a><span data-ttu-id="f05a6-102">Фильтрация данных (C#)</span><span class="sxs-lookup"><span data-stu-id="f05a6-102">Filtering Data (C#)</span></span>
<span data-ttu-id="f05a6-103">Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию.</span><span class="sxs-lookup"><span data-stu-id="f05a6-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="f05a6-104">Это также называется выборкой.</span><span class="sxs-lookup"><span data-stu-id="f05a6-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="f05a6-105">На следующем рисунке показаны результаты операции фильтрации последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="f05a6-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="f05a6-106">Предикат для операции фильтрации указывает, что символ должен быть "A".</span><span class="sxs-lookup"><span data-stu-id="f05a6-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="f05a6-107">![Операция фильтрации LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="f05a6-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="f05a6-108">Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="f05a6-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f05a6-109">Методы</span><span class="sxs-lookup"><span data-stu-id="f05a6-109">Methods</span></span>  
  
|<span data-ttu-id="f05a6-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="f05a6-110">Method Name</span></span>|<span data-ttu-id="f05a6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f05a6-111">Description</span></span>|<span data-ttu-id="f05a6-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="f05a6-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="f05a6-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f05a6-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="f05a6-114">OfType</span><span class="sxs-lookup"><span data-stu-id="f05a6-114">OfType</span></span>|<span data-ttu-id="f05a6-115">Выбирает значения в зависимости от возможности приведения их к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="f05a6-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="f05a6-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="f05a6-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|<span data-ttu-id="f05a6-117">Where</span><span class="sxs-lookup"><span data-stu-id="f05a6-117">Where</span></span>|<span data-ttu-id="f05a6-118">Выбирает значения, основанные на функции предиката.</span><span class="sxs-lookup"><span data-stu-id="f05a6-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="f05a6-119">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="f05a6-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="f05a6-120">В следующем примере для выбора из массива строк, имеющих определенную длину, используется предложение `where`.</span><span class="sxs-lookup"><span data-stu-id="f05a6-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="f05a6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="f05a6-121">See Also</span></span>  
 <span data-ttu-id="f05a6-122"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f05a6-122"><xref:System.Linq></span></span>   
 <span data-ttu-id="f05a6-123">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f05a6-123">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="f05a6-124">[Предложение where](../../../../csharp/language-reference/keywords/where-clause.md) </span><span class="sxs-lookup"><span data-stu-id="f05a6-124">[where clause](../../../../csharp/language-reference/keywords/where-clause.md) </span></span>  
 <span data-ttu-id="f05a6-125">[Практическое руководство. Динамическое определение фильтров предикатов во время выполнения](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="f05a6-125">[How to: Dynamically Specify Predicate Filters at Runtime](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span></span>  
 <span data-ttu-id="f05a6-126">[Практическое руководство. Выполнение запроса к метаданным сборки при помощи отражения (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f05a6-126">[How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span></span>  
 <span data-ttu-id="f05a6-127">[Практическое руководство. Запрос файлов с указанными атрибутами или именем (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span><span class="sxs-lookup"><span data-stu-id="f05a6-127">[How to: Query for Files with a Specified Attribute or Name (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span></span>  
 [<span data-ttu-id="f05a6-128">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f05a6-128">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

