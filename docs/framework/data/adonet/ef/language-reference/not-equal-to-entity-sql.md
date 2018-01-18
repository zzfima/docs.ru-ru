---
title: "!= (не равно) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 237dae641c272260e37fa7757792247700784d17
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="75892-102">!= (не равно) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="75892-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="75892-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения не равным значению правого выражения.</span><span class="sxs-lookup"><span data-stu-id="75892-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="75892-104">Действие оператора != (не равно) эквивалентно действию оператора <>.</span><span class="sxs-lookup"><span data-stu-id="75892-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75892-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75892-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="75892-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="75892-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="75892-107">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="75892-107">Any valid expression.</span></span> <span data-ttu-id="75892-108">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="75892-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="75892-109">Типы результата</span><span class="sxs-lookup"><span data-stu-id="75892-109">Result Types</span></span>  
 <span data-ttu-id="75892-110">`true` , если значение левого выражения не равно значению правого; в противном случае - `false`.</span><span class="sxs-lookup"><span data-stu-id="75892-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75892-111">Пример</span><span class="sxs-lookup"><span data-stu-id="75892-111">Example</span></span>  
 <span data-ttu-id="75892-112">В следующем запросе Entity SQL оператор != используется для сравнения двух выражений, чтобы определить, отличается ли значение левого выражения от значения правого.</span><span class="sxs-lookup"><span data-stu-id="75892-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="75892-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="75892-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="75892-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="75892-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="75892-115">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="75892-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="75892-116">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="75892-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="75892-117">См. также</span><span class="sxs-lookup"><span data-stu-id="75892-117">See Also</span></span>  
 [<span data-ttu-id="75892-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="75892-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
