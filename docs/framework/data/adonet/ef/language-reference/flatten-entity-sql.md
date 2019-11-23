---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 84b846e3db86c664bc42363f3d983a1001f5c318
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833806"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="bd67a-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bd67a-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="bd67a-103">Преобразовывает коллекцию коллекций в плоскую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bd67a-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="bd67a-104">Новая коллекция содержит все те же элементы, что и старая коллекция, но без структуры вложения.</span><span class="sxs-lookup"><span data-stu-id="bd67a-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd67a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd67a-105">Syntax</span></span>  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="bd67a-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bd67a-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="bd67a-107">Любое допустимое выражение, которое возвращает коллекцию коллекций значений, предназначенных для сведения в плоскую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bd67a-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd67a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd67a-108">Remarks</span></span>  
 <span data-ttu-id="bd67a-109">Оператор`FLATTEN` - это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd67a-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="bd67a-110">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="bd67a-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="bd67a-111">Дополнительные сведения см. в разделе, [за исключением](except-entity-sql.md) сведений о приоритетах для операторов набора [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd67a-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd67a-112">Пример</span><span class="sxs-lookup"><span data-stu-id="bd67a-112">Example</span></span>  
 <span data-ttu-id="bd67a-113">В следующем запросе Entity SQL используется оператор `FLATTEN` для преобразования коллекции коллекций в плоскую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bd67a-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="bd67a-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="bd67a-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bd67a-115">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bd67a-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bd67a-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bd67a-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="bd67a-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd67a-117">See also</span></span>

- [<span data-ttu-id="bd67a-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bd67a-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
