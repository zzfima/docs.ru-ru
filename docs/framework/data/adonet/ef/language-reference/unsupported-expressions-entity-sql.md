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
# <a name="unsupported-expressions"></a><span data-ttu-id="2957a-102">Неподдерживаемые выражения</span><span class="sxs-lookup"><span data-stu-id="2957a-102">Unsupported expressions</span></span>

<span data-ttu-id="2957a-103">В этом разделе описываются выражения [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], не поддерживаемые в [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2957a-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="2957a-104">Дополнительные сведения см. в разделе [Entity SQL отличия от Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2957a-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="2957a-105">Предикаты с кванторами</span><span class="sxs-lookup"><span data-stu-id="2957a-105">Quantified predicates</span></span>

<span data-ttu-id="2957a-106">Язык [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] допускает присутствие следующих конструкций:</span><span class="sxs-lookup"><span data-stu-id="2957a-106">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="2957a-107">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] такие конструкции не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="2957a-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="2957a-108">Эквивалентные выражения могут быть написаны на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2957a-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="2957a-109">\* - оператор</span><span class="sxs-lookup"><span data-stu-id="2957a-109">\* operator</span></span>

<span data-ttu-id="2957a-110">В [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] поддерживается использование оператора \* в предложении SELECT, чтобы указать, что необходимо вернуть все столбцы. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2957a-110">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="2957a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2957a-111">See also</span></span>

- [<span data-ttu-id="2957a-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2957a-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="2957a-113">Отличия Entity SQL от Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2957a-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
