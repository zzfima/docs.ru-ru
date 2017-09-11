---
title: "Группирование данных (Visual Basic) | Документы Microsoft"
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
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
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
ms.openlocfilehash: ce4e8f924f91eed451d3b1a02cd0bcff75589537
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="c2f9a-102">Группирование данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2f9a-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="c2f9a-103">Группирование — это операция размещения данных по группам, чтобы элементы в каждой группе имеют общий атрибут.</span><span class="sxs-lookup"><span data-stu-id="c2f9a-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="c2f9a-104">Ниже показаны результаты группировки последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="c2f9a-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="c2f9a-105">Ключ для каждой группы — это символ.</span><span class="sxs-lookup"><span data-stu-id="c2f9a-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="c2f9a-106">![Операции группировки LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="c2f9a-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="c2f9a-107">В следующем разделе перечислены методы стандартных операторов запросов, сгруппировать элементы данных.</span><span class="sxs-lookup"><span data-stu-id="c2f9a-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2f9a-108">Методы</span><span class="sxs-lookup"><span data-stu-id="c2f9a-108">Methods</span></span>  
  
|<span data-ttu-id="c2f9a-109">Имя метода</span><span class="sxs-lookup"><span data-stu-id="c2f9a-109">Method Name</span></span>|<span data-ttu-id="c2f9a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c2f9a-110">Description</span></span>|<span data-ttu-id="c2f9a-111">Синтаксис выражения запроса для Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2f9a-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="c2f9a-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c2f9a-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="c2f9a-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="c2f9a-113">GroupBy</span></span>|<span data-ttu-id="c2f9a-114">Группирует элементы с общим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="c2f9a-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="c2f9a-115">Каждая группа представлена <xref:System.Linq.IGrouping%602>объекта.</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="c2f9a-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<span data-ttu-id="c2f9a-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c2f9a-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="c2f9a-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c2f9a-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="c2f9a-118">ToLookup</span><span class="sxs-lookup"><span data-stu-id="c2f9a-118">ToLookup</span></span>|<span data-ttu-id="c2f9a-119">Добавляет элементы в <xref:System.Linq.Lookup%602>(словарь "один ко многим") на основании функции выбора ключа.</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="c2f9a-119">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="c2f9a-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="c2f9a-120">Not applicable.</span></span>|<span data-ttu-id="c2f9a-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c2f9a-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="c2f9a-122">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="c2f9a-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="c2f9a-123">В следующем примере кода `Group By` предложение для группировки целых чисел из списка на основании, являются ли они четным или нечетным.</span><span class="sxs-lookup"><span data-stu-id="c2f9a-123">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2f9a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c2f9a-124">See Also</span></span>  
 <span data-ttu-id="c2f9a-125"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="c2f9a-125"><xref:System.Linq></span></span>   
<span data-ttu-id="c2f9a-126"> [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="c2f9a-126"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="c2f9a-127"> [Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="c2f9a-127"> [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span></span>  
<span data-ttu-id="c2f9a-128"> [Практическое руководство: группировка файлов по расширению (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span><span class="sxs-lookup"><span data-stu-id="c2f9a-128"> [How to: Group Files by Extension (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span></span>  
<span data-ttu-id="c2f9a-129"> [Практическое руководство: Разделение файла на несколько файлов с помощью групп (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span><span class="sxs-lookup"><span data-stu-id="c2f9a-129"> [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span></span>
