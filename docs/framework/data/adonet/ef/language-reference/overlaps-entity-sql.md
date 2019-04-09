---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: 74399c4c5701fcf039666ef3de19de2cf9a6b50e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104212"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="073a9-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="073a9-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="073a9-103">Определяет, содержат ли две коллекции общие элементы.</span><span class="sxs-lookup"><span data-stu-id="073a9-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="073a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="073a9-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="073a9-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="073a9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="073a9-106">Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса.</span><span class="sxs-lookup"><span data-stu-id="073a9-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="073a9-107">Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="073a9-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="073a9-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="073a9-108">Return Value</span></span>  
 `true` <span data-ttu-id="073a9-109">Если две коллекции содержат общие элементы; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="073a9-109">if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="073a9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="073a9-110">Remarks</span></span>  
 <span data-ttu-id="073a9-111">OVERLAPS функционально эквивалентен следующее:</span><span class="sxs-lookup"><span data-stu-id="073a9-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="073a9-112">Оператор OVERLAPS - это один из операторов работы с наборами в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="073a9-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="073a9-113">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="073a9-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="073a9-114">Сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторы работы с наборами, см. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="073a9-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="073a9-115">Пример</span><span class="sxs-lookup"><span data-stu-id="073a9-115">Example</span></span>  
 <span data-ttu-id="073a9-116">В следующем запросе Entity SQL оператор OVERLAPS используется для определения, имеют ли две коллекции общее значение.</span><span class="sxs-lookup"><span data-stu-id="073a9-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="073a9-117">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="073a9-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="073a9-118">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="073a9-118">To compile and run this, follow these steps:</span></span>  
  
1.  <span data-ttu-id="073a9-119">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="073a9-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="073a9-120">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="073a9-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="073a9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="073a9-121">See also</span></span>

- [<span data-ttu-id="073a9-122">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="073a9-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
