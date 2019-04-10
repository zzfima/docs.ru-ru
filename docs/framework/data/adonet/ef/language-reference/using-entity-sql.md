---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: e14b7857a65898683939647c872c48d0b3fe458a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297867"
---
# <a name="using-entity-sql"></a><span data-ttu-id="2f385-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2f385-102">USING (Entity SQL)</span></span>
<span data-ttu-id="2f385-103">Задает пространства имен, используемые в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="2f385-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f385-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f385-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f385-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2f385-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="2f385-106">Задает более короткий псевдоним, с помощью которого можно уточнить применяемое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="2f385-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="2f385-107">Любое допустимое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="2f385-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f385-108">Пример</span><span class="sxs-lookup"><span data-stu-id="2f385-108">Example</span></span>  
 <span data-ttu-id="2f385-109">В следующем запросе Entity SQL используется оператор USING для задания пространства имен, используемого в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="2f385-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="2f385-110">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="2f385-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2f385-111">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2f385-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="2f385-112">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2f385-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f385-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2f385-113">See also</span></span>

- [<span data-ttu-id="2f385-114">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="2f385-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="2f385-115">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2f385-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
