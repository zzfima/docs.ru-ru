---
title: Переменные (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: a16c450401eee1021aeef885fba129c943a87fd7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742280"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="9849e-102">Переменные (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9849e-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="9849e-103">Переменная</span><span class="sxs-lookup"><span data-stu-id="9849e-103">Variable</span></span>  
 <span data-ttu-id="9849e-104">Выражение переменной – это ссылка на именованное выражение, определенное в текущей области.</span><span class="sxs-lookup"><span data-stu-id="9849e-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="9849e-105">Ссылка на переменную должен быть допустимым [!INCLUDE[esql](../../../../../../includes/esql-md.md)] идентификатор, как определено в [идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9849e-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="9849e-106">В следующем примере показано применение переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="9849e-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="9849e-107">Символ `c` в предложении FROM является определением переменной.</span><span class="sxs-lookup"><span data-stu-id="9849e-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="9849e-108">Использование символа `c` в предложении SELECT представляет ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="9849e-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="9849e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9849e-109">See also</span></span>
- [<span data-ttu-id="9849e-110">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="9849e-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="9849e-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="9849e-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="9849e-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9849e-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
