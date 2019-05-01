---
title: Группирование данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: b5a6a3795e02e0638b81824701ad0cbacbcca91a
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808137"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="fc654-102">Группирование данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc654-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="fc654-103">Группированием называют операцию объединения данных в группы таким образом, чтобы у элементов в каждой группе был общий атрибут.</span><span class="sxs-lookup"><span data-stu-id="fc654-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="fc654-104">На следующем рисунке показаны результаты операции группирования последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="fc654-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="fc654-105">Ключ для каждой группы — это символ.</span><span class="sxs-lookup"><span data-stu-id="fc654-105">The key for each group is the character.</span></span>  
  
 ![Схема, показывающая операции группирования LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="fc654-107">Далее перечислены методы стандартных операторов запроса, которые группируют элементы данных.</span><span class="sxs-lookup"><span data-stu-id="fc654-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc654-108">Методы</span><span class="sxs-lookup"><span data-stu-id="fc654-108">Methods</span></span>  
  
|<span data-ttu-id="fc654-109">Имя метода</span><span class="sxs-lookup"><span data-stu-id="fc654-109">Method Name</span></span>|<span data-ttu-id="fc654-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fc654-110">Description</span></span>|<span data-ttu-id="fc654-111">Синтаксис выражений запросов Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc654-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="fc654-112">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="fc654-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="fc654-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="fc654-113">GroupBy</span></span>|<span data-ttu-id="fc654-114">Группирует элементы с общим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="fc654-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="fc654-115">Каждая группа представлена объектом <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="fc654-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fc654-116">ToLookup</span><span class="sxs-lookup"><span data-stu-id="fc654-116">ToLookup</span></span>|<span data-ttu-id="fc654-117">Вставляет элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="fc654-117">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="fc654-118">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="fc654-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="fc654-119">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="fc654-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="fc654-120">В следующем примере кода предложение `Group By` используется для группирования целых чисел в списке на основании четности.</span><span class="sxs-lookup"><span data-stu-id="fc654-120">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc654-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fc654-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="fc654-122">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc654-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="fc654-123">Предложение Group By</span><span class="sxs-lookup"><span data-stu-id="fc654-123">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="fc654-124">Практическое руководство. Группировать файлы по расширению (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc654-124">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="fc654-125">Практическое руководство. Разделение файла на несколько файлов с помощью групп (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc654-125">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
