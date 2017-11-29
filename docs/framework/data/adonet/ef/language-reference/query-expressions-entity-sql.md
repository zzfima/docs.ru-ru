---
title: "Выражения запросов (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8b30deea78efe275ccaf6beabafb16a84357ba26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="query-expressions-entity-sql"></a>Выражения запросов (Entity SQL)
Выражение запроса объединяет в едином синтаксисе множество разных операторов запросов. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]предоставляет различные типы выражений, включая следующие: [литералы](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [параметры](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [переменных](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), операторы, [функции](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)операторов работы с наборами и т. д. Дополнительные сведения см. в разделе [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## <a name="clauses"></a>Предложения  
 Выражение запроса состоит из предложений, которые последовательно применяют операции к коллекции объектов. Они основаны на тех же предложениях, найти в стандартной инструкции SQL select: [ВЫБЕРИТЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [ГДЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [НАЛИЧИЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), и [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## <a name="scope"></a>Область  
 Имена, определенные в предложении FROM, появляются в области FROM в порядке перечисления, слева направо. В списке JOIN выражения могут ссылаться на имена, которые определены в списке ранее. Открытые свойства элементов, указанные в предложении FROM, не добавляются в область FROM. На них всегда следует ссылаться через имя с псевдонимом. Но обычно все части выражения выбора находятся в области FROM.  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
