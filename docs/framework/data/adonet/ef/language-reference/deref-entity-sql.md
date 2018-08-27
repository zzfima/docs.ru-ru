---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: abe47f8c72abe13bd5c27fe10a412ff94ab861cf
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930016"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="59b90-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="59b90-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="59b90-103">Разыменовывает значение ссылки и выдает результат разыменования.</span><span class="sxs-lookup"><span data-stu-id="59b90-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59b90-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="59b90-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="59b90-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="59b90-106">Любое допустимое выражение запроса, возвращающее коллекцию.</span><span class="sxs-lookup"><span data-stu-id="59b90-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59b90-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="59b90-107">Return Value</span></span>  
 <span data-ttu-id="59b90-108">Значение сущности, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="59b90-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59b90-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="59b90-109">Remarks</span></span>  
 <span data-ttu-id="59b90-110">Оператор DEREF разыменовывает значение ссылки и выдает результат разыменования.</span><span class="sxs-lookup"><span data-stu-id="59b90-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="59b90-111">Например если `r` является ссылкой типа ref\<T >, `Deref(r)` является выражением типа `T` возвращает сущность, на который указывает `r`.</span><span class="sxs-lookup"><span data-stu-id="59b90-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="59b90-112">Если ссылка имеет значение null или висячее значение (т. е. цель ссылки не существует), то результатом оператора DEREF будет значение null.</span><span class="sxs-lookup"><span data-stu-id="59b90-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b90-113">Пример</span><span class="sxs-lookup"><span data-stu-id="59b90-113">Example</span></span>  
 <span data-ttu-id="59b90-114">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор DEREF используется для разыменования значения ссылки и возврата результата разыменования.</span><span class="sxs-lookup"><span data-stu-id="59b90-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="59b90-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="59b90-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="59b90-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="59b90-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="59b90-117">Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="59b90-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="59b90-118">Передайте методу ExecutePrimitiveTypeQuery следующий запрос в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="59b90-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="59b90-119">См. также</span><span class="sxs-lookup"><span data-stu-id="59b90-119">See Also</span></span>  
 [<span data-ttu-id="59b90-120">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="59b90-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="59b90-121">REF</span><span class="sxs-lookup"><span data-stu-id="59b90-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="59b90-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="59b90-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="59b90-123">KEY</span><span class="sxs-lookup"><span data-stu-id="59b90-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="59b90-124">Допускающие значения NULL структурированные типы</span><span class="sxs-lookup"><span data-stu-id="59b90-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
