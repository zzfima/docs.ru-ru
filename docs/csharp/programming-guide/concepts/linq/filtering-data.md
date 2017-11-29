---
title: "Фильтрация данных (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77a68d5fa0fa606a7d164adf187c8aa0027170bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="filtering-data-c"></a><span data-ttu-id="50bb2-102">Фильтрация данных (C#)</span><span class="sxs-lookup"><span data-stu-id="50bb2-102">Filtering Data (C#)</span></span>
<span data-ttu-id="50bb2-103">Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию.</span><span class="sxs-lookup"><span data-stu-id="50bb2-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="50bb2-104">Это также называется выборкой.</span><span class="sxs-lookup"><span data-stu-id="50bb2-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="50bb2-105">На следующем рисунке показаны результаты операции фильтрации последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="50bb2-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="50bb2-106">Предикат для операции фильтрации указывает, что символ должен быть "A".</span><span class="sxs-lookup"><span data-stu-id="50bb2-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="50bb2-107">![Операция фильтрации LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="50bb2-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="50bb2-108">Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="50bb2-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50bb2-109">Методы</span><span class="sxs-lookup"><span data-stu-id="50bb2-109">Methods</span></span>  
  
|<span data-ttu-id="50bb2-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="50bb2-110">Method Name</span></span>|<span data-ttu-id="50bb2-111">Описание</span><span class="sxs-lookup"><span data-stu-id="50bb2-111">Description</span></span>|<span data-ttu-id="50bb2-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="50bb2-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="50bb2-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="50bb2-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="50bb2-114">OfType</span><span class="sxs-lookup"><span data-stu-id="50bb2-114">OfType</span></span>|<span data-ttu-id="50bb2-115">Выбирает значения в зависимости от возможности приведения их к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="50bb2-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="50bb2-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="50bb2-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="50bb2-117">Where</span><span class="sxs-lookup"><span data-stu-id="50bb2-117">Where</span></span>|<span data-ttu-id="50bb2-118">Выбирает значения, основанные на функции предиката.</span><span class="sxs-lookup"><span data-stu-id="50bb2-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="50bb2-119">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="50bb2-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="50bb2-120">В следующем примере для выбора из массива строк, имеющих определенную длину, используется предложение `where`.</span><span class="sxs-lookup"><span data-stu-id="50bb2-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="50bb2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="50bb2-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="50bb2-122">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="50bb2-122">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="50bb2-123">предложение where</span><span class="sxs-lookup"><span data-stu-id="50bb2-123">where clause</span></span>](../../../../csharp/language-reference/keywords/where-clause.md)  
 [<span data-ttu-id="50bb2-124">Практическое руководство. Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="50bb2-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
 [<span data-ttu-id="50bb2-125">Практическое руководство. Выполнение запроса к метаданным сборки при помощи отражения (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="50bb2-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [<span data-ttu-id="50bb2-126">Практическое руководство. Запрос файлов с указанными атрибутами или именем (C#)</span><span class="sxs-lookup"><span data-stu-id="50bb2-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [<span data-ttu-id="50bb2-127">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="50bb2-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
