---
title: (Остаток от деления) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: b08689b6f5b17950738c557e02f995fa85aeb35e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160489"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="5271f-102">(Остаток от деления) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5271f-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="5271f-103">Возвращает остаток от деления значения одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="5271f-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5271f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5271f-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="5271f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5271f-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="5271f-106">Делимое числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="5271f-106">The numeric expression to divide.</span></span> `dividend` <span data-ttu-id="5271f-107">— любое допустимое выражение любого из числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="5271f-107">is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="5271f-108">Числовое выражение, на которое делится делимое.</span><span class="sxs-lookup"><span data-stu-id="5271f-108">The numeric expression to divide the dividend by.</span></span> `divisor` <span data-ttu-id="5271f-109">— любое допустимое выражение любого из числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="5271f-109">is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5271f-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="5271f-110">Result Types</span></span>  
 <span data-ttu-id="5271f-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="5271f-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="5271f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="5271f-112">Example</span></span>  
 <span data-ttu-id="5271f-113">В следующем запросе Entity SQL используется арифметический оператор % для получения остатка от деления одного выражения на другое.</span><span class="sxs-lookup"><span data-stu-id="5271f-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="5271f-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5271f-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5271f-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5271f-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5271f-116">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5271f-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5271f-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5271f-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="5271f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5271f-118">See also</span></span>

- [<span data-ttu-id="5271f-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5271f-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
