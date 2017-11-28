---
title: "Секционирование данных (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 32b95887e05767513dd818743dd1726149503b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="partitioning-data-c"></a><span data-ttu-id="b7059-102">Секционирование данных (C#)</span><span class="sxs-lookup"><span data-stu-id="b7059-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="b7059-103">Секционированием в LINQ называют операцию разделения входной последовательности на два раздела без изменения порядка элементов, а затем возвращения одного из разделов.</span><span class="sxs-lookup"><span data-stu-id="b7059-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="b7059-104">На следующем рисунке показаны результаты трех различных операций секционирования в последовательности символов.</span><span class="sxs-lookup"><span data-stu-id="b7059-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="b7059-105">Первая операция возвращает первые три элемента в последовательности.</span><span class="sxs-lookup"><span data-stu-id="b7059-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="b7059-106">Вторая операция пропускает первые три элемента и возвращает остальные элементы.</span><span class="sxs-lookup"><span data-stu-id="b7059-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="b7059-107">Третья операция пропускает первые два элемента в последовательности и возвращает три следующих элемента.</span><span class="sxs-lookup"><span data-stu-id="b7059-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="b7059-108">![Операции секционирования LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="b7059-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="b7059-109">Далее перечислены методы стандартных операторов запроса, которые секционируют последовательности.</span><span class="sxs-lookup"><span data-stu-id="b7059-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="b7059-110">Операторы</span><span class="sxs-lookup"><span data-stu-id="b7059-110">Operators</span></span>  
  
|<span data-ttu-id="b7059-111">Имя оператора</span><span class="sxs-lookup"><span data-stu-id="b7059-111">Operator Name</span></span>|<span data-ttu-id="b7059-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b7059-112">Description</span></span>|<span data-ttu-id="b7059-113">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="b7059-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="b7059-114">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b7059-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b7059-115">Skip</span><span class="sxs-lookup"><span data-stu-id="b7059-115">Skip</span></span>|<span data-ttu-id="b7059-116">Пропускает элементы до указанной позиции в последовательности.</span><span class="sxs-lookup"><span data-stu-id="b7059-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="b7059-117">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b7059-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7059-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="b7059-118">SkipWhile</span></span>|<span data-ttu-id="b7059-119">Пропускает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="b7059-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="b7059-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b7059-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7059-121">Take</span><span class="sxs-lookup"><span data-stu-id="b7059-121">Take</span></span>|<span data-ttu-id="b7059-122">Возвращает элементы на указанную позицию в последовательности.</span><span class="sxs-lookup"><span data-stu-id="b7059-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="b7059-123">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b7059-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7059-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="b7059-124">TakeWhile</span></span>|<span data-ttu-id="b7059-125">Принимает элементы, пока элемент не удовлетворит условию функции предиката.</span><span class="sxs-lookup"><span data-stu-id="b7059-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="b7059-126">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b7059-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="b7059-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b7059-127">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="b7059-128">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="b7059-128">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
