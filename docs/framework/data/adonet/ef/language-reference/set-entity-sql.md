---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 4e2a387cf400a881dfd91c61b36ee3ce0f5a4431
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309437"
---
# <a name="set-entity-sql"></a><span data-ttu-id="abccd-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="abccd-102">SET (Entity SQL)</span></span>
<span data-ttu-id="abccd-103">Выражение SET используется для преобразования коллекции объектов в набор путем получения новой коллекции, из которой удалены все повторяющиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="abccd-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abccd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abccd-104">Syntax</span></span>  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="abccd-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="abccd-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="abccd-106">Любое допустимое выражение запроса, возвращающее коллекцию.</span><span class="sxs-lookup"><span data-stu-id="abccd-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abccd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="abccd-107">Remarks</span></span>  
 <span data-ttu-id="abccd-108">Выражение набора `SET(c)` логически эквивалентно следующей инструкции SELECT:</span><span class="sxs-lookup"><span data-stu-id="abccd-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` <span data-ttu-id="abccd-109">является одним из [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторы работы с наборами.</span><span class="sxs-lookup"><span data-stu-id="abccd-109">is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="abccd-110">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="abccd-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="abccd-111">См. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторы работы с наборами.</span><span class="sxs-lookup"><span data-stu-id="abccd-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abccd-112">Пример</span><span class="sxs-lookup"><span data-stu-id="abccd-112">Example</span></span>  
 <span data-ttu-id="abccd-113">В следующем запросе Entity SQL используется выражение SET для преобразования коллекции объектов в набор.</span><span class="sxs-lookup"><span data-stu-id="abccd-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="abccd-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="abccd-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="abccd-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="abccd-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="abccd-116">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="abccd-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="abccd-117">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="abccd-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a><span data-ttu-id="abccd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="abccd-118">See also</span></span>

- [<span data-ttu-id="abccd-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="abccd-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
