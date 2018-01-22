---
title: "Разбивка на страницы (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dfbd282eed19fdfa81a1dda5d06d41a80386feaa
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="paging-entity-sql"></a><span data-ttu-id="6deca-102">Разбивка на страницы (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6deca-102">Paging (Entity SQL)</span></span>
<span data-ttu-id="6deca-103">Физическое разбиение на страницы может выполняться с помощью [пропустить](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [ограничение](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) вложенные предложения в [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) предложения.</span><span class="sxs-lookup"><span data-stu-id="6deca-103">Physical paging can be performed by using the [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses in the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="6deca-104">Для детерминированного физического разбиения на страницы необходимо использовать предложения SKIP и LIMIT.</span><span class="sxs-lookup"><span data-stu-id="6deca-104">To perform physical paging deterministically, you should use SKIP and LIMIT.</span></span> <span data-ttu-id="6deca-105">Если требуется ограничить количество строк в результате недетерминированным методом, следует использовать [ВЕРХНЕЙ](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6deca-105">If you only want to restrict the number of rows in the result in a non-determinsitic way, you should use [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).</span></span> <span data-ttu-id="6deca-106">Предложения TOP и SKIP/LIMIT являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="6deca-106">TOP and SKIP/LIMIT are mutually exclusive.</span></span>  
  
## <a name="top-overview"></a><span data-ttu-id="6deca-107">Общие сведения о предложении TOP</span><span class="sxs-lookup"><span data-stu-id="6deca-107">TOP Overview</span></span>  
 <span data-ttu-id="6deca-108">Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL/DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="6deca-108">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="6deca-109">Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк.</span><span class="sxs-lookup"><span data-stu-id="6deca-109">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span> <span data-ttu-id="6deca-110">Дополнительные сведения см. в разделе [ВЕРХНЕЙ](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6deca-110">For more information, see [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).</span></span>  
  
## <a name="skip-and-limit-overview"></a><span data-ttu-id="6deca-111">Общие сведения о предложениях SKIP и LIMIT</span><span class="sxs-lookup"><span data-stu-id="6deca-111">SKIP And LIMIT Overview</span></span>  
 <span data-ttu-id="6deca-112">Предложения SKIP и LIMIT являются частью предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="6deca-112">SKIP and LIMIT are part of the ORDER BY clause.</span></span> <span data-ttu-id="6deca-113">Если в предложении ORDER BY имеется вложенное предложение SKIP, результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP.</span><span class="sxs-lookup"><span data-stu-id="6deca-113">If a SKIP expression sub-clause is present in a ORDER BY clause, the results will be sorted according to the sort specification and the result set will include row(s) starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="6deca-114">Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.</span><span class="sxs-lookup"><span data-stu-id="6deca-114">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span> <span data-ttu-id="6deca-115">Если в предложении ORDER BY имеется подчиненное выражение LIMIT, результаты запроса будут отсортированы в соответствии со спецификацией сортировки, а количество строк в наборе будет ограничено выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="6deca-115">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="6deca-116">Например, LIMIT 5 ограничит результирующий набор пятью экземплярами строк.</span><span class="sxs-lookup"><span data-stu-id="6deca-116">For instance, LIMIT 5 will restrict the result set to five instances or rows.</span></span> <span data-ttu-id="6deca-117">Предложения SKIP и LIMIT необязательно использовать вместе: в предложение ORDER BY можно включить только SKIP или только LIMIT.</span><span class="sxs-lookup"><span data-stu-id="6deca-117">SKIP and LIMIT do not have to be used together; you can use just SKIP or just LIMIT with ORDER BY clause.</span></span> <span data-ttu-id="6deca-118">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="6deca-118">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="6deca-119">SKIP</span><span class="sxs-lookup"><span data-stu-id="6deca-119">SKIP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [<span data-ttu-id="6deca-120">LIMIT</span><span class="sxs-lookup"><span data-stu-id="6deca-120">LIMIT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [<span data-ttu-id="6deca-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="6deca-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="6deca-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6deca-122">See Also</span></span>  
 [<span data-ttu-id="6deca-123">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6deca-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="6deca-124">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6deca-124">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="6deca-125">Как: постранично просмотреть результаты запроса</span><span class="sxs-lookup"><span data-stu-id="6deca-125">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
