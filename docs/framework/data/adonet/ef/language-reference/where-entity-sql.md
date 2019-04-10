---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 02eeaeb8cfa335e5545b26d3d52b91c4e1614629
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230711"
---
# <a name="where-entity-sql"></a><span data-ttu-id="fd226-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fd226-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="fd226-103">Предложение WHERE применяется непосредственно после [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) предложение.</span><span class="sxs-lookup"><span data-stu-id="fd226-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd226-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd226-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fd226-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fd226-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="fd226-106">Тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="fd226-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd226-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd226-107">Remarks</span></span>  
 <span data-ttu-id="fd226-108">Предложение WHERE имеет такую же семантику, которая описана для [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd226-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fd226-109">Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.</span><span class="sxs-lookup"><span data-stu-id="fd226-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="fd226-110">Выражение `e` должно иметь тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="fd226-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="fd226-111">Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции.</span><span class="sxs-lookup"><span data-stu-id="fd226-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="fd226-112">Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="fd226-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd226-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fd226-113">See also</span></span>

- [<span data-ttu-id="fd226-114">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fd226-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="fd226-115">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="fd226-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
