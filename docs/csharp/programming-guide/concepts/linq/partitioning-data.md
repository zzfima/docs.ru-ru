---
title: Секционирование данных (C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: d9330e9973b2f25903e1f81a7296362e2a7c756b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591593"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="ce4c6-102">Секционирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="ce4c6-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="ce4c6-103">Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="ce4c6-104">На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="ce4c6-105">Первая операция возвращает первые три элемента в последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="ce4c6-106">Вторая операция пропускает первые три элемента и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="ce4c6-107">Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Рисунок иллюстрирующий три операции секционирования LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="ce4c6-109">Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="ce4c6-110">Операторы</span><span class="sxs-lookup"><span data-stu-id="ce4c6-110">Operators</span></span>  
  
|<span data-ttu-id="ce4c6-111">Имя оператора</span><span class="sxs-lookup"><span data-stu-id="ce4c6-111">Operator Name</span></span>|<span data-ttu-id="ce4c6-112">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ce4c6-112">Description</span></span>|<span data-ttu-id="ce4c6-113">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="ce4c6-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="ce4c6-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ce4c6-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ce4c6-115">Skip</span><span class="sxs-lookup"><span data-stu-id="ce4c6-115">Skip</span></span>|<span data-ttu-id="ce4c6-116">Пропускает элементы до указанной позиции в последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="ce4c6-117">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ce4c6-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="ce4c6-118">SkipWhile</span></span>|<span data-ttu-id="ce4c6-119">Пропускает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="ce4c6-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ce4c6-121">Take</span><span class="sxs-lookup"><span data-stu-id="ce4c6-121">Take</span></span>|<span data-ttu-id="ce4c6-122">Возвращает элементы на указанную позицию в последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="ce4c6-123">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ce4c6-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="ce4c6-124">TakeWhile</span></span>|<span data-ttu-id="ce4c6-125">Принимает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="ce4c6-126">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="ce4c6-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="ce4c6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ce4c6-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ce4c6-128">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="ce4c6-128">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
