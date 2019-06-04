---
title: Не поддерживаемые выражения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: af0e00f470584883b6a65b63f2650c1c359b404c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489857"
---
# <a name="unsupported-expressions"></a>Неподдерживаемые выражения

В этом разделе описываются выражения Transact-SQL, которые не поддерживаются в [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Дополнительные сведения см. в разделе [Entity SQL отличия от Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Предикаты с кванторами

Transact-SQL поддерживает конструкции следующего вида:

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

Transact-SQL поддерживает использование * оператор в предложении SELECT, чтобы указать, что необходимо вернуть все столбцы. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это не поддерживается.

## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Отличия Entity SQL от Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
