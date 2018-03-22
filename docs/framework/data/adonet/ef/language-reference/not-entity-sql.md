---
title: '! (NOT) (язык Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: f3786724280cc077574f37e4d373c85faf5340f3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="-not-entity-sql"></a><span data-ttu-id="80dfd-103">!</span><span class="sxs-lookup"><span data-stu-id="80dfd-103">!</span></span> <span data-ttu-id="80dfd-104">(NOT) (язык Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="80dfd-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="80dfd-105">Изменяет значение выражения типа `Boolean` на обратное.</span><span class="sxs-lookup"><span data-stu-id="80dfd-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80dfd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80dfd-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="80dfd-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="80dfd-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="80dfd-108">Любое допустимое выражение, возвращающее значение типа Boolean.</span><span class="sxs-lookup"><span data-stu-id="80dfd-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80dfd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="80dfd-109">Remarks</span></span>  
 <span data-ttu-id="80dfd-110">Восклицательный знак (!) имеет ту же функциональность, что и оператор NOT.</span><span class="sxs-lookup"><span data-stu-id="80dfd-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80dfd-111">Пример</span><span class="sxs-lookup"><span data-stu-id="80dfd-111">Example</span></span>  
 <span data-ttu-id="80dfd-112">Следующий запрос Entity SQL использует оператор NOT, чтобы изменить на обратное выражение типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="80dfd-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="80dfd-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="80dfd-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="80dfd-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="80dfd-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="80dfd-115">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="80dfd-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="80dfd-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="80dfd-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="80dfd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="80dfd-117">See Also</span></span>  
 [<span data-ttu-id="80dfd-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="80dfd-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
