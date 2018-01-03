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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2ad170500770bc370eb67a04ab29d0c9f9dcaabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="where-entity-sql"></a><span data-ttu-id="04476-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="04476-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="04476-103">Предложение WHERE применяется непосредственно после [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) предложения.</span><span class="sxs-lookup"><span data-stu-id="04476-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04476-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04476-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="04476-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="04476-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="04476-106">Тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="04476-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04476-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="04476-107">Remarks</span></span>  
 <span data-ttu-id="04476-108">Предложение WHERE имеет такую же семантику, которая описана для [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04476-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="04476-109">Она ограничивает набор объектов, полученный выражением запроса, выбирая из исходной коллекции только те элементы, которые соответствуют условию.</span><span class="sxs-lookup"><span data-stu-id="04476-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="04476-110">Выражение `e` должно иметь тип Boolean.</span><span class="sxs-lookup"><span data-stu-id="04476-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="04476-111">Предложение WHERE применяется непосредственно после предложения FROM, до выполнения любого группирования, упорядочения или проекции.</span><span class="sxs-lookup"><span data-stu-id="04476-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="04476-112">Все имена элементов, определенные в предложении FROM, доступны в выражении предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="04476-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04476-113">См. также</span><span class="sxs-lookup"><span data-stu-id="04476-113">See Also</span></span>  
 [<span data-ttu-id="04476-114">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="04476-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="04476-115">Выражения запросов</span><span class="sxs-lookup"><span data-stu-id="04476-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
