---
title: Не поддерживаемые выражения (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: a47ff46ca99a84500bc5dfecc19bb31652e9b4b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628026"
---
# <a name="unsupported-expressions"></a>Неподдерживаемые выражения

В этом разделе описываются выражения [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], не поддерживаемые в [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Дополнительные сведения см. в разделе [Entity SQL отличия от Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Предикаты с кванторами

Язык [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] допускает присутствие следующих конструкций:

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

В [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] поддерживается использование оператора * в предложении SELECT, чтобы указать, что необходимо вернуть все столбцы. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это не поддерживается.

## <a name="see-also"></a>См. также

- [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Отличия Entity SQL от Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
