---
title: Переменные (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bf6fa95e38d1eb5817fd67165b6993cbb0755fd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153586"
---
# <a name="variables-entity-sql"></a>Переменные (Entity SQL)
## <a name="variable"></a>Переменная  
 Выражение переменной – это ссылка на именованное выражение, определенное в текущей области. Ссылка на переменную должен быть допустимым [!INCLUDE[esql](../../../../../../includes/esql-md.md)] идентификатор, как определено в [идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 В следующем примере показано применение переменной в выражении. Символ `c` в предложении FROM является определением переменной. Использование символа `c` в предложении SELECT представляет ссылку на переменную.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>См. также

- [Идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [Параметры](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
