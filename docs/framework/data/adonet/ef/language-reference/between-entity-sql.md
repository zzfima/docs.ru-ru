---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225265"
---
# <a name="between-entity-sql"></a><span data-ttu-id="4a6ba-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4a6ba-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="4a6ba-103">Определяет, находится ли значение выражения в указанном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="4a6ba-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] Выражение BETWEEN имеет ту же функциональность, что и выражение Transact-SQL BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6ba-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a6ba-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="4a6ba-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4a6ba-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="4a6ba-107">Любое допустимое выражение для проверки на принадлежность диапазону в пределах от `begin_expression` до `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> `expression` <span data-ttu-id="4a6ba-108">должен быть тот же тип, что и `begin_expression` и `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-108">must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="4a6ba-109">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-109">Any valid expression.</span></span> `begin_expression` <span data-ttu-id="4a6ba-110">должен быть тот же тип, что и `expression` и `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-110">must be the same type as both `expression` and `end_expression`.</span></span> `begin_expression` <span data-ttu-id="4a6ba-111">должно быть меньше, чем `end_expression`, в противном случае возвращаемое значение будет инвертировано.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-111">should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="4a6ba-112">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-112">Any valid expression.</span></span> `end_expression` <span data-ttu-id="4a6ba-113">должен быть тот же тип, что и `expression` и `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-113">must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="4a6ba-114">NOT</span><span class="sxs-lookup"><span data-stu-id="4a6ba-114">NOT</span></span>  
 <span data-ttu-id="4a6ba-115">Указывает, что результат оператора BETWEEN должен быть инвертирован.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="4a6ba-116">AND</span><span class="sxs-lookup"><span data-stu-id="4a6ba-116">AND</span></span>  
 <span data-ttu-id="4a6ba-117">Играет роль местозаполнителя и указывает на то, что значение выражения `expression` должно находиться в пределах заданных значений аргументов `begin_expression` и `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a6ba-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a6ba-118">Return Value</span></span>  
 `true` <span data-ttu-id="4a6ba-119">Если `expression` между диапазона, обозначенного `begin_expression` и `end_expression`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-119">if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> `null` <span data-ttu-id="4a6ba-120">Если будет возвращаться `expression` — `null` или, если `begin_expression` или `end_expression` является `null`.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-120">will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a6ba-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a6ba-121">Remarks</span></span>  
 <span data-ttu-id="4a6ba-122">Для указания исключающего диапазона, используйте больше (>) и меньше, чем операторы (<) вместо BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a6ba-123">Пример</span><span class="sxs-lookup"><span data-stu-id="4a6ba-123">Example</span></span>  
 <span data-ttu-id="4a6ba-124">В следующем запросе Entity SQL оператор BETWEEN определяет, входит ли значение выражения в указанный диапазон.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="4a6ba-125">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4a6ba-126">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4a6ba-126">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4a6ba-127">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="4a6ba-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="4a6ba-128">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="4a6ba-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="4a6ba-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4a6ba-129">See also</span></span>

- [<span data-ttu-id="4a6ba-130">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4a6ba-130">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
