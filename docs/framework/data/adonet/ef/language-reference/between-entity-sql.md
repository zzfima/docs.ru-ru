---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: a0f5dd19c439861451b1e88c3ae35f9f265288fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150497"
---
# <a name="between-entity-sql"></a><span data-ttu-id="bda38-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bda38-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="bda38-103">Определяет, находится ли значение выражения в указанном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="bda38-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="bda38-104">Выражение [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN имеет ту же функциональность, что и выражение Transact-S'L BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="bda38-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda38-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bda38-105">Syntax</span></span>  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression
```  
  
## <a name="arguments"></a><span data-ttu-id="bda38-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="bda38-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bda38-107">Любое допустимое выражение для проверки на принадлежность диапазону в пределах от `begin_expression` до `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="bda38-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="bda38-108">Аргумент `expression` должен быть того же типа данных, что и аргументы `begin_expression` и `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="bda38-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="bda38-109">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="bda38-109">Any valid expression.</span></span> <span data-ttu-id="bda38-110">Аргумент `begin_expression` должен быть того же типа данных, что и аргументы `expression` и `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="bda38-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="bda38-111">Значение `begin_expression` должно быть меньше `end_expression`, иначе возвращаемое значение будет инвертировано.</span><span class="sxs-lookup"><span data-stu-id="bda38-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="bda38-112">Любое допустимое выражение.</span><span class="sxs-lookup"><span data-stu-id="bda38-112">Any valid expression.</span></span> <span data-ttu-id="bda38-113">Аргумент `end_expression` должен быть того же типа данных, что и аргументы `expression` и `begin_expression`.</span><span class="sxs-lookup"><span data-stu-id="bda38-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="bda38-114">NOT</span><span class="sxs-lookup"><span data-stu-id="bda38-114">NOT</span></span>  
 <span data-ttu-id="bda38-115">Указывает, что результат оператора BETWEEN должен быть инвертирован.</span><span class="sxs-lookup"><span data-stu-id="bda38-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="bda38-116">AND</span><span class="sxs-lookup"><span data-stu-id="bda38-116">AND</span></span>  
 <span data-ttu-id="bda38-117">Играет роль местозаполнителя и указывает на то, что значение выражения `expression` должно находиться в пределах заданных значений аргументов `begin_expression` и `end_expression`.</span><span class="sxs-lookup"><span data-stu-id="bda38-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bda38-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bda38-118">Return Value</span></span>  
 <span data-ttu-id="bda38-119">Значение `true`, если аргумент `expression` находится в диапазоне между `begin_expression` и `end_expression`; в противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="bda38-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="bda38-120">Возвращает `null`, если `expression` равно `null` или если `begin_expression` или `end_expression` равно `null`.</span><span class="sxs-lookup"><span data-stu-id="bda38-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bda38-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="bda38-121">Remarks</span></span>  
 <span data-ttu-id="bda38-122">Чтобы указать эксклюзивный диапазон, используйте больше, чем (>) и меньше, чем (<) операторов вместо BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="bda38-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bda38-123">Пример</span><span class="sxs-lookup"><span data-stu-id="bda38-123">Example</span></span>  
 <span data-ttu-id="bda38-124">В следующем запросе Entity SQL оператор BETWEEN определяет, входит ли значение выражения в указанный диапазон.</span><span class="sxs-lookup"><span data-stu-id="bda38-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="bda38-125">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="bda38-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bda38-126">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="bda38-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bda38-127">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="bda38-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bda38-128">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="bda38-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="bda38-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bda38-129">See also</span></span>

- [<span data-ttu-id="bda38-130">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bda38-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
