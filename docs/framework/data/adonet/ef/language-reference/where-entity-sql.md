---
title: WHERE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 11687b1218c61acde7a68bb8fc112e287e5e1c38
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="where-entity-sql"></a><span data-ttu-id="734a0-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="734a0-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="734a0-103">Предложение WHERE применяется непосредственно после [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) предложения.</span><span class="sxs-lookup"><span data-stu-id="734a0-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="734a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="734a0-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="734a0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="734a0-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="734a0-106">Тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="734a0-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="734a0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="734a0-107">Remarks</span></span>  
 <span data-ttu-id="734a0-108">Предложение WHERE имеет такую же семантику, которая описана для [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="734a0-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="734a0-109">Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.</span><span class="sxs-lookup"><span data-stu-id="734a0-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="734a0-110">Выражение `e` должно иметь тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="734a0-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="734a0-111">Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции.</span><span class="sxs-lookup"><span data-stu-id="734a0-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="734a0-112">Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="734a0-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734a0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="734a0-113">See Also</span></span>  
 [<span data-ttu-id="734a0-114">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="734a0-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="734a0-115">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="734a0-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
