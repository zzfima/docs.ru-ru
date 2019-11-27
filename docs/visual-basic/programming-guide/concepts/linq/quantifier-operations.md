---
title: Операции, использующие квантификаторы
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: f5b98ec09405ca4b8c715dc7da342e66a5d434d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346586"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="a8edc-102">Операции квантификаторов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8edc-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="a8edc-103">Квантификаторы возвращают значение <xref:System.Boolean>, которое указывает, удовлетворяют ли условию некоторые или все элементы в последовательности.</span><span class="sxs-lookup"><span data-stu-id="a8edc-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="a8edc-104">На приведенном ниже рисунке показаны два различных квантификатора, примененные к двум разным исходным последовательностям.</span><span class="sxs-lookup"><span data-stu-id="a8edc-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="a8edc-105">Первая операция проверяет, является ли один или несколько элементов буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="a8edc-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="a8edc-106">Вторая операция проверяет, являются ли все элементы буквой "А"; результатом является `true`.</span><span class="sxs-lookup"><span data-stu-id="a8edc-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Операции, использующие квантификаторы LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="a8edc-108">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с использованием квантификаторов.</span><span class="sxs-lookup"><span data-stu-id="a8edc-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8edc-109">Методы</span><span class="sxs-lookup"><span data-stu-id="a8edc-109">Methods</span></span>  
  
|<span data-ttu-id="a8edc-110">Имя метода</span><span class="sxs-lookup"><span data-stu-id="a8edc-110">Method Name</span></span>|<span data-ttu-id="a8edc-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a8edc-111">Description</span></span>|<span data-ttu-id="a8edc-112">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8edc-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="a8edc-113">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a8edc-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="a8edc-114">Все</span><span class="sxs-lookup"><span data-stu-id="a8edc-114">All</span></span>|<span data-ttu-id="a8edc-115">Определяет, все ли элементы последовательности удовлетворяют условию.</span><span class="sxs-lookup"><span data-stu-id="a8edc-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8edc-116">Любой</span><span class="sxs-lookup"><span data-stu-id="a8edc-116">Any</span></span>|<span data-ttu-id="a8edc-117">Определяет, удовлетворяют ли условию какие-либо элементы последовательности.</span><span class="sxs-lookup"><span data-stu-id="a8edc-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a8edc-118">Содержит</span><span class="sxs-lookup"><span data-stu-id="a8edc-118">Contains</span></span>|<span data-ttu-id="a8edc-119">Определяет, содержит ли последовательность указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="a8edc-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="a8edc-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="a8edc-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="a8edc-121">Примеры синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="a8edc-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="a8edc-122">В этих примерах используется предложение `Aggregate` в Visual Basic в качестве части условия фильтрации в запросе LINQ.</span><span class="sxs-lookup"><span data-stu-id="a8edc-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="a8edc-123">В следующем примере используется предложение `Aggregate` и метод расширения <xref:System.Linq.Enumerable.All%2A> для возврата из коллекции тех людей, чьи pets старше указанного возраста.</span><span class="sxs-lookup"><span data-stu-id="a8edc-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="a8edc-124">В следующем примере используется предложение `Aggregate` и метод расширения <xref:System.Linq.Enumerable.Any%2A> для возврата из коллекции пользователей, у которых есть по крайней мере один Pet, который старше указанного возраста.</span><span class="sxs-lookup"><span data-stu-id="a8edc-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a8edc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a8edc-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="a8edc-126">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8edc-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="a8edc-127">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="a8edc-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="a8edc-128">Пошаговое руководство. запрос предложений, содержащих указанный набор слов (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8edc-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
