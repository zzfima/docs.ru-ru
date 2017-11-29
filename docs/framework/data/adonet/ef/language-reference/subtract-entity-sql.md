---
title: "- (Вычитание) (Язык entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 07921151309486617312a76285eea7be54463d4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="8e3ae-102">- (вычитание) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8e3ae-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="8e3ae-103">Вычитает одно число из другого.</span><span class="sxs-lookup"><span data-stu-id="8e3ae-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e3ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e3ae-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e3ae-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8e3ae-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8e3ae-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="8e3ae-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8e3ae-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="8e3ae-107">Result Types</span></span>  
 <span data-ttu-id="8e3ae-108">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="8e3ae-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="8e3ae-109">Дополнительные сведения о неявном повышении уровня типов см. в разделе [системы типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8e3ae-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e3ae-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8e3ae-110">Example</span></span>  
 <span data-ttu-id="8e3ae-111">Следующий запрос Entity SQL использует арифметический оператор вычитания (-) для вычитания одного числа из другого.</span><span class="sxs-lookup"><span data-stu-id="8e3ae-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="8e3ae-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="8e3ae-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8e3ae-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="8e3ae-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8e3ae-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8e3ae-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="8e3ae-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8e3ae-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="8e3ae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8e3ae-116">See Also</span></span>  
 [<span data-ttu-id="8e3ae-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8e3ae-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
