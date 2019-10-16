---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: b551d15d7de2cf07afc7455b7fd0a0faf6436ccf
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319181"
---
# <a name="where-entity-sql"></a><span data-ttu-id="62c75-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="62c75-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="62c75-103">Предложение WHERE применяется непосредственно после предложения [from](from-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="62c75-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62c75-104">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="62c75-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="62c75-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="62c75-106">Тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="62c75-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c75-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="62c75-107">Remarks</span></span>  
 <span data-ttu-id="62c75-108">В предложении WHERE есть та же семантика, которая описана для Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="62c75-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="62c75-109">Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.</span><span class="sxs-lookup"><span data-stu-id="62c75-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="62c75-110">Выражение `e` должно иметь тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="62c75-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="62c75-111">Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции.</span><span class="sxs-lookup"><span data-stu-id="62c75-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="62c75-112">Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="62c75-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c75-113">См. также</span><span class="sxs-lookup"><span data-stu-id="62c75-113">See also</span></span>

- [<span data-ttu-id="62c75-114">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="62c75-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="62c75-115">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="62c75-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
