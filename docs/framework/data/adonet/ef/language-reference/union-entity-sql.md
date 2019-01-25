---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: b7818866571fc362e56e8fdea3344f0888f1a2aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679842"
---
# <a name="union-entity-sql"></a><span data-ttu-id="5110d-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5110d-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="5110d-103">Сводит результаты двух или более запросов в одну коллекцию.</span><span class="sxs-lookup"><span data-stu-id="5110d-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5110d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5110d-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5110d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5110d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5110d-106">Любое допустимое выражение запроса, возвращающее коллекцию для объединения с данной коллекцией. Все выражения должны быть одного типа с параметром `expression`либо базового или производного типа для типа этого параметра.</span><span class="sxs-lookup"><span data-stu-id="5110d-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="5110d-107">UNION</span><span class="sxs-lookup"><span data-stu-id="5110d-107">UNION</span></span>  
 <span data-ttu-id="5110d-108">Указывает на то, что несколько коллекций следует объединить и возвратить в виде единой коллекции.</span><span class="sxs-lookup"><span data-stu-id="5110d-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="5110d-109">ALL</span><span class="sxs-lookup"><span data-stu-id="5110d-109">ALL</span></span>  
 <span data-ttu-id="5110d-110">Указывает на то, что несколько коллекций следует объединить и возвратить в виде единой коллекции, включая повторения.</span><span class="sxs-lookup"><span data-stu-id="5110d-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="5110d-111">Если этот аргумент не указан, то повторения удаляются из итоговой коллекции.</span><span class="sxs-lookup"><span data-stu-id="5110d-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5110d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5110d-112">Return Value</span></span>  
 <span data-ttu-id="5110d-113">Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.</span><span class="sxs-lookup"><span data-stu-id="5110d-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5110d-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="5110d-114">Remarks</span></span>  
 <span data-ttu-id="5110d-115">UNION - это один из операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5110d-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="5110d-116">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="5110d-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="5110d-117">Сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторы работы с наборами, см. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5110d-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5110d-118">Пример</span><span class="sxs-lookup"><span data-stu-id="5110d-118">Example</span></span>  
 <span data-ttu-id="5110d-119">В следующем запросе Entity SQL оператор UNION ALL используется, чтобы объединить результаты двух запросов в единую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="5110d-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="5110d-120">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5110d-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5110d-121">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5110d-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5110d-122">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5110d-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5110d-123">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5110d-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="5110d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5110d-124">See also</span></span>
- [<span data-ttu-id="5110d-125">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5110d-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
