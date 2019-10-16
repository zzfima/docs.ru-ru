---
title: + (Объединение строк) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 9c078e193eeecd4d331c5e3c04c66dee2c4a1daa
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319314"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="5fccc-102">+ (объединение строк) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5fccc-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="5fccc-103">Объединяет две строки.</span><span class="sxs-lookup"><span data-stu-id="5fccc-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fccc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fccc-104">Syntax</span></span>  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5fccc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5fccc-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5fccc-106">Любое допустимое выражение с типом данных EDM.String.</span><span class="sxs-lookup"><span data-stu-id="5fccc-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="5fccc-107">Оба выражения должны быть одного типа данных, либо должна иметься возможность неявного преобразования типа данных одного выражения в тип данных другого выражения.</span><span class="sxs-lookup"><span data-stu-id="5fccc-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="5fccc-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="5fccc-108">Result Types</span></span>  
 <span data-ttu-id="5fccc-109">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="5fccc-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="5fccc-110">Дополнительные сведения о неявном повышении типа см. в разделе [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5fccc-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fccc-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5fccc-111">Example</span></span>  
 <span data-ttu-id="5fccc-112">В следующем запросе Entity SQL с помощью оператора «+» объединяются две строки.</span><span class="sxs-lookup"><span data-stu-id="5fccc-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="5fccc-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5fccc-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5fccc-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5fccc-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5fccc-115">Выполните процедуру, описанную в разделе [инструкции. выполнение запроса, возвращающего тип PrimitiveType результаты](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5fccc-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="5fccc-116">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5fccc-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="5fccc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5fccc-117">See also</span></span>

- [<span data-ttu-id="5fccc-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5fccc-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="5fccc-119">Типы концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="5fccc-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
