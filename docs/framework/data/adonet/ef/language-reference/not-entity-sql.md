---
title: '! (NOT) (язык Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 7755219c5238f78e59332c508643fe2ae1f5096f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319521"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="026d5-103">!</span><span class="sxs-lookup"><span data-stu-id="026d5-103">!</span></span> <span data-ttu-id="026d5-104">(NOT) (язык Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="026d5-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="026d5-105">Изменяет значение выражения типа `Boolean` на обратное.</span><span class="sxs-lookup"><span data-stu-id="026d5-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="026d5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="026d5-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
``` 
  
## <a name="arguments"></a><span data-ttu-id="026d5-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="026d5-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="026d5-108">Любое допустимое выражение, возвращающее значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="026d5-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="026d5-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="026d5-109">Remarks</span></span>  
 <span data-ttu-id="026d5-110">Восклицательный знак (!) имеет ту же функциональность, что и оператор NOT.</span><span class="sxs-lookup"><span data-stu-id="026d5-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="026d5-111">Пример</span><span class="sxs-lookup"><span data-stu-id="026d5-111">Example</span></span>  
 <span data-ttu-id="026d5-112">Следующий запрос Entity SQL использует оператор NOT, чтобы изменить на обратное выражение типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="026d5-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="026d5-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="026d5-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="026d5-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="026d5-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="026d5-115">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="026d5-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="026d5-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="026d5-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="026d5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="026d5-117">See also</span></span>

- [<span data-ttu-id="026d5-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="026d5-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
