---
title: '- (Отрицательное значение) (Язык entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 343f53b2a6fc54a5be6f8673348384567b48262b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102847"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="977ed-102">- (отрицательное) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="977ed-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="977ed-103">Возвращает значение числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="977ed-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="977ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="977ed-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="977ed-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="977ed-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="977ed-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="977ed-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="977ed-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="977ed-107">Result Types</span></span>  
 <span data-ttu-id="977ed-108">Тип данных `expression`.</span><span class="sxs-lookup"><span data-stu-id="977ed-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="977ed-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="977ed-109">Remarks</span></span>  
 <span data-ttu-id="977ed-110">Если аргумент `expression` имеет тип данных без знака, то типом результата становится тип данных со знаком, который в наибольшей степени связан с типом аргумента `expression`.</span><span class="sxs-lookup"><span data-stu-id="977ed-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="977ed-111">Например, если аргумент `expression` имеет тип Byte, то возвращается значение типа Int16.</span><span class="sxs-lookup"><span data-stu-id="977ed-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="977ed-112">Пример</span><span class="sxs-lookup"><span data-stu-id="977ed-112">Example</span></span>  
 <span data-ttu-id="977ed-113">В следующем запросе Entity SQL используется арифметический оператор «-» для возврата значения числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="977ed-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="977ed-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="977ed-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="977ed-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="977ed-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="977ed-116">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="977ed-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="977ed-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="977ed-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="977ed-118">См. также</span><span class="sxs-lookup"><span data-stu-id="977ed-118">See also</span></span>

- [<span data-ttu-id="977ed-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="977ed-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
