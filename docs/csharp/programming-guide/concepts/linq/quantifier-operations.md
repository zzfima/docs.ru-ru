---
title: Операции, использующие квантификаторы (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 4a0f5b2c90d4b71a945dee02a32cbe897818c538
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591474"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="fb916-102">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="fb916-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="fb916-103">Квантификаторы возвращают значение <xref:System.Boolean>, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.</span><span class="sxs-lookup"><span data-stu-id="fb916-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="fb916-104">На приведенном ниже рисунке показаны два различных квантификатора, примененные к двум разным исходным последовательностям.</span><span class="sxs-lookup"><span data-stu-id="fb916-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="fb916-105">Первая операция проверяет, является ли один или несколько элементов буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="fb916-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="fb916-106">Вторая операция проверяет, являются ли все элементы буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="fb916-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Операции, использующие квантификаторы LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="fb916-108">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с использованием квантификаторов.</span><span class="sxs-lookup"><span data-stu-id="fb916-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb916-109">Методы</span><span class="sxs-lookup"><span data-stu-id="fb916-109">Methods</span></span>  
  
|<span data-ttu-id="fb916-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="fb916-110">Method Name</span></span>|<span data-ttu-id="fb916-111">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="fb916-111">Description</span></span>|<span data-ttu-id="fb916-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="fb916-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="fb916-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="fb916-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="fb916-114">Все</span><span class="sxs-lookup"><span data-stu-id="fb916-114">All</span></span>|<span data-ttu-id="fb916-115">Определяет, все ли элементы последовательности удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="fb916-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="fb916-116">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="fb916-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fb916-117">Любой</span><span class="sxs-lookup"><span data-stu-id="fb916-117">Any</span></span>|<span data-ttu-id="fb916-118">Определяет, удовлетворяют ли условию какие-либо элементы последовательности.</span><span class="sxs-lookup"><span data-stu-id="fb916-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="fb916-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="fb916-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="fb916-120">Содержит</span><span class="sxs-lookup"><span data-stu-id="fb916-120">Contains</span></span>|<span data-ttu-id="fb916-121">Определяет, содержит ли последовательность указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="fb916-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="fb916-122">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="fb916-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="fb916-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fb916-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="fb916-124">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="fb916-124">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="fb916-125">Практическое руководство. Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="fb916-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="fb916-126">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fb916-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
