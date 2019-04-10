---
title: Секционирование данных (C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: b857c8c6e6b56a7263e6725a747e98ccfe4ff4fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832467"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="a78f7-102">Секционирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="a78f7-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="a78f7-103">Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.</span><span class="sxs-lookup"><span data-stu-id="a78f7-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="a78f7-104">На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="a78f7-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="a78f7-105">Первая операция возвращает первые три элемента в последовательности.</span><span class="sxs-lookup"><span data-stu-id="a78f7-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="a78f7-106">Вторая операция пропускает первые три элемента и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="a78f7-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="a78f7-107">Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.</span><span class="sxs-lookup"><span data-stu-id="a78f7-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Рисунок иллюстрирующий три операции секционирования LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="a78f7-109">Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.</span><span class="sxs-lookup"><span data-stu-id="a78f7-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="a78f7-110">Операторы</span><span class="sxs-lookup"><span data-stu-id="a78f7-110">Operators</span></span>  
  
|<span data-ttu-id="a78f7-111">Имя оператора</span><span class="sxs-lookup"><span data-stu-id="a78f7-111">Operator Name</span></span>|<span data-ttu-id="a78f7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a78f7-112">Description</span></span>|<span data-ttu-id="a78f7-113">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="a78f7-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="a78f7-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a78f7-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="a78f7-115">Skip</span><span class="sxs-lookup"><span data-stu-id="a78f7-115">Skip</span></span>|<span data-ttu-id="a78f7-116">Пропускает элементы до указанной позиции в последовательности.</span><span class="sxs-lookup"><span data-stu-id="a78f7-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="a78f7-117">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="a78f7-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a78f7-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="a78f7-118">SkipWhile</span></span>|<span data-ttu-id="a78f7-119">Пропускает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="a78f7-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="a78f7-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="a78f7-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a78f7-121">Take</span><span class="sxs-lookup"><span data-stu-id="a78f7-121">Take</span></span>|<span data-ttu-id="a78f7-122">Возвращает элементы на указанную позицию в последовательности.</span><span class="sxs-lookup"><span data-stu-id="a78f7-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="a78f7-123">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="a78f7-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a78f7-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="a78f7-124">TakeWhile</span></span>|<span data-ttu-id="a78f7-125">Принимает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="a78f7-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="a78f7-126">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="a78f7-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="a78f7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a78f7-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="a78f7-128">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="a78f7-128">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
