---
title: INTERSECT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 70078c849e78ff31d3d55c12606d8423d4e6772f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="e4d85-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e4d85-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="e4d85-103">Возвращает коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="e4d85-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="e4d85-104">Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="e4d85-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d85-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4d85-105">Syntax</span></span>  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e4d85-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e4d85-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e4d85-107">Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса.</span><span class="sxs-lookup"><span data-stu-id="e4d85-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4d85-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e4d85-108">Return Value</span></span>  
 <span data-ttu-id="e4d85-109">Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.</span><span class="sxs-lookup"><span data-stu-id="e4d85-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4d85-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4d85-110">Remarks</span></span>  
 <span data-ttu-id="e4d85-111">INTERSECT - один из операторов для работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4d85-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="e4d85-112">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="e4d85-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="e4d85-113">Сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов работы с наборами см. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e4d85-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4d85-114">Пример</span><span class="sxs-lookup"><span data-stu-id="e4d85-114">Example</span></span>  
 <span data-ttu-id="e4d85-115">Следующий запрос Entity SQL использует оператор INTERSECT, чтобы вернуть коллекцию различных значений, возвращаемых выражениями запроса, указанных как слева, так и справа от операнда INTERSECT.</span><span class="sxs-lookup"><span data-stu-id="e4d85-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="e4d85-116">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e4d85-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e4d85-117">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="e4d85-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e4d85-118">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e4d85-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e4d85-119">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e4d85-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="e4d85-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e4d85-120">See Also</span></span>  
 [<span data-ttu-id="e4d85-121">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e4d85-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
