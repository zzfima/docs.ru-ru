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
# <a name="variables-entity-sql"></a>Переменные (Entity SQL)
## <a name="variable"></a>Переменная  
 Выражение переменной – это ссылка на именованное выражение, определенное в текущей области. Ссылка на переменную должна быть допустимым идентификатором [!INCLUDE[esql](../../../../../../includes/esql-md.md)], как определено в [идентификаторах](identifiers-entity-sql.md).  
  
 В следующем примере показано применение переменной в выражении. Символ `c` в предложении FROM является определением переменной. Использование символа `c` в предложении SELECT представляет ссылку на переменную.  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>См. также

- [Идентификаторы](identifiers-entity-sql.md)
- [Параметры](parameters-entity-sql.md)
- [Общие сведения об Entity SQL](entity-sql-overview.md)
