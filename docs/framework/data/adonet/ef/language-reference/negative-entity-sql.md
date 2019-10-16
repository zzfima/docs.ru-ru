---
title: '- Отрицатель (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 7716b9115587a873531be9c14b7da93c7a148ed8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319535"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="6a1f0-102">- (отрицательное) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6a1f0-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="6a1f0-103">Возвращает значение числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a1f0-104">Syntax</span></span>  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6a1f0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6a1f0-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6a1f0-106">Любое допустимое выражение с любым числовым типом данных.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6a1f0-107">Типы результата</span><span class="sxs-lookup"><span data-stu-id="6a1f0-107">Result Types</span></span>  
 <span data-ttu-id="6a1f0-108">Тип данных `expression`.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a1f0-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6a1f0-109">Remarks</span></span>  
 <span data-ttu-id="6a1f0-110">Если аргумент `expression` имеет тип данных без знака, то типом результата становится тип данных со знаком, который в наибольшей степени связан с типом аргумента `expression`.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="6a1f0-111">Например, если аргумент `expression` имеет тип Byte, то возвращается значение типа Int16.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a1f0-112">Пример</span><span class="sxs-lookup"><span data-stu-id="6a1f0-112">Example</span></span>  
 <span data-ttu-id="6a1f0-113">В следующем запросе Entity SQL используется арифметический оператор «-» для возврата значения числового выражения с противоположным знаком.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="6a1f0-114">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6a1f0-115">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="6a1f0-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6a1f0-116">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6a1f0-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6a1f0-117">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6a1f0-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="6a1f0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6a1f0-118">See also</span></span>

- [<span data-ttu-id="6a1f0-119">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6a1f0-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
