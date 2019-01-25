---
title: Секционирование данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: afbbd479d3dadd69b81cdd6aead0a4263b92dfe9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728272"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="4e6f8-102">Секционирование данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e6f8-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="4e6f8-103">Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="4e6f8-104">На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="4e6f8-105">Первая операция возвращает первые три элемента в последовательности.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="4e6f8-106">Вторая операция пропускает первые три элемента и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="4e6f8-107">Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="4e6f8-108">![Операции секционирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="4e6f8-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="4e6f8-109">Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="4e6f8-110">Операторы</span><span class="sxs-lookup"><span data-stu-id="4e6f8-110">Operators</span></span>  
  
|<span data-ttu-id="4e6f8-111">Имя оператора</span><span class="sxs-lookup"><span data-stu-id="4e6f8-111">Operator Name</span></span>|<span data-ttu-id="4e6f8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4e6f8-112">Description</span></span>|<span data-ttu-id="4e6f8-113">Синтаксис выражений запросов Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e6f8-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="4e6f8-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4e6f8-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="4e6f8-115">Skip</span><span class="sxs-lookup"><span data-stu-id="4e6f8-115">Skip</span></span>|<span data-ttu-id="4e6f8-116">Пропускает элементы до указанной позиции в последовательности.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4e6f8-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4e6f8-117">SkipWhile</span></span>|<span data-ttu-id="4e6f8-118">Пропускает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4e6f8-119">Take</span><span class="sxs-lookup"><span data-stu-id="4e6f8-119">Take</span></span>|<span data-ttu-id="4e6f8-120">Возвращает элементы на указанную позицию в последовательности.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4e6f8-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4e6f8-121">TakeWhile</span></span>|<span data-ttu-id="4e6f8-122">Принимает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="4e6f8-123">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="4e6f8-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="4e6f8-124">Skip</span><span class="sxs-lookup"><span data-stu-id="4e6f8-124">Skip</span></span>  
 <span data-ttu-id="4e6f8-125">В следующем примере кода используется `Skip` предложение в Visual Basic, чтобы пропустить первые четыре строки в массиве строк перед возвращением оставшихся строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a><span data-ttu-id="4e6f8-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4e6f8-126">SkipWhile</span></span>  
 <span data-ttu-id="4e6f8-127">В следующем примере кода используется `Skip While` предложение в Visual Basic для пропуска строк в массиве, при первой буквы строки «».</span><span class="sxs-lookup"><span data-stu-id="4e6f8-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="4e6f8-128">Возвращаются оставшихся строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a><span data-ttu-id="4e6f8-129">Take</span><span class="sxs-lookup"><span data-stu-id="4e6f8-129">Take</span></span>  
 <span data-ttu-id="4e6f8-130">В следующем примере кода используется `Take` предложение в Visual Basic для возврата первых двух строк в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a><span data-ttu-id="4e6f8-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4e6f8-131">TakeWhile</span></span>  
 <span data-ttu-id="4e6f8-132">В следующем примере кода используется `Take While` предложение в Visual Basic для получения строк из массива, тогда как длина строки меньше пяти.</span><span class="sxs-lookup"><span data-stu-id="4e6f8-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4e6f8-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4e6f8-133">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="4e6f8-134">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e6f8-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="4e6f8-135">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="4e6f8-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="4e6f8-136">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="4e6f8-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="4e6f8-137">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="4e6f8-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="4e6f8-138">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="4e6f8-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
