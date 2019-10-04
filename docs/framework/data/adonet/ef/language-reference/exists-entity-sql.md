---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 44f128a292b013fd3a3a80efdd2d10a63e3cfb07
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833840"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="ba728-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ba728-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="ba728-103">Определяет, является ли коллекция пустой.</span><span class="sxs-lookup"><span data-stu-id="ba728-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba728-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba728-104">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba728-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ba728-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ba728-106">Любое допустимое выражение, возвращающее коллекцию.</span><span class="sxs-lookup"><span data-stu-id="ba728-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="ba728-107">NOT</span><span class="sxs-lookup"><span data-stu-id="ba728-107">NOT</span></span>  
 <span data-ttu-id="ba728-108">Указывает, что результат оператора EXISTS должен быть инвертирован.</span><span class="sxs-lookup"><span data-stu-id="ba728-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba728-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba728-109">Return Value</span></span>  
 <span data-ttu-id="ba728-110">Значение `true`, если коллекция не пуста; в противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ba728-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba728-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba728-111">Remarks</span></span>  
 <span data-ttu-id="ba728-112">EXISTS - это один из операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba728-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="ba728-113">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="ba728-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="ba728-114">Сведения о приоритетах для операторов установки [!INCLUDE[esql](../../../../../../includes/esql-md.md)] см. в разделе [except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ba728-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba728-115">Пример</span><span class="sxs-lookup"><span data-stu-id="ba728-115">Example</span></span>  
 <span data-ttu-id="ba728-116">В следующем запросе Entity SQL оператор EXISTS используется, чтобы определить, пуста ли коллекция.</span><span class="sxs-lookup"><span data-stu-id="ba728-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="ba728-117">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ba728-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ba728-118">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="ba728-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ba728-119">Выполните процедуру, описанную в разделе [How: Выполните запрос, возвращающий Структуралтипе Results @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="ba728-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ba728-120">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ba728-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="ba728-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ba728-121">See also</span></span>

- [<span data-ttu-id="ba728-122">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ba728-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
