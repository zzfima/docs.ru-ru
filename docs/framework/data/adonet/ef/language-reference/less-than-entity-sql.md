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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 14e1af042601c11cae32dd3046dee73ec4fd209f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lt-less-than-entity-sql"></a><span data-ttu-id="38306-102">&lt; (меньше) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="38306-102">&lt; (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="38306-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.</span><span class="sxs-lookup"><span data-stu-id="38306-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38306-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38306-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="38306-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="38306-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="38306-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="38306-106">Any valid expression.</span></span> <span data-ttu-id="38306-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="38306-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="38306-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="38306-108">Result Types</span></span>  
 <span data-ttu-id="38306-109">`true` , если значение левого выражения меньше, чем правого; в противном случае - `false`.</span><span class="sxs-lookup"><span data-stu-id="38306-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38306-110">Пример</span><span class="sxs-lookup"><span data-stu-id="38306-110">Example</span></span>  
 <span data-ttu-id="38306-111">В следующем запросе Entity SQL оператор < используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого.</span><span class="sxs-lookup"><span data-stu-id="38306-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="38306-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="38306-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="38306-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="38306-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="38306-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="38306-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="38306-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="38306-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="38306-116">См. также</span><span class="sxs-lookup"><span data-stu-id="38306-116">See Also</span></span>  
 [<span data-ttu-id="38306-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="38306-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
