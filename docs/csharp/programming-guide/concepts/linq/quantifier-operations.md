---
title: Операции, использующие квантификаторы (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635487"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="7c8f4-102">Операции, использующие квантификаторы (C#)</span><span class="sxs-lookup"><span data-stu-id="7c8f4-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="7c8f4-103">Квантификаторы возвращают значение <xref:System.Boolean>, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="7c8f4-104">На приведенном ниже рисунке показаны два различных квантификатора, примененные к двум разным исходным последовательностям.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="7c8f4-105">Первая операция проверяет, является ли один или несколько элементов буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="7c8f4-106">Вторая операция проверяет, являются ли все элементы буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Операции, использующие кванторы LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="7c8f4-108">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с использованием квантификаторов.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c8f4-109">Методы</span><span class="sxs-lookup"><span data-stu-id="7c8f4-109">Methods</span></span>  
  
|<span data-ttu-id="7c8f4-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="7c8f4-110">Method Name</span></span>|<span data-ttu-id="7c8f4-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="7c8f4-111">Description</span></span>|<span data-ttu-id="7c8f4-112">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="7c8f4-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="7c8f4-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7c8f4-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="7c8f4-114">Все</span><span class="sxs-lookup"><span data-stu-id="7c8f4-114">All</span></span>|<span data-ttu-id="7c8f4-115">Определяет, все ли элементы последовательности удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="7c8f4-116">Не применяется</span><span class="sxs-lookup"><span data-stu-id="7c8f4-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="7c8f4-117">Любой</span><span class="sxs-lookup"><span data-stu-id="7c8f4-117">Any</span></span>|<span data-ttu-id="7c8f4-118">Определяет, удовлетворяют ли условию какие-либо элементы последовательности.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="7c8f4-119">Не применяется</span><span class="sxs-lookup"><span data-stu-id="7c8f4-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="7c8f4-120">Содержит</span><span class="sxs-lookup"><span data-stu-id="7c8f4-120">Contains</span></span>|<span data-ttu-id="7c8f4-121">Определяет, содержит ли последовательность указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="7c8f4-122">Не применяется</span><span class="sxs-lookup"><span data-stu-id="7c8f4-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="7c8f4-123">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="7c8f4-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="7c8f4-124">Все</span><span class="sxs-lookup"><span data-stu-id="7c8f4-124">All</span></span>  
<span data-ttu-id="7c8f4-125">В следующем примере используется `All` для проверки того, что все строки имеют определенную длину.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="7c8f4-126">Любой</span><span class="sxs-lookup"><span data-stu-id="7c8f4-126">Any</span></span>  
<span data-ttu-id="7c8f4-127">В следующем примере используется `Any` для проверки того, что все строки начинаются o.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="7c8f4-128">Содержит</span><span class="sxs-lookup"><span data-stu-id="7c8f4-128">Contains</span></span>  
<span data-ttu-id="7c8f4-129">В следующем примере используется `Contains` для проверки того, что массив имеет указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="7c8f4-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="7c8f4-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7c8f4-130">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="7c8f4-131">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="7c8f4-131">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="7c8f4-132">Динамическое определение фильтров предикатов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="7c8f4-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="7c8f4-133">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7c8f4-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
