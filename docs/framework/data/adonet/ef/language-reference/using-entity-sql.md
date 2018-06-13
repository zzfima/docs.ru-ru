---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 89306c8b4c317ebaba0d964869c4fe9e1028631a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762342"
---
# <a name="using-entity-sql"></a>USING (Entity SQL)
Задает пространства имен, используемые в выражении запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Аргументы  
 `alias`  
 Задает более короткий псевдоним, с помощью которого можно уточнить применяемое пространство имен.  
  
 `namespace`  
 Любое допустимое пространство имен.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL используется оператор USING для задания пространства имен, используемого в выражении запроса. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>См. также  
 [Пространства имен](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
