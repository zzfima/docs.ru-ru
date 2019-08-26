---
title: Группирование данных (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 15dafdb144ee9fd4184d4c8281d041e03161a16b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594200"
---
# <a name="grouping-data-c"></a><span data-ttu-id="fe397-102">Группирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="fe397-102">Grouping Data (C#)</span></span>
<span data-ttu-id="fe397-103">Группированием называют операцию объединения данных в группы таким образом, чтобы у элементов в каждой группе был общий атрибут.</span><span class="sxs-lookup"><span data-stu-id="fe397-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="fe397-104">На следующем рисунке показаны результаты операции группирования последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="fe397-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="fe397-105">Ключ для каждой группы — это символ.</span><span class="sxs-lookup"><span data-stu-id="fe397-105">The key for each group is the character.</span></span>  
  
 ![Схема, показывающая операцию группирования LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="fe397-107">Далее перечислены методы стандартных операторов запроса, которые группируют элементы данных.</span><span class="sxs-lookup"><span data-stu-id="fe397-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe397-108">Методы</span><span class="sxs-lookup"><span data-stu-id="fe397-108">Methods</span></span>  
  
|<span data-ttu-id="fe397-109">Имя метода</span><span class="sxs-lookup"><span data-stu-id="fe397-109">Method Name</span></span>|<span data-ttu-id="fe397-110">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="fe397-110">Description</span></span>|<span data-ttu-id="fe397-111">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="fe397-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="fe397-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="fe397-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="fe397-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="fe397-113">GroupBy</span></span>|<span data-ttu-id="fe397-114">Группирует элементы с общим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="fe397-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="fe397-115">Каждая группа представлена объектом <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="fe397-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="fe397-116">-или-</span><span class="sxs-lookup"><span data-stu-id="fe397-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fe397-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="fe397-117">ToLookup</span></span>|<span data-ttu-id="fe397-118">Вставляет элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="fe397-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="fe397-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="fe397-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="fe397-120">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="fe397-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="fe397-121">В следующем примере кода предложение `group by` используется для группирования целых чисел в списке на основании четности.</span><span class="sxs-lookup"><span data-stu-id="fe397-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe397-122">См. также</span><span class="sxs-lookup"><span data-stu-id="fe397-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="fe397-123">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="fe397-123">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="fe397-124">предложение group</span><span class="sxs-lookup"><span data-stu-id="fe397-124">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="fe397-125">Практическое руководство. Создание вложенной группы</span><span class="sxs-lookup"><span data-stu-id="fe397-125">How to: Create a Nested Group</span></span>](../../linq-query-expressions/how-to-create-a-nested-group.md)
- [<span data-ttu-id="fe397-126">Практическое руководство. Группировка файлов по расширению (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe397-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="fe397-127">Практическое руководство. Группировка результатов запросов</span><span class="sxs-lookup"><span data-stu-id="fe397-127">How to: Group Query Results</span></span>](../../linq-query-expressions/how-to-group-query-results.md)
- [<span data-ttu-id="fe397-128">Практическое руководство. Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="fe397-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="fe397-129">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe397-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
