---
title: + (Объединение строк) (Язык entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 8a1785d590c5f7fcc443856180d516bb40cfc28e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500884"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="24df4-102">+ (объединение строк) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="24df4-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="24df4-103">Объединяет две строки.</span><span class="sxs-lookup"><span data-stu-id="24df4-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24df4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24df4-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="24df4-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="24df4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="24df4-106">Любое допустимое выражение с типом данных EDM.String.</span><span class="sxs-lookup"><span data-stu-id="24df4-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="24df4-107">Оба выражения должны быть одного типа данных, либо должна иметься возможность неявного преобразования типа данных одного выражения в тип данных другого выражения.</span><span class="sxs-lookup"><span data-stu-id="24df4-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="24df4-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="24df4-108">Result Types</span></span>  
 <span data-ttu-id="24df4-109">Тип данных, который является результатом неявного повышения типов обоих аргументов.</span><span class="sxs-lookup"><span data-stu-id="24df4-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="24df4-110">Дополнительные сведения о неявном повышении уровня типов, см. в разделе [система типов](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="24df4-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24df4-111">Пример</span><span class="sxs-lookup"><span data-stu-id="24df4-111">Example</span></span>  
 <span data-ttu-id="24df4-112">В следующем запросе Entity SQL с помощью оператора «+» объединяются две строки.</span><span class="sxs-lookup"><span data-stu-id="24df4-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="24df4-113">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="24df4-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="24df4-114">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="24df4-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="24df4-115">Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="24df4-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="24df4-116">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="24df4-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="24df4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="24df4-117">See Also</span></span>  
 [<span data-ttu-id="24df4-118">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="24df4-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="24df4-119">Типы концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="24df4-119">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
