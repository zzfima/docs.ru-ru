---
title: Операции, использующие квантификаторы (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5899af79799d5b8404e60027d7ba1b005c4b1b79
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423366"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="e50b7-102">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="e50b7-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="e50b7-103">Квантификаторы возвращают значение <xref:System.Boolean>, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.</span><span class="sxs-lookup"><span data-stu-id="e50b7-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="e50b7-104">На приведенном ниже рисунке показаны два различных квантификатора, примененные к двум разным исходным последовательностям.</span><span class="sxs-lookup"><span data-stu-id="e50b7-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="e50b7-105">Первая операция проверяет, является ли один или несколько элементов буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="e50b7-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="e50b7-106">Вторая операция проверяет, являются ли все элементы буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="e50b7-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Операции, использующие квантификаторы LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="e50b7-108">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с использованием квантификаторов.</span><span class="sxs-lookup"><span data-stu-id="e50b7-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e50b7-109">Методы</span><span class="sxs-lookup"><span data-stu-id="e50b7-109">Methods</span></span>  
  
|<span data-ttu-id="e50b7-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="e50b7-110">Method Name</span></span>|<span data-ttu-id="e50b7-111">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="e50b7-111">Description</span></span>|<span data-ttu-id="e50b7-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="e50b7-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="e50b7-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e50b7-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="e50b7-114">Все</span><span class="sxs-lookup"><span data-stu-id="e50b7-114">All</span></span>|<span data-ttu-id="e50b7-115">Определяет, все ли элементы последовательности удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="e50b7-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="e50b7-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="e50b7-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e50b7-117">Любой</span><span class="sxs-lookup"><span data-stu-id="e50b7-117">Any</span></span>|<span data-ttu-id="e50b7-118">Определяет, удовлетворяют ли условию какие-либо элементы последовательности.</span><span class="sxs-lookup"><span data-stu-id="e50b7-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="e50b7-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="e50b7-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e50b7-120">Содержит</span><span class="sxs-lookup"><span data-stu-id="e50b7-120">Contains</span></span>|<span data-ttu-id="e50b7-121">Определяет, содержит ли последовательность указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="e50b7-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="e50b7-122">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="e50b7-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="e50b7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e50b7-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="e50b7-124">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="e50b7-124">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="e50b7-125">Практическое руководство. Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e50b7-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="e50b7-126">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="e50b7-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
