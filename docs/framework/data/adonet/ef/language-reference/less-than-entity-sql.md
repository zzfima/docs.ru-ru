---
title: "&lt; (меньше) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5bf1560c0bebafcfdbf79ca9a9906c9df23b7cae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="lt-less-than-entity-sql"></a><span data-ttu-id="bed27-102">&lt; (меньше) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bed27-102">&lt; (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="bed27-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.</span><span class="sxs-lookup"><span data-stu-id="bed27-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bed27-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="bed27-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bed27-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bed27-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="bed27-106">Any valid expression.</span></span> <span data-ttu-id="bed27-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="bed27-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bed27-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="bed27-108">Result Types</span></span>  
 <span data-ttu-id="bed27-109">`true` , если значение левого выражения меньше, чем правого; в противном случае - `false`.</span><span class="sxs-lookup"><span data-stu-id="bed27-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed27-110">Пример</span><span class="sxs-lookup"><span data-stu-id="bed27-110">Example</span></span>  
 <span data-ttu-id="bed27-111">В следующем запросе Entity SQL оператор < используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого.</span><span class="sxs-lookup"><span data-stu-id="bed27-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="bed27-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="bed27-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bed27-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="bed27-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="bed27-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bed27-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="bed27-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bed27-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="bed27-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bed27-116">See Also</span></span>  
 [<span data-ttu-id="bed27-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bed27-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
