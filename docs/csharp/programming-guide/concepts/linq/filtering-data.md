---
title: Фильтрация данных (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: eb448c1c2ea6d9b3fcf0120043cafebc01cd3805
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418479"
---
# <a name="filtering-data-c"></a><span data-ttu-id="99f93-102">Фильтрация данных (C#)</span><span class="sxs-lookup"><span data-stu-id="99f93-102">Filtering Data (C#)</span></span>
<span data-ttu-id="99f93-103">Фильтрация — это операция по ограничению значений в результирующем наборе только элементами, соответствующими указанному условию.</span><span class="sxs-lookup"><span data-stu-id="99f93-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="99f93-104">Это также называется выборкой.</span><span class="sxs-lookup"><span data-stu-id="99f93-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="99f93-105">На следующем рисунке показаны результаты операции фильтрации последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="99f93-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="99f93-106">Предикат для операции фильтрации указывает, что символ должен быть "A".</span><span class="sxs-lookup"><span data-stu-id="99f93-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Схема, иллюстрирующая операцию фильтрации LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="99f93-108">Методы стандартных операторов запросов, которые выполняют выборку, перечислены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="99f93-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99f93-109">Методы</span><span class="sxs-lookup"><span data-stu-id="99f93-109">Methods</span></span>  
  
|<span data-ttu-id="99f93-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="99f93-110">Method Name</span></span>|<span data-ttu-id="99f93-111">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="99f93-111">Description</span></span>|<span data-ttu-id="99f93-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="99f93-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="99f93-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="99f93-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="99f93-114">OfType</span><span class="sxs-lookup"><span data-stu-id="99f93-114">OfType</span></span>|<span data-ttu-id="99f93-115">Выбирает значения в зависимости от возможности приведения их к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="99f93-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="99f93-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="99f93-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="99f93-117">Where</span><span class="sxs-lookup"><span data-stu-id="99f93-117">Where</span></span>|<span data-ttu-id="99f93-118">Выбирает значения, основанные на функции предиката.</span><span class="sxs-lookup"><span data-stu-id="99f93-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="99f93-119">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="99f93-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="99f93-120">В следующем примере для выбора из массива строк, имеющих определенную длину, используется предложение `where`.</span><span class="sxs-lookup"><span data-stu-id="99f93-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99f93-121">См. также</span><span class="sxs-lookup"><span data-stu-id="99f93-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="99f93-122">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="99f93-122">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="99f93-123">предложение where</span><span class="sxs-lookup"><span data-stu-id="99f93-123">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="99f93-124">Практическое руководство. Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="99f93-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="99f93-125">Практическое руководство. Выполнение запроса к метаданным сборки при помощи отражения (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="99f93-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="99f93-126">Практическое руководство. Запрос файлов с указанным атрибутом или именем (C#)</span><span class="sxs-lookup"><span data-stu-id="99f93-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="99f93-127">Практическое руководство. Сортировка или фильтрация текстовых данных по любому слову или полю (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="99f93-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
