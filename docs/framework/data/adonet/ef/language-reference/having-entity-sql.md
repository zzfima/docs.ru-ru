---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 76a63140668fb1f41cf9e6f901d9a43240a1d098
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936081"
---
# <a name="having-entity-sql"></a><span data-ttu-id="4a470-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4a470-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="4a470-103">Задает условие поиска для группы или статистического выражения.</span><span class="sxs-lookup"><span data-stu-id="4a470-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a470-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a470-104">Syntax</span></span>  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4a470-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4a470-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="4a470-106">Определяет условие поиска, которому должна соответствовать группа или статистическое выражение.</span><span class="sxs-lookup"><span data-stu-id="4a470-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="4a470-107">Если предложение HAVING используется в сочетании с GROUP BY ALL, то оно переопределяет ALL.</span><span class="sxs-lookup"><span data-stu-id="4a470-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a470-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a470-108">Remarks</span></span>  
 <span data-ttu-id="4a470-109">Предложение HAVING позволяет указать дополнительное условие фильтрации для результатов группирования.</span><span class="sxs-lookup"><span data-stu-id="4a470-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="4a470-110">Если в выражении запроса не указано предложение GROUP BY, то предполагается неявным образом созданная группа, состоящая из одного набора.</span><span class="sxs-lookup"><span data-stu-id="4a470-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a470-111">HAVING можно использовать только с инструкцией [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="4a470-111">HAVING can be used only with the [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statement.</span></span> <span data-ttu-id="4a470-112">Если [Group By](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) не используется, то ведет себя как предложение WHERE.</span><span class="sxs-lookup"><span data-stu-id="4a470-112">When [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
 <span data-ttu-id="4a470-113">Предложение HAVING работает точно так же, как и предложение WHERE, за исключением того, что применяется после операции GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="4a470-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="4a470-114">Это означает, что предложение HAVING может ссылаться только на псевдонимы и статистические выражения группирования, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4a470-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example.</span></span>  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="4a470-115">Предыдущий пример производится ограничение до тех групп, которые содержат более одного товара.</span><span class="sxs-lookup"><span data-stu-id="4a470-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a470-116">Пример</span><span class="sxs-lookup"><span data-stu-id="4a470-116">Example</span></span>  
 <span data-ttu-id="4a470-117">В следующем запросе Entity SQL операторы HAVING и GROUP BY задают условие поиска для группы или статистического выражения.</span><span class="sxs-lookup"><span data-stu-id="4a470-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="4a470-118">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="4a470-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4a470-119">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4a470-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4a470-120">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего тип PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="4a470-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="4a470-121">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="4a470-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a><span data-ttu-id="4a470-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4a470-122">See also</span></span>

- [<span data-ttu-id="4a470-123">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4a470-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="4a470-124">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="4a470-124">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
