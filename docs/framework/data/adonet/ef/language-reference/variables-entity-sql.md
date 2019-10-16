---
title: Переменные (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319191"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="22510-102">Переменные (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="22510-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="22510-103">Переменная</span><span class="sxs-lookup"><span data-stu-id="22510-103">Variable</span></span>  
 <span data-ttu-id="22510-104">Выражение переменной – это ссылка на именованное выражение, определенное в текущей области.</span><span class="sxs-lookup"><span data-stu-id="22510-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="22510-105">Ссылка на переменную должна быть допустимым идентификатором [!INCLUDE[esql](../../../../../../includes/esql-md.md)], как определено в [идентификаторах](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="22510-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="22510-106">В следующем примере показано применение переменной в выражении.</span><span class="sxs-lookup"><span data-stu-id="22510-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="22510-107">Символ `c` в предложении FROM является определением переменной.</span><span class="sxs-lookup"><span data-stu-id="22510-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="22510-108">Использование символа `c` в предложении SELECT представляет ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="22510-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="22510-109">См. также</span><span class="sxs-lookup"><span data-stu-id="22510-109">See also</span></span>

- [<span data-ttu-id="22510-110">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="22510-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="22510-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="22510-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="22510-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="22510-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
