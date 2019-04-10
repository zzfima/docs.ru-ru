---
title: < (Меньше) (язык Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 1ca1cbdf1282782295b659393e8f54aae3ec5649
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320448"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="b27fb-102">\< (меньше) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b27fb-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="b27fb-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.</span><span class="sxs-lookup"><span data-stu-id="b27fb-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b27fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b27fb-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b27fb-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b27fb-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b27fb-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="b27fb-106">Any valid expression.</span></span> <span data-ttu-id="b27fb-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="b27fb-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b27fb-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="b27fb-108">Result Types</span></span>  
 `true` <span data-ttu-id="b27fb-109">Если левое выражение значение меньше правого выражения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="b27fb-109">if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b27fb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b27fb-110">Example</span></span>  
 <span data-ttu-id="b27fb-111">В следующем запросе Entity SQL оператор < используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого.</span><span class="sxs-lookup"><span data-stu-id="b27fb-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="b27fb-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b27fb-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b27fb-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="b27fb-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b27fb-114">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b27fb-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b27fb-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b27fb-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="b27fb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b27fb-116">See also</span></span>

- [<span data-ttu-id="b27fb-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b27fb-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
