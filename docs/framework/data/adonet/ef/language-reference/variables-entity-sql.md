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
# <a name="variables-entity-sql"></a>Переменные (Entity SQL)
## <a name="variable"></a>Переменная  
 Выражение переменной – это ссылка на именованное выражение, определенное в текущей области. Переменная ссылка должна [!INCLUDE[esql](../../../../../../includes/esql-md.md)] быть действительным идентификатором, как это определено в [идентификаторах.](identifiers-entity-sql.md)  
  
 В следующем примере показано применение переменной в выражении. Символ `c` в предложении FROM является определением переменной. Использование символа `c` в предложении SELECT представляет ссылку на переменную.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>См. также раздел

- [Идентификаторы](identifiers-entity-sql.md)
- [Параметры](parameters-entity-sql.md)
- [Общие сведения об Entity SQL](entity-sql-overview.md)
