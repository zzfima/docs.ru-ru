---
title: '|| (ИЛИ) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: d089bcec56ff13ddcd5250a63aee6a00d0c3ef11
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297802"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="1d26b-102">|| (ИЛИ) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1d26b-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="1d26b-103">Объединяет два выражения типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="1d26b-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d26b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d26b-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1d26b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1d26b-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="1d26b-106">Любое допустимое выражение, возвращающее значение типа `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="1d26b-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d26b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d26b-107">Return Value</span></span>  
 `true` <span data-ttu-id="1d26b-108">Если любое из условий равно `true`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="1d26b-108">when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d26b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d26b-109">Remarks</span></span>  
 <span data-ttu-id="1d26b-110">OR - это логический оператор [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d26b-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="1d26b-111">Он используется только для объединения двух условий.</span><span class="sxs-lookup"><span data-stu-id="1d26b-111">It is used to combine two conditions.</span></span> <span data-ttu-id="1d26b-112">Если в инструкции используется более одного логического оператора, операторы OR вычисляются после операторов AND.</span><span class="sxs-lookup"><span data-stu-id="1d26b-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="1d26b-113">Однако порядок выполнения можно изменить с помощью скобок.</span><span class="sxs-lookup"><span data-stu-id="1d26b-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="1d26b-114">Двойная вертикальная черта (&#124;&#124;) имеют ту же функциональность, что и оператор OR.</span><span class="sxs-lookup"><span data-stu-id="1d26b-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="1d26b-115">В следующей таблице указаны возможные входные значения и возвращаемые типы.</span><span class="sxs-lookup"><span data-stu-id="1d26b-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="1d26b-116">true</span><span class="sxs-lookup"><span data-stu-id="1d26b-116">TRUE</span></span>|<span data-ttu-id="1d26b-117">true</span><span class="sxs-lookup"><span data-stu-id="1d26b-117">TRUE</span></span>|<span data-ttu-id="1d26b-118">true</span><span class="sxs-lookup"><span data-stu-id="1d26b-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="1d26b-119">true</span><span class="sxs-lookup"><span data-stu-id="1d26b-119">TRUE</span></span>|<span data-ttu-id="1d26b-120">false</span><span class="sxs-lookup"><span data-stu-id="1d26b-120">FALSE</span></span>|<span data-ttu-id="1d26b-121">NULL</span><span class="sxs-lookup"><span data-stu-id="1d26b-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="1d26b-122">true</span><span class="sxs-lookup"><span data-stu-id="1d26b-122">TRUE</span></span>|<span data-ttu-id="1d26b-123">NULL</span><span class="sxs-lookup"><span data-stu-id="1d26b-123">NULL</span></span>|<span data-ttu-id="1d26b-124">NULL</span><span class="sxs-lookup"><span data-stu-id="1d26b-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d26b-125">Пример</span><span class="sxs-lookup"><span data-stu-id="1d26b-125">Example</span></span>  
 <span data-ttu-id="1d26b-126">Следующий запрос Entity SQL использует оператор OR, чтобы объединить два выражения типа `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="1d26b-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="1d26b-127">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1d26b-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1d26b-128">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="1d26b-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1d26b-129">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1d26b-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1d26b-130">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1d26b-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="1d26b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="1d26b-131">See also</span></span>

- [<span data-ttu-id="1d26b-132">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1d26b-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
