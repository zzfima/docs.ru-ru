---
title: Выражения запросов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 4428286890f41573a02daf31a4593d0c8f9ad34b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249278"
---
# <a name="query-expressions-entity-sql"></a>Выражения запросов (Entity SQL)
Выражение запроса объединяет в едином синтаксисе множество разных операторов запросов. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]предоставляет различные типы выражений, включая [литералы](literals-entity-sql.md), [Параметры](parameters-entity-sql.md), [переменные](variables-entity-sql.md), операторы, [функции](functions-entity-sql.md), операторы SET и т. д. Дополнительные сведения см. в разделе [Справочник по Entity SQL](entity-sql-reference.md).  
  
## <a name="clauses"></a>Предложения  
 Выражение запроса состоит из предложений, которые последовательно применяют операции к набору объектов. Они основаны на предложениях, из которых состоят стандартные инструкции выбора языка SQL: [Выберите](select-entity-sql.md), [из](from-entity-sql.md), [где](where-entity-sql.md), [Группировать по](group-by-entity-sql.md), [HAVING](having-entity-sql.md)и [Упорядочить по](order-by-entity-sql.md).  
  
## <a name="scope"></a>`Scope`  
 Имена, определенные в предложении FROM, появляются в области FROM в порядке перечисления, слева направо. В списке JOIN выражения могут ссылаться на имена, которые определены в списке ранее. Открытые свойства элементов, определяемых в предложении FROM, в область FROM не добавляются: в ссылке на них следует всегда использовать имя с псевдонимом. Но обычно все части выражения выбора находятся в области FROM.  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
