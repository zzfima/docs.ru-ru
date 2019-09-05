---
title: Не поддерживаемые выражения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248783"
---
# <a name="unsupported-expressions"></a>Неподдерживаемые выражения

В этом разделе описываются выражения Transact-SQL, которые не поддерживаются в [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Дополнительные сведения см. в разделе [Entity SQL отличается от языка Transact-SQL](how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Количественные предикаты

Transact-SQL позволяет создавать конструкции следующего вида:

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] такие конструкции не поддерживает. Эквивалентные выражения могут быть написаны на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующим образом:

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>* - оператор

Transact-SQL поддерживает использование оператора * в предложении SELECT для указания того, что все столбцы должны быть прогнозируемыми. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это не поддерживается.

## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](entity-sql-overview.md)
- [Отличия Entity SQL от Transact-SQL](how-entity-sql-differs-from-transact-sql.md)
