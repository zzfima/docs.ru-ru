---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: cbaea82108dd3debcca972ca15dea248227330ac
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251105"
---
# <a name="createref-entity-sql"></a><span data-ttu-id="bed6b-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bed6b-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="bed6b-103">Формирует ссылки на сущность в наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="bed6b-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bed6b-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="bed6b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bed6b-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="bed6b-106">Идентификатор набора сущностей, а не строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="bed6b-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="bed6b-107">Выражение типа строки таблицы, соответствующее свойствам ключа типа сущности.</span><span class="sxs-lookup"><span data-stu-id="bed6b-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bed6b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bed6b-108">Remarks</span></span>  
 <span data-ttu-id="bed6b-109">Выражение`row_typed_expression` должно быть структурно эквивалентно типу ключа для данной сущности.</span><span class="sxs-lookup"><span data-stu-id="bed6b-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="bed6b-110">Это значит, что оно должно иметь такое же число и типы полей, расположенные в том же порядке, как и ключи сущности.</span><span class="sxs-lookup"><span data-stu-id="bed6b-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="bed6b-111">В приведенном далее примере Orders и BadOrders являются наборами сущностей типа Order, и предполагается, что идентификатор Id является единственным свойством ключа для типа Order.</span><span class="sxs-lookup"><span data-stu-id="bed6b-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="bed6b-112">Этот пример иллюстрирует, как можно сформировать ссылку на сущность в наборе сущностей BadOrders.</span><span class="sxs-lookup"><span data-stu-id="bed6b-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="bed6b-113">Отметим, что ссылка может быть висячей.</span><span class="sxs-lookup"><span data-stu-id="bed6b-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="bed6b-114">Это значит, что в действительности ссылка может не указывать на конкретную сущность.</span><span class="sxs-lookup"><span data-stu-id="bed6b-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="bed6b-115">В этом случае оператор `DEREF` для этой ссылки возвратит значение null.</span><span class="sxs-lookup"><span data-stu-id="bed6b-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="bed6b-116">Пример</span><span class="sxs-lookup"><span data-stu-id="bed6b-116">Example</span></span>  
 <span data-ttu-id="bed6b-117">В следующем запросе Entity SQL оператор CREATEREF используется для формирования ссылок на сущность в наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="bed6b-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="bed6b-118">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="bed6b-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bed6b-119">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="bed6b-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bed6b-120">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="bed6b-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bed6b-121">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bed6b-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="bed6b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="bed6b-122">See also</span></span>

- [<span data-ttu-id="bed6b-123">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bed6b-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="bed6b-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="bed6b-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="bed6b-125">KEY</span><span class="sxs-lookup"><span data-stu-id="bed6b-125">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="bed6b-126">REF</span><span class="sxs-lookup"><span data-stu-id="bed6b-126">REF</span></span>](ref-entity-sql.md)
