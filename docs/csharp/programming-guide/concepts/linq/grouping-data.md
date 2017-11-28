---
title: "Группирование данных (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4aef8d10eaffb384fe919ffa6a1e742cb837f540
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="grouping-data-c"></a><span data-ttu-id="5a83c-102">Группирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="5a83c-102">Grouping Data (C#)</span></span>
<span data-ttu-id="5a83c-103">Группированием называют операцию объединения данных в группы таким образом, чтобы у элементов в каждой группе был общий атрибут.</span><span class="sxs-lookup"><span data-stu-id="5a83c-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="5a83c-104">На следующем рисунке показаны результаты операции группирования последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="5a83c-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="5a83c-105">Ключ для каждой группы — это символ.</span><span class="sxs-lookup"><span data-stu-id="5a83c-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="5a83c-106">![Операции группирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="5a83c-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="5a83c-107">Далее перечислены методы стандартных операторов запроса, которые группируют элементы данных.</span><span class="sxs-lookup"><span data-stu-id="5a83c-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a83c-108">Методы</span><span class="sxs-lookup"><span data-stu-id="5a83c-108">Methods</span></span>  
  
|<span data-ttu-id="5a83c-109">Имя метода</span><span class="sxs-lookup"><span data-stu-id="5a83c-109">Method Name</span></span>|<span data-ttu-id="5a83c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5a83c-110">Description</span></span>|<span data-ttu-id="5a83c-111">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="5a83c-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="5a83c-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5a83c-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="5a83c-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="5a83c-113">GroupBy</span></span>|<span data-ttu-id="5a83c-114">Группирует элементы с общим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="5a83c-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="5a83c-115">Каждая группа представлена объектом <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="5a83c-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="5a83c-116">-или-</span><span class="sxs-lookup"><span data-stu-id="5a83c-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5a83c-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="5a83c-117">ToLookup</span></span>|<span data-ttu-id="5a83c-118">Вставляет элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="5a83c-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="5a83c-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="5a83c-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="5a83c-120">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="5a83c-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="5a83c-121">В следующем примере кода предложение `group by` используется для группирования целых чисел в списке на основании четности.</span><span class="sxs-lookup"><span data-stu-id="5a83c-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5a83c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5a83c-122">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="5a83c-123">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="5a83c-123">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="5a83c-124">предложение group</span><span class="sxs-lookup"><span data-stu-id="5a83c-124">group clause</span></span>](../../../../csharp/language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="5a83c-125">Практическое руководство. Создание вложенной группы</span><span class="sxs-lookup"><span data-stu-id="5a83c-125">How to: Create a Nested Group</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)  
 [<span data-ttu-id="5a83c-126">Практическое руководство. Группировка файлов по расширению (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5a83c-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 [<span data-ttu-id="5a83c-127">Практическое руководство. Группировка результатов запросов</span><span class="sxs-lookup"><span data-stu-id="5a83c-127">How to: Group Query Results</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)  
 [<span data-ttu-id="5a83c-128">Практическое руководство. Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="5a83c-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="5a83c-129">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5a83c-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
