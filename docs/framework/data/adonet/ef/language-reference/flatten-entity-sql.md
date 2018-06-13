---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 75463ed622ac969eb2690c4118861823479a2caa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760574"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="cc609-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cc609-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="cc609-103">Преобразовывает коллекцию коллекций в плоскую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="cc609-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="cc609-104">Новая коллекция содержит все те же элементы, что и старая коллекция, но без структуры вложения.</span><span class="sxs-lookup"><span data-stu-id="cc609-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc609-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc609-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc609-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cc609-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="cc609-107">Любое допустимое выражение, которое возвращает коллекцию коллекций значений, предназначенных для сведения в плоскую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="cc609-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc609-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc609-108">Remarks</span></span>  
 <span data-ttu-id="cc609-109">Оператор`FLATTEN` - это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc609-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="cc609-110">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="cc609-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="cc609-111">В разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов работы с наборами.</span><span class="sxs-lookup"><span data-stu-id="cc609-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc609-112">Пример</span><span class="sxs-lookup"><span data-stu-id="cc609-112">Example</span></span>  
 <span data-ttu-id="cc609-113">В следующем запросе Entity SQL используется оператор `FLATTEN` для преобразования коллекции коллекций в плоскую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="cc609-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="cc609-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cc609-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cc609-115">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cc609-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cc609-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="cc609-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="cc609-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cc609-117">See Also</span></span>  
 [<span data-ttu-id="cc609-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cc609-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
