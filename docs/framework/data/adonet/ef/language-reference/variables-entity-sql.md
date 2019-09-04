---
title: Переменные (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 5be9c80c2fce877f179d79f6b2c22f11e31e65a0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248692"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="fb3b1-102">Переменные (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fb3b1-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="fb3b1-103">Переменная</span><span class="sxs-lookup"><span data-stu-id="fb3b1-103">Variable</span></span>  
 <span data-ttu-id="fb3b1-104">Выражение переменной – это ссылка на именованное выражение, определенное в текущей области.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="fb3b1-105">Ссылка на переменную должна быть допустимым [!INCLUDE[esql](../../../../../../includes/esql-md.md)] идентификатором, как определено в [идентификаторах](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="fb3b1-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="fb3b1-106">В следующем примере показано применение переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="fb3b1-107">Символ `c` в предложении FROM является определением переменной.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="fb3b1-108">Использование символа `c` в предложении SELECT представляет ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb3b1-109">См. также</span><span class="sxs-lookup"><span data-stu-id="fb3b1-109">See also</span></span>

- [<span data-ttu-id="fb3b1-110">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="fb3b1-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="fb3b1-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb3b1-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="fb3b1-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fb3b1-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
