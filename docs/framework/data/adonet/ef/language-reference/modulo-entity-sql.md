---
title: (Остаток от деления) (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e204612904aa55b4a0ae9aa65f2bbfd644bbc396
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="0f935-102">(Остаток от деления) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0f935-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="0f935-103">Возвращает остаток от деления значения одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="0f935-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f935-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f935-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="0f935-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0f935-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="0f935-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="0f935-106">The numeric expression to divide.</span></span> <span data-ttu-id="0f935-107">`dividend` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="0f935-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="0f935-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="0f935-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="0f935-109">`divisor` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="0f935-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0f935-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="0f935-110">Result Types</span></span>  
 <span data-ttu-id="0f935-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="0f935-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f935-112">Пример</span><span class="sxs-lookup"><span data-stu-id="0f935-112">Example</span></span>  
 <span data-ttu-id="0f935-113">В следующем запросе Entity SQL используется арифметический оператор % для получения остатка от деления одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="0f935-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="0f935-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="0f935-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0f935-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="0f935-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0f935-116">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0f935-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="0f935-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0f935-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="0f935-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0f935-118">See Also</span></span>  
 [<span data-ttu-id="0f935-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0f935-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
