---
title: < (Меньше) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: fb3f4a1c6bc0df6af3c27836f7b53b2701776366
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319692"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="fd814-102">\< (меньше) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fd814-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="fd814-103">Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.</span><span class="sxs-lookup"><span data-stu-id="fd814-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd814-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd814-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="fd814-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fd814-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="fd814-106">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="fd814-106">Any valid expression.</span></span> <span data-ttu-id="fd814-107">Оба выражения должны иметь типы данных, допускающих неявное преобразование.</span><span class="sxs-lookup"><span data-stu-id="fd814-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="fd814-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="fd814-108">Result Types</span></span>  
 <span data-ttu-id="fd814-109">`true` , если значение левого выражения меньше, чем правого; в противном случае - `false`.</span><span class="sxs-lookup"><span data-stu-id="fd814-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd814-110">Пример</span><span class="sxs-lookup"><span data-stu-id="fd814-110">Example</span></span>  
 <span data-ttu-id="fd814-111">В следующем запросе Entity SQL оператор < используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого.</span><span class="sxs-lookup"><span data-stu-id="fd814-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="fd814-112">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="fd814-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="fd814-113">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="fd814-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="fd814-114">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="fd814-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="fd814-115">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="fd814-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="fd814-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fd814-116">See also</span></span>

- [<span data-ttu-id="fd814-117">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fd814-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
