---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 9495e5daf88326c5a682172d835c3349fe79e571
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248750"
---
# <a name="using-entity-sql"></a><span data-ttu-id="67548-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="67548-102">USING (Entity SQL)</span></span>
<span data-ttu-id="67548-103">Задает пространства имен, используемые в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="67548-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67548-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67548-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="67548-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="67548-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="67548-106">Задает более короткий псевдоним, с помощью которого можно уточнить применяемое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="67548-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="67548-107">Любое допустимое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="67548-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67548-108">Пример</span><span class="sxs-lookup"><span data-stu-id="67548-108">Example</span></span>  
 <span data-ttu-id="67548-109">В следующем запросе Entity SQL используется оператор USING для задания пространства имен, используемого в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="67548-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="67548-110">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="67548-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="67548-111">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего тип PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="67548-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="67548-112">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="67548-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="67548-113">См. также</span><span class="sxs-lookup"><span data-stu-id="67548-113">See also</span></span>

- [<span data-ttu-id="67548-114">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="67548-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="67548-115">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="67548-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
