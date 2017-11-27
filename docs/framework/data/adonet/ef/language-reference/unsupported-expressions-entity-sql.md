---
title: "Не поддерживаемые выражения (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c18c726a962d9a29a3dace1ebd5c2073637bb4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="unsupported-expressions-entity-sql"></a><span data-ttu-id="612ea-102">Не поддерживаемые выражения (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="612ea-102">Unsupported Expressions (Entity SQL)</span></span>
<span data-ttu-id="612ea-103">В этом разделе описываются выражения [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], не поддерживаемые в [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="612ea-103">This topic describes [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="612ea-104">Дополнительные сведения см. в разделе [как Entity SQL отличается от языка Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="612ea-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>  
  
## <a name="quantified-predicates"></a><span data-ttu-id="612ea-105">Предикаты с кванторами</span><span class="sxs-lookup"><span data-stu-id="612ea-105">Quantified Predicates</span></span>  
 <span data-ttu-id="612ea-106">Язык [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] допускает присутствие следующих конструкций:</span><span class="sxs-lookup"><span data-stu-id="612ea-106">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] allows constructs of the following form:</span></span>  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 <span data-ttu-id="612ea-107">Язык [!INCLUDE[esql](../../../../../../includes/esql-md.md)] такие конструкции не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="612ea-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="612ea-108">Эквивалентные выражения могут быть написаны на языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] следующим образом:</span><span class="sxs-lookup"><span data-stu-id="612ea-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## <a name="-operator"></a><span data-ttu-id="612ea-109">Оператор *</span><span class="sxs-lookup"><span data-stu-id="612ea-109">* Operator</span></span>  
 <span data-ttu-id="612ea-110">В [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] поддерживается использование оператора * в предложении SELECT, чтобы указать, что необходимо вернуть все столбцы. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="612ea-110">[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] supports the use of the * operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612ea-111">См. также</span><span class="sxs-lookup"><span data-stu-id="612ea-111">See Also</span></span>  
 [<span data-ttu-id="612ea-112">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="612ea-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="612ea-113">Отличия Entity SQL от Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="612ea-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
