---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 939d4c0ec2c30bc71b22fb65ab36644e063f97de
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489848"
---
# <a name="where-entity-sql"></a><span data-ttu-id="088d3-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="088d3-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="088d3-103">Предложение WHERE применяется непосредственно после [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) предложение.</span><span class="sxs-lookup"><span data-stu-id="088d3-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="088d3-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="088d3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="088d3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="088d3-106">Тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="088d3-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="088d3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="088d3-107">Remarks</span></span>  
 <span data-ttu-id="088d3-108">Предложение WHERE имеет ту же семантику, как описано для Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="088d3-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="088d3-109">Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.</span><span class="sxs-lookup"><span data-stu-id="088d3-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="088d3-110">Выражение `e` должно иметь тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="088d3-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="088d3-111">Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции.</span><span class="sxs-lookup"><span data-stu-id="088d3-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="088d3-112">Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="088d3-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088d3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="088d3-113">See also</span></span>

- [<span data-ttu-id="088d3-114">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="088d3-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="088d3-115">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="088d3-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
