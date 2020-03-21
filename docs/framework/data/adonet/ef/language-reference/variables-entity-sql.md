---
title: Переменные (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 88ee41bc08711cf84b8b2e273c9ac0f4267d1d34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149821"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="fdbf2-102">Переменные (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fdbf2-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="fdbf2-103">Переменная</span><span class="sxs-lookup"><span data-stu-id="fdbf2-103">Variable</span></span>  
 <span data-ttu-id="fdbf2-104">Выражение переменной – это ссылка на именованное выражение, определенное в текущей области.</span><span class="sxs-lookup"><span data-stu-id="fdbf2-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="fdbf2-105">Переменная ссылка должна [!INCLUDE[esql](../../../../../../includes/esql-md.md)] быть действительным идентификатором, как это определено в [идентификаторах.](identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="fdbf2-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="fdbf2-106">В следующем примере показано применение переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="fdbf2-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="fdbf2-107">Символ `c` в предложении FROM является определением переменной.</span><span class="sxs-lookup"><span data-stu-id="fdbf2-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="fdbf2-108">Использование символа `c` в предложении SELECT представляет ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="fdbf2-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdbf2-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fdbf2-109">See also</span></span>

- [<span data-ttu-id="fdbf2-110">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="fdbf2-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="fdbf2-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="fdbf2-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="fdbf2-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fdbf2-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
