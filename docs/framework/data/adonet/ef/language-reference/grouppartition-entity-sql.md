---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 19df566c254a3f3202eb3554ab43ee0d7c944181
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833752"
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="c8751-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c8751-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="c8751-103">Возвращает коллекцию значений аргумента, проекция которых получена из текущей секции группы, с которой связано статистическое выражение.</span><span class="sxs-lookup"><span data-stu-id="c8751-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="c8751-104">Агрегат `GroupPartition` основан на группе и не имеет формы, основанной на коллекции.</span><span class="sxs-lookup"><span data-stu-id="c8751-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8751-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8751-105">Syntax</span></span>  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8751-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c8751-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c8751-107">Произвольное выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8751-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8751-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8751-108">Remarks</span></span>  
 <span data-ttu-id="c8751-109">Следующий запрос возвращает список продуктов и коллекцию количеств в строках заказа для каждого продукта:</span><span class="sxs-lookup"><span data-stu-id="c8751-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="c8751-110">Следующие два запроса семантически эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="c8751-110">The following two queries are semantically equal:</span></span>  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 <span data-ttu-id="c8751-111">Оператор `GROUPPARTITION` может использоваться вместе с определяемыми пользователем агрегатная функциями.</span><span class="sxs-lookup"><span data-stu-id="c8751-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
<span data-ttu-id="c8751-112">Оператор`GROUPPARTITION` является специальным агрегатным оператором, который хранит ссылку на сгруппированный входной набор.</span><span class="sxs-lookup"><span data-stu-id="c8751-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="c8751-113">Эта ссылка может использоваться в любом месте запроса, где в области находится предложение GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="c8751-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="c8751-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="c8751-114">For example:</span></span>
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="c8751-115">При обычной `GROUP BY` результаты группирования скрываются.</span><span class="sxs-lookup"><span data-stu-id="c8751-115">With a regular `GROUP BY`, the results of the grouping are hidden.</span></span> <span data-ttu-id="c8751-116">Эти результаты можно использовать только в агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="c8751-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="c8751-117">Чтобы можно было видеть результаты группирования, необходимо сопоставить результаты группирования и входной набор с использованием вложенного запроса.</span><span class="sxs-lookup"><span data-stu-id="c8751-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="c8751-118">Следующие два запроса эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="c8751-118">The following two queries are equivalent:</span></span>  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="c8751-119">Как показывает этот пример, применение статистического оператора GROUPPARTITION позволяет упростить получение ссылки на входной набор после группирования.</span><span class="sxs-lookup"><span data-stu-id="c8751-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="c8751-120">В операторе GROUPPARTITION на входе может указываться любое выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , если используется параметр `expression` .</span><span class="sxs-lookup"><span data-stu-id="c8751-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="c8751-121">Например, все следующие входные выражения для секции группы являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="c8751-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="c8751-122">Пример</span><span class="sxs-lookup"><span data-stu-id="c8751-122">Example</span></span>  
 <span data-ttu-id="c8751-123">В следующем примере показано, как использовать предложение GROUPPARTITION с предложением GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="c8751-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="c8751-124">Предложение GROUP BY группирует сущности `SalesOrderHeader` по их значениям `Contact`.</span><span class="sxs-lookup"><span data-stu-id="c8751-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="c8751-125">Затем предложение GROUPPARTITION находит проекцию свойства `TotalDue` для каждой группы, что приводит к получению коллекции десятичных чисел.</span><span class="sxs-lookup"><span data-stu-id="c8751-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
