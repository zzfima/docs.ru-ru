---
title: "Группирование данных (C#)"
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
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2cf1b228a5ff4120bdf3b97a7ec9308f11d7b8ee
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="grouping-data-c"></a><span data-ttu-id="dd663-102">Группирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="dd663-102">Grouping Data (C#)</span></span>
<span data-ttu-id="dd663-103">Группированием называют операцию объединения данных в группы таким образом, чтобы у элементов в каждой группе был общий атрибут.</span><span class="sxs-lookup"><span data-stu-id="dd663-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="dd663-104">На следующем рисунке показаны результаты операции группирования последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="dd663-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="dd663-105">Ключ для каждой группы — это символ.</span><span class="sxs-lookup"><span data-stu-id="dd663-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="dd663-106">![Операции группирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="dd663-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="dd663-107">Далее перечислены методы стандартных операторов запроса, которые группируют элементы данных.</span><span class="sxs-lookup"><span data-stu-id="dd663-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd663-108">Методы</span><span class="sxs-lookup"><span data-stu-id="dd663-108">Methods</span></span>  
  
|<span data-ttu-id="dd663-109">Имя метода</span><span class="sxs-lookup"><span data-stu-id="dd663-109">Method Name</span></span>|<span data-ttu-id="dd663-110">Описание</span><span class="sxs-lookup"><span data-stu-id="dd663-110">Description</span></span>|<span data-ttu-id="dd663-111">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="dd663-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="dd663-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="dd663-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="dd663-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="dd663-113">GroupBy</span></span>|<span data-ttu-id="dd663-114">Группирует элементы с общим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="dd663-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="dd663-115">Каждая группа представлена объектом <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="dd663-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="dd663-116">-или-</span><span class="sxs-lookup"><span data-stu-id="dd663-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="dd663-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="dd663-117">ToLookup</span></span>|<span data-ttu-id="dd663-118">Вставляет элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="dd663-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="dd663-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="dd663-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="dd663-120">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="dd663-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="dd663-121">В следующем примере кода предложение `group by` используется для группирования целых чисел в списке на основании четности.</span><span class="sxs-lookup"><span data-stu-id="dd663-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd663-122">См. также</span><span class="sxs-lookup"><span data-stu-id="dd663-122">See Also</span></span>  
 <span data-ttu-id="dd663-123"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="dd663-123"><xref:System.Linq></span></span>   
 <span data-ttu-id="dd663-124">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="dd663-124">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="dd663-125">[Предложение group](../../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="dd663-125">[group clause](../../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 <span data-ttu-id="dd663-126">[Практическое руководство. Создание вложенной группы](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md) </span><span class="sxs-lookup"><span data-stu-id="dd663-126">[How to: Create a Nested Group](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md) </span></span>  
 <span data-ttu-id="dd663-127">[Практическое руководство. Группировка файлов по расширению (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span><span class="sxs-lookup"><span data-stu-id="dd663-127">[How to: Group Files by Extension (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span></span>  
 <span data-ttu-id="dd663-128">[Практическое руководство. Группировка результатов запросов](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md) </span><span class="sxs-lookup"><span data-stu-id="dd663-128">[How to: Group Query Results](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md) </span></span>  
 <span data-ttu-id="dd663-129">[Практическое руководство. Вложенный запрос в операции группирования](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md) </span><span class="sxs-lookup"><span data-stu-id="dd663-129">[How to: Perform a Subquery on a Grouping Operation](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md) </span></span>  
 [<span data-ttu-id="dd663-130">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="dd663-130">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)

