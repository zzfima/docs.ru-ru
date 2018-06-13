---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: c35cac018392aa9688866e280ff64fdf6a1453f5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760561"
---
# <a name="key-entity-sql"></a><span data-ttu-id="fa8ce-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fa8ce-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="fa8ce-103">Извлекает ключ ссылки или выражение сущности.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa8ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa8ce-104">Syntax</span></span>  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa8ce-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa8ce-105">Remarks</span></span>  
 <span data-ttu-id="fa8ce-106">Ключ сущности содержит значения ключа в правильном порядке указанной сущности или ссылки на сущность.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="fa8ce-107">На одном и том же типе сущности могут быть основаны разные наборы сущностей, поэтому в каждом наборе сущностей может появиться одинаковый ключ.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="fa8ce-108">Для получения уникальной ссылки используйте `REF`.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="fa8ce-109">Возвращаемый тип оператора KEY – это тип строки, включающий одно поле для каждого ключа сущности в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="fa8ce-110">В следующем примере оператору ключа передается ссылка на сущность BadOrder, и он возвращает ключевую часть этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="fa8ce-111">В данном случае – тип записи точно с одним полем, соответствующим свойству `Id` .</span><span class="sxs-lookup"><span data-stu-id="fa8ce-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="fa8ce-112">Пример</span><span class="sxs-lookup"><span data-stu-id="fa8ce-112">Example</span></span>  
 <span data-ttu-id="fa8ce-113">В следующем запросе Entity SQL используется оператор KEY с целью извлечения ключевой части выражения со ссылкой на тип.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="fa8ce-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fa8ce-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fa8ce-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="fa8ce-116">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="fa8ce-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="fa8ce-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fa8ce-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a><span data-ttu-id="fa8ce-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fa8ce-118">See Also</span></span>  
 [<span data-ttu-id="fa8ce-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fa8ce-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="fa8ce-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="fa8ce-120">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="fa8ce-121">REF</span><span class="sxs-lookup"><span data-stu-id="fa8ce-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="fa8ce-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="fa8ce-122">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
