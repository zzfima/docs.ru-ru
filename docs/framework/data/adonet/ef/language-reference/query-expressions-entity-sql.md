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
ms.workload: dotnet
ms.openlocfilehash: 8ad130797be55b33b319ca4e85de09ec3e00a554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="e7262-102">Выражения запросов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e7262-102">Query Expressions (Entity SQL)</span></span>
<span data-ttu-id="e7262-103">Выражение запроса объединяет в едином синтаксисе множество разных операторов запросов.</span><span class="sxs-lookup"><span data-stu-id="e7262-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e7262-104">предоставляет различные типы выражений, включая следующие: [литералы](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [параметры](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [переменных](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), операторы, [функции](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)операторов работы с наборами и т. д.</span><span class="sxs-lookup"><span data-stu-id="e7262-104"> provides various kinds of expressions, including the following: [literals](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [parameters](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [variables](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), operators, [functions](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="e7262-105">Дополнительные сведения см. в разделе [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e7262-105">For more information, see [Entity SQL Reference](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="e7262-106">Предложения</span><span class="sxs-lookup"><span data-stu-id="e7262-106">Clauses</span></span>  
 <span data-ttu-id="e7262-107">Выражение запроса состоит из предложений, которые последовательно применяют операции к коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="e7262-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="e7262-108">Они основаны на тех же предложениях, найти в стандартной инструкции SQL select: [ВЫБЕРИТЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [ГДЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [НАЛИЧИЕ](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), и [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e7262-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [WHERE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), and [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="e7262-109">Область</span><span class="sxs-lookup"><span data-stu-id="e7262-109">Scope</span></span>  
 <span data-ttu-id="e7262-110">Имена, определенные в предложении FROM, появляются в области FROM в порядке перечисления, слева направо.</span><span class="sxs-lookup"><span data-stu-id="e7262-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="e7262-111">В списке JOIN выражения могут ссылаться на имена, которые определены в списке ранее.</span><span class="sxs-lookup"><span data-stu-id="e7262-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="e7262-112">Открытые свойства элементов, указанные в предложении FROM, не добавляются в область FROM. На них всегда следует ссылаться через имя с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="e7262-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="e7262-113">Но обычно все части выражения выбора находятся в области FROM.</span><span class="sxs-lookup"><span data-stu-id="e7262-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7262-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e7262-114">See Also</span></span>  
 [<span data-ttu-id="e7262-115">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e7262-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
