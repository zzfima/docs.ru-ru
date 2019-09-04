---
title: Агрегатные функции (Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: c79071e73763b56c0dde906499f3eef1d296ce0c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251335"
---
# <a name="aggregate-functions-entity-sql"></a><span data-ttu-id="6d4a6-102">Агрегатные функции (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6d4a6-102">Aggregate Functions (Entity SQL)</span></span>
<span data-ttu-id="6d4a6-103">Статистическое выражение представляет собой языковую конструкцию, которая сжимает коллекцию в скаляр в составе операции группировки.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-103">An aggregate is a language construct that condenses a collection into a scalar as a part of a group operation.</span></span> <span data-ttu-id="6d4a6-104">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] статистические выражения встречаются в двух формах.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] aggregates come in two forms:</span></span>  
  
- [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6d4a6-105">функции сбора, которые могут использоваться в любом месте выражения.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-105">collection functions that may be used anywhere in an expression.</span></span> <span data-ttu-id="6d4a6-106">Сюда относится использование агрегатных функций в проекциях и предикатах, применяемых к коллекциям.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-106">This includes using aggregate functions in projections and predicates that act on collections.</span></span> <span data-ttu-id="6d4a6-107">Функции коллекций — это предпочтительный способ задания статистических функций в [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d4a6-107">Collection functions are the preferred mode of specifying aggregates in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
- <span data-ttu-id="6d4a6-108">Групповые статистические выражения в выражениях запроса с предложением GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-108">Group aggregates in query expressions that have a GROUP BY clause.</span></span> <span data-ttu-id="6d4a6-109">Как и в Transact-SQL, групповые статистические функции принимают DISTINCT и ALL как модификаторы для входных статистических данных.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-109">As in Transact-SQL, group aggregates accept DISTINCT and ALL as modifiers to the aggregate input.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6d4a6-110">сначала пытается интерпретировать выражение как функцию сбора, и если выражение находится в контексте выражения SELECT, оно интерпретирует его как Статистическое выражение группы.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-110">first tries to interpret an expression as a collection function and if the expression is in the context of a SELECT expression it interprets it as a group aggregate.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6d4a6-111">Определяет специальный статистический оператор с именем [GROUPPARTITION](grouppartition-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6d4a6-111">defines a special aggregate operator called [GROUPPARTITION](grouppartition-entity-sql.md).</span></span> <span data-ttu-id="6d4a6-112">Этот оператор позволяет получить ссылку на сгруппированный входной набор.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-112">This operator enables you to get a reference to the grouped input set.</span></span> <span data-ttu-id="6d4a6-113">Это позволяет выполнять расширенные запросы группирования, в которых результаты предложения GROUP BY могут использоваться в местах, отличных от функций коллекции или группового статистического выражения.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-113">This allows more advanced grouping queries, where the results of the GROUP BY clause can be used in places other than group aggregate or collection functions.</span></span>  
  
## <a name="collection-functions"></a><span data-ttu-id="6d4a6-114">Функции коллекции</span><span class="sxs-lookup"><span data-stu-id="6d4a6-114">Collection Functions</span></span>  
 <span data-ttu-id="6d4a6-115">Функции коллекции работают с коллекциями и возвращают скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-115">Collection functions operate on collections and return a scalar value.</span></span> <span data-ttu-id="6d4a6-116">Например, если `orders` - это коллекция всех объектов `orders`, то можно рассчитать самую раннюю дату отгрузки с помощью следующего выражения:</span><span class="sxs-lookup"><span data-stu-id="6d4a6-116">For example, if `orders` is a collection of all `orders`, you can calculate the earliest ship date with the following expression:</span></span>  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a><span data-ttu-id="6d4a6-117">Групповые статистические выражения</span><span class="sxs-lookup"><span data-stu-id="6d4a6-117">Group Aggregates</span></span>  
 <span data-ttu-id="6d4a6-118">Групповые статистические выражения вычисляются по результату группирования, определенного предложением GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-118">Group aggregates are calculated over a group result as defined by the GROUP BY clause.</span></span> <span data-ttu-id="6d4a6-119">Предложение GROUP BY разделяет данные на группы.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-119">The GROUP BY clause partitions data  into groups.</span></span> <span data-ttu-id="6d4a6-120">К каждой группе в результате применяется агрегатная функция, и вычисляется отдельное статистическое выражение с использованием элементов каждой группы в качестве входных значений.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-120">For each group in the result, the aggregate function is applied and a separate aggregate is calculated by using the elements in each group as inputs to the aggregate calculation.</span></span> <span data-ttu-id="6d4a6-121">Если в выражении SELECT используется предложение GROUP BY, то в проекции, а также предложении HAVING или ORDER BY, могут присутствовать только имена выражений группирования, статистические функции или константные выражения.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-121">When a GROUP BY clause is used in a SELECT expression, only grouping expression names, aggregates, or constant expressions may be present in the projection, HAVING, or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="6d4a6-122">В следующем примере вычисляется средняя величина заказа для каждого продукта.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-122">The following example calculates the average quantity ordered for each product.</span></span>  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 <span data-ttu-id="6d4a6-123">В выражении SELECT может присутствовать групповое статистическое выражение без явно заданного предложения GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-123">It is possible to have a group aggregate without an explicit GROUP BY clause in the SELECT expression.</span></span> <span data-ttu-id="6d4a6-124">Все элементы при этом рассматриваются как одна группа, что эквивалентно определению группирования на основе константы.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-124">All elements will be treated as a single group, equivalent to the case of specifying a grouping based on a constant.</span></span>  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 <span data-ttu-id="6d4a6-125">Выражения, используемые в предложении GROUP BY, вычисляются в той же области разрешения имен, которая является видимой для выражения предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="6d4a6-125">Expressions used in the GROUP BY clause are evaluated by using the same name-resolution scope that would be visible to the WHERE clause expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4a6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6d4a6-126">See also</span></span>

- [<span data-ttu-id="6d4a6-127">Функции</span><span class="sxs-lookup"><span data-stu-id="6d4a6-127">Functions</span></span>](functions-entity-sql.md)
