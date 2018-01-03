---
title: GROUPPARTITION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8807564cb9acf8c50aed43ee11441ebdfbbcea78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="b50a2-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b50a2-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="b50a2-103">Возвращает коллекцию значений аргумента, проекция которых получена из текущей секции группы, с которой связано статистическое выражение.</span><span class="sxs-lookup"><span data-stu-id="b50a2-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="b50a2-104">Агрегат `GroupPartition` основан на группе и не имеет формы, основанной на коллекции.</span><span class="sxs-lookup"><span data-stu-id="b50a2-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b50a2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b50a2-105">Syntax</span></span>  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b50a2-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b50a2-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b50a2-107">Произвольное выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b50a2-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b50a2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b50a2-108">Remarks</span></span>  
 <span data-ttu-id="b50a2-109">Следующий запрос возвращает список продуктов и коллекцию количеств в строках заказа для каждого продукта:</span><span class="sxs-lookup"><span data-stu-id="b50a2-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="b50a2-110">Следующие два запроса семантически эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="b50a2-110">The following two queries are semantically equal:</span></span>  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="b50a2-111">Оператор `GROUPPARTITION` может использоваться вместе с определяемыми пользователем агрегатная функциями.</span><span class="sxs-lookup"><span data-stu-id="b50a2-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
 <span data-ttu-id="b50a2-112">Оператор`GROUPPARTITION` является специальным агрегатным оператором, который хранит ссылку на сгруппированный входной набор.</span><span class="sxs-lookup"><span data-stu-id="b50a2-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="b50a2-113">Эта ссылка может использоваться в любом месте запроса, где в области находится предложение GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="b50a2-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="b50a2-114">Например:</span><span class="sxs-lookup"><span data-stu-id="b50a2-114">For example,</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="b50a2-115">При использовании обычного предложения GROUP BY результаты группирования скрыты.</span><span class="sxs-lookup"><span data-stu-id="b50a2-115">With a regular GROUP BY, the results of the grouping are hidden.</span></span> <span data-ttu-id="b50a2-116">Эти результаты можно использовать только в агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="b50a2-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="b50a2-117">Чтобы можно было видеть результаты группирования, необходимо сопоставить результаты группирования и входной набор с использованием вложенного запроса.</span><span class="sxs-lookup"><span data-stu-id="b50a2-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="b50a2-118">Следующие два запроса эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="b50a2-118">The following two queries are equivalent:</span></span>  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="b50a2-119">Как показывает этот пример, применение статистического оператора GROUPPARTITION позволяет упростить получение ссылки на входной набор после группирования.</span><span class="sxs-lookup"><span data-stu-id="b50a2-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="b50a2-120">В операторе GROUPPARTITION на входе может указываться любое выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , если используется параметр `expression` .</span><span class="sxs-lookup"><span data-stu-id="b50a2-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="b50a2-121">Например, все следующие входные выражения для секции группы являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="b50a2-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="b50a2-122">Пример</span><span class="sxs-lookup"><span data-stu-id="b50a2-122">Example</span></span>  
 <span data-ttu-id="b50a2-123">В следующем примере показано, как использовать предложение GROUPPARTITION с предложением GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="b50a2-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="b50a2-124">Предложение GROUP BY группирует сущности `SalesOrderHeader` по их значениям `Contact`.</span><span class="sxs-lookup"><span data-stu-id="b50a2-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="b50a2-125">Затем предложение GROUPPARTITION находит проекцию свойства `TotalDue` для каждой группы, что приводит к получению коллекции десятичных чисел.</span><span class="sxs-lookup"><span data-stu-id="b50a2-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
