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
# <a name="unsupported-expressions"></a><span data-ttu-id="cb7c9-102">Неподдерживаемые выражения</span><span class="sxs-lookup"><span data-stu-id="cb7c9-102">Unsupported expressions</span></span>

<span data-ttu-id="cb7c9-103">В этом разделе описываются выражения Transact-SQL, которые не поддерживаются в [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb7c9-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="cb7c9-104">Дополнительные сведения см. в разделе [Entity SQL отличается от языка Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cb7c9-104">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="cb7c9-105">Количественные предикаты</span><span class="sxs-lookup"><span data-stu-id="cb7c9-105">Quantified predicates</span></span>

<span data-ttu-id="cb7c9-106">Transact-SQL позволяет создавать конструкции следующего вида:</span><span class="sxs-lookup"><span data-stu-id="cb7c9-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="cb7c9-107">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] такие конструкции не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="cb7c9-108">Эквивалентные выражения могут быть написаны на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb7c9-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="cb7c9-109">\* - оператор</span><span class="sxs-lookup"><span data-stu-id="cb7c9-109">\* operator</span></span>

<span data-ttu-id="cb7c9-110">Transact-SQL поддерживает использование оператора \* в предложении SELECT для указания того, что все столбцы должны быть прогнозируемыми. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="cb7c9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cb7c9-111">See also</span></span>

- [<span data-ttu-id="cb7c9-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cb7c9-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="cb7c9-113">Отличия Entity SQL от Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb7c9-113">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
