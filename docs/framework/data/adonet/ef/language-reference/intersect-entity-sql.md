---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: dc7338d176302b8683d541ab0dc715dd8d149c6f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319767"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="205f9-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="205f9-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="205f9-103">Возвращает коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="205f9-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="205f9-104">Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="205f9-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="205f9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="205f9-105">Syntax</span></span>  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="205f9-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="205f9-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="205f9-107">Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса.</span><span class="sxs-lookup"><span data-stu-id="205f9-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="205f9-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="205f9-108">Return Value</span></span>  
 <span data-ttu-id="205f9-109">Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.</span><span class="sxs-lookup"><span data-stu-id="205f9-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="205f9-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="205f9-110">Remarks</span></span>  
 <span data-ttu-id="205f9-111">INTERSECT - один из операторов для работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="205f9-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="205f9-112">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="205f9-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="205f9-113">Сведения о приоритетах для операторов установки [!INCLUDE[esql](../../../../../../includes/esql-md.md)] см. в разделе [except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="205f9-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="205f9-114">Пример</span><span class="sxs-lookup"><span data-stu-id="205f9-114">Example</span></span>  
 <span data-ttu-id="205f9-115">Следующий запрос Entity SQL использует оператор INTERSECT, чтобы вернуть коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="205f9-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="205f9-116">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="205f9-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="205f9-117">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="205f9-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="205f9-118">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="205f9-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="205f9-119">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="205f9-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="205f9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="205f9-120">See also</span></span>

- [<span data-ttu-id="205f9-121">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="205f9-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
