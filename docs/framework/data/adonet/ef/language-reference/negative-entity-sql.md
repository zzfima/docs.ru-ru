---
title: '- (Отрицательное значение) (Язык entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 2ceedd99221047ab73474ad5dc2478e527618b87
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="fbf6b-102">- (отрицательное) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fbf6b-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="fbf6b-103">Возвращает значение числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbf6b-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="fbf6b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fbf6b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="fbf6b-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fbf6b-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="fbf6b-107">Result Types</span></span>  
 <span data-ttu-id="fbf6b-108">Тип данных `expression`.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbf6b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbf6b-109">Remarks</span></span>  
 <span data-ttu-id="fbf6b-110">Если аргумент `expression` имеет тип данных без знака, то типом результата становится тип данных со знаком, который в наибольшей степени связан с типом аргумента `expression`.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="fbf6b-111">Например, если аргумент `expression` имеет тип Byte, то возвращается значение типа Int16.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbf6b-112">Пример</span><span class="sxs-lookup"><span data-stu-id="fbf6b-112">Example</span></span>  
 <span data-ttu-id="fbf6b-113">В следующем запросе Entity SQL используется арифметический оператор «-» для возврата значения числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="fbf6b-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fbf6b-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fbf6b-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="fbf6b-116">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="fbf6b-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="fbf6b-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fbf6b-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="fbf6b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fbf6b-118">See Also</span></span>  
 [<span data-ttu-id="fbf6b-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fbf6b-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
