---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 0bcd4a2140a04fa0ecbfa7eee450ed029f278286
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319204"
---
# <a name="using-entity-sql"></a><span data-ttu-id="46fae-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="46fae-102">USING (Entity SQL)</span></span>
<span data-ttu-id="46fae-103">Задает пространства имен, используемые в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="46fae-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46fae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46fae-104">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="46fae-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="46fae-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="46fae-106">Задает более короткий псевдоним, с помощью которого можно уточнить применяемое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="46fae-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="46fae-107">Любое допустимое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="46fae-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46fae-108">Пример</span><span class="sxs-lookup"><span data-stu-id="46fae-108">Example</span></span>  
 <span data-ttu-id="46fae-109">В следующем запросе Entity SQL используется оператор USING для задания пространства имен, используемого в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="46fae-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="46fae-110">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="46fae-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="46fae-111">Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="46fae-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="46fae-112">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="46fae-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="46fae-113">См. также</span><span class="sxs-lookup"><span data-stu-id="46fae-113">See also</span></span>

- [<span data-ttu-id="46fae-114">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="46fae-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="46fae-115">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="46fae-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
