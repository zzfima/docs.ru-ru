---
title: Секционирование данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 2da63a1f6b73c8592d6036a90fa374a0d4385f4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839578"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="bfdd0-102">Секционирование данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfdd0-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="bfdd0-103">Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="bfdd0-104">На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="bfdd0-105">Первая операция возвращает первые три элемента в последовательности.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="bfdd0-106">Вторая операция пропускает первые три элемента и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="bfdd0-107">Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Рисунок иллюстрирующий три операции секционирования LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="bfdd0-109">Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="bfdd0-110">Операторы</span><span class="sxs-lookup"><span data-stu-id="bfdd0-110">Operators</span></span>  
  
|<span data-ttu-id="bfdd0-111">Имя оператора</span><span class="sxs-lookup"><span data-stu-id="bfdd0-111">Operator Name</span></span>|<span data-ttu-id="bfdd0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bfdd0-112">Description</span></span>|<span data-ttu-id="bfdd0-113">Синтаксис выражений запросов Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfdd0-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="bfdd0-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="bfdd0-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="bfdd0-115">Skip</span><span class="sxs-lookup"><span data-stu-id="bfdd0-115">Skip</span></span>|<span data-ttu-id="bfdd0-116">Пропускает элементы до указанной позиции в последовательности.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bfdd0-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="bfdd0-117">SkipWhile</span></span>|<span data-ttu-id="bfdd0-118">Пропускает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bfdd0-119">Take</span><span class="sxs-lookup"><span data-stu-id="bfdd0-119">Take</span></span>|<span data-ttu-id="bfdd0-120">Возвращает элементы на указанную позицию в последовательности.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bfdd0-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="bfdd0-121">TakeWhile</span></span>|<span data-ttu-id="bfdd0-122">Принимает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="bfdd0-123">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="bfdd0-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="bfdd0-124">Skip</span><span class="sxs-lookup"><span data-stu-id="bfdd0-124">Skip</span></span>  
 <span data-ttu-id="bfdd0-125">В следующем примере кода используется `Skip` предложение в Visual Basic, чтобы пропустить первые четыре строки в массиве строк перед возвращением оставшихся строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="bfdd0-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="bfdd0-126">SkipWhile</span></span>  
 <span data-ttu-id="bfdd0-127">В следующем примере кода используется `Skip While` предложение в Visual Basic для пропуска строк в массиве, при первой буквы строки «».</span><span class="sxs-lookup"><span data-stu-id="bfdd0-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="bfdd0-128">Возвращаются оставшихся строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="bfdd0-129">Take</span><span class="sxs-lookup"><span data-stu-id="bfdd0-129">Take</span></span>  
 <span data-ttu-id="bfdd0-130">В следующем примере кода используется `Take` предложение в Visual Basic для возврата первых двух строк в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="bfdd0-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="bfdd0-131">TakeWhile</span></span>  
 <span data-ttu-id="bfdd0-132">В следующем примере кода используется `Take While` предложение в Visual Basic для получения строк из массива, тогда как длина строки меньше пяти.</span><span class="sxs-lookup"><span data-stu-id="bfdd0-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="bfdd0-133">См. также</span><span class="sxs-lookup"><span data-stu-id="bfdd0-133">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="bfdd0-134">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfdd0-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="bfdd0-135">Предложение Skip</span><span class="sxs-lookup"><span data-stu-id="bfdd0-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="bfdd0-136">Предложение Skip While</span><span class="sxs-lookup"><span data-stu-id="bfdd0-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="bfdd0-137">Предложение Take</span><span class="sxs-lookup"><span data-stu-id="bfdd0-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="bfdd0-138">Предложение Take While</span><span class="sxs-lookup"><span data-stu-id="bfdd0-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
