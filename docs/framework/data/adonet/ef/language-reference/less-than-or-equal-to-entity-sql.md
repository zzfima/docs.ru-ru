---
title: "&lt;= (меньше или равно) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ca900cde1845083e515fa4e8e884b57f8ae689a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lt-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="3365b-102">&lt;= (меньше или равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3365b-102">&lt;= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="3365b-103">Сравнивает два выражения и определяет, имеет ли левое выражение значение, меньшее или равное значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="3365b-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3365b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3365b-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3365b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3365b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3365b-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="3365b-106">Any valid expression.</span></span> <span data-ttu-id="3365b-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="3365b-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3365b-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="3365b-108">Result Types</span></span>  
 <span data-ttu-id="3365b-109">Значение`true` , если левое выражение меньше или равно правому выражению. В противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="3365b-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3365b-110">Пример</span><span class="sxs-lookup"><span data-stu-id="3365b-110">Example</span></span>  
 <span data-ttu-id="3365b-111">Следующий запрос Entity SQL использует оператор сравнения <= для сравнения двух выражений и определяет, имеет ли левое выражение значение, меньшее или равное значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="3365b-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="3365b-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3365b-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3365b-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="3365b-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3365b-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3365b-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="3365b-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3365b-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="3365b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3365b-116">See Also</span></span>  
 [<span data-ttu-id="3365b-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3365b-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
