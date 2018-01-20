---
title: "+ (Объединение строк) (Язык entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 24591b54af97eaad705e4914764c7b2c21e5ed0e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="16f7b-102">+ (объединение строк) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="16f7b-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="16f7b-103">Объединяет две строки.</span><span class="sxs-lookup"><span data-stu-id="16f7b-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16f7b-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="16f7b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="16f7b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="16f7b-106">Любое допустимое выражение с типом данных EDM.String.</span><span class="sxs-lookup"><span data-stu-id="16f7b-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="16f7b-107">Оба выражения должны быть одного типа данных, либо должна иметься возможность неявного преобразования типа данных одного выражения в тип данных другого выражения.</span><span class="sxs-lookup"><span data-stu-id="16f7b-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="16f7b-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="16f7b-108">Result Types</span></span>  
 <span data-ttu-id="16f7b-109">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="16f7b-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="16f7b-110">Дополнительные сведения о неявном повышении уровня типов см. в разделе [системы типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="16f7b-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16f7b-111">Пример</span><span class="sxs-lookup"><span data-stu-id="16f7b-111">Example</span></span>  
 <span data-ttu-id="16f7b-112">В следующем запросе Entity SQL с помощью оператора «+» объединяются две строки.</span><span class="sxs-lookup"><span data-stu-id="16f7b-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="16f7b-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="16f7b-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="16f7b-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="16f7b-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="16f7b-115">Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="16f7b-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="16f7b-116">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="16f7b-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="16f7b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="16f7b-117">See Also</span></span>  
 [<span data-ttu-id="16f7b-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="16f7b-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="16f7b-119">Типы концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="16f7b-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
