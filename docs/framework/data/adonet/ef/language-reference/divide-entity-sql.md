---
title: '- (Деление) (Язык entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 5f9f640d50ec24b30cedfe0d4d8d4982509efc35
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="0d34d-102">/ (деление) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0d34d-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="0d34d-103">Делит одно число на другое.</span><span class="sxs-lookup"><span data-stu-id="0d34d-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d34d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d34d-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d34d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0d34d-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="0d34d-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="0d34d-106">The numeric expression to divide.</span></span> <span data-ttu-id="0d34d-107">`dividend` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="0d34d-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="0d34d-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="0d34d-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="0d34d-109">`divisor` - любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="0d34d-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0d34d-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="0d34d-110">Result Types</span></span>  
 <span data-ttu-id="0d34d-111">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="0d34d-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="0d34d-112">Дополнительные сведения о неявном повышении уровня типов см. в разделе [системы типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0d34d-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d34d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="0d34d-113">Example</span></span>  
 <span data-ttu-id="0d34d-114">Следующий запрос Entity SQL использует арифметический оператор деления для деления одного числа на другое.</span><span class="sxs-lookup"><span data-stu-id="0d34d-114">The following Entity SQL query uses the / arithmetic operator to divide one numer by another.</span></span> <span data-ttu-id="0d34d-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="0d34d-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0d34d-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="0d34d-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0d34d-117">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0d34d-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="0d34d-118">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0d34d-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="0d34d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0d34d-119">See Also</span></span>  
 [<span data-ttu-id="0d34d-120">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0d34d-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
