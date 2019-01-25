---
title: Разбивка на страницы (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: f6ff95c387224705e58edb0b80bf908f39391a80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672933"
---
# <a name="paging-entity-sql"></a>Разбивка на страницы (Entity SQL)
Физическое разбиение на страницы может выполняться с помощью [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) и [ограничение](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) вложенные предложения в [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) предложение. Для детерминированного физического разбиения на страницы необходимо использовать предложения SKIP и LIMIT. Если требуется ограничить количество строк в результате недетерминированным образом, следует использовать [ВЕРХНЕЙ](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md). Предложения TOP и SKIP/LIMIT являются взаимоисключающими.  
  
## <a name="top-overview"></a>Общие сведения о предложении TOP  
 Предложение SELECT может иметь необязательное вложенное предложение TOP, которое следует за необязательным модификатором ALL/DISTINCT. Предложение TOP указывает, что в результатах запроса возвращается только набор первых строк. Дополнительные сведения см. в разделе [ВЕРХНЕЙ](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Общие сведения о предложениях SKIP и LIMIT  
 Предложения SKIP и LIMIT являются частью предложения ORDER BY. Если в предложении ORDER BY имеется вложенное предложение SKIP, результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP. Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой. Если в предложении ORDER BY имеется подчиненное выражение LIMIT, результаты запроса будут отсортированы в соответствии со спецификацией сортировки, а количество строк в наборе будет ограничено выражением LIMIT. Например, LIMIT 5 ограничит результирующий набор пятью экземплярами строк. Предложения SKIP и LIMIT необязательно использовать вместе: в предложение ORDER BY можно включить только SKIP или только LIMIT. Дополнительные сведения см. в следующих разделах:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>См. также
- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Практическое руководство. Постранично просмотреть результаты запроса](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)
