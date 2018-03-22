---
title: '- (Вычитание) (Язык entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 5ca2bc8cb34d99421962289930c26de84eaa68e2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="bdfa1-102">- (вычитание) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bdfa1-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="bdfa1-103">Вычитает одно число из другого.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfa1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdfa1-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="bdfa1-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bdfa1-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bdfa1-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bdfa1-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="bdfa1-107">Result Types</span></span>  
 <span data-ttu-id="bdfa1-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="bdfa1-109">Дополнительные сведения о неявном повышении уровня типов см. в разделе [системы типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdfa1-110">Пример</span><span class="sxs-lookup"><span data-stu-id="bdfa1-110">Example</span></span>  
 <span data-ttu-id="bdfa1-111">Следующий запрос Entity SQL использует арифметический оператор вычитания (-) для вычитания одного числа из другого.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="bdfa1-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bdfa1-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="bdfa1-114">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="bdfa1-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bdfa1-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="bdfa1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bdfa1-116">See Also</span></span>  
 [<span data-ttu-id="bdfa1-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bdfa1-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
