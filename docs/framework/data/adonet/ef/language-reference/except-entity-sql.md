---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: 32b5148e43a38e5cf8dcce0ae16260d7a6b6a018
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341222"
---
# <a name="except-entity-sql"></a><span data-ttu-id="3e8af-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3e8af-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="3e8af-103">Возвращает коллекцию различных значений из выражения запроса, расположенного левее операнда EXCEPT, за исключением тех, которые были возвращены выражением запроса, расположенного правее операнда EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="3e8af-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="3e8af-104">Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="3e8af-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8af-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e8af-105">Syntax</span></span>  
  
```  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e8af-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3e8af-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3e8af-107">Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса.</span><span class="sxs-lookup"><span data-stu-id="3e8af-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e8af-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e8af-108">Return Value</span></span>  
 <span data-ttu-id="3e8af-109">Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.</span><span class="sxs-lookup"><span data-stu-id="3e8af-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e8af-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e8af-110">Remarks</span></span>  
 <span data-ttu-id="3e8af-111">Оператор EXCEPT - это один из операторов работы с наборами в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e8af-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="3e8af-112">Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="3e8af-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="3e8af-113">Следующая таблица демонстрирует очередность операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e8af-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="3e8af-114">Приоритет</span><span class="sxs-lookup"><span data-stu-id="3e8af-114">Precedence</span></span>|<span data-ttu-id="3e8af-115">Операторы</span><span class="sxs-lookup"><span data-stu-id="3e8af-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="3e8af-116">Наивысшая</span><span class="sxs-lookup"><span data-stu-id="3e8af-116">Highest</span></span>|<span data-ttu-id="3e8af-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="3e8af-117">INTERSECT</span></span>|  
||<span data-ttu-id="3e8af-118">UNION</span><span class="sxs-lookup"><span data-stu-id="3e8af-118">UNION</span></span><br /><br /> <span data-ttu-id="3e8af-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="3e8af-119">UNION ALL</span></span>|  
||<span data-ttu-id="3e8af-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="3e8af-120">EXCEPT</span></span>|  
|<span data-ttu-id="3e8af-121">Наименьшая</span><span class="sxs-lookup"><span data-stu-id="3e8af-121">Lowest</span></span>|<span data-ttu-id="3e8af-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="3e8af-122">EXISTS</span></span><br /><br /> <span data-ttu-id="3e8af-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="3e8af-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="3e8af-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="3e8af-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="3e8af-125">SET</span><span class="sxs-lookup"><span data-stu-id="3e8af-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3e8af-126">Пример</span><span class="sxs-lookup"><span data-stu-id="3e8af-126">Example</span></span>  
 <span data-ttu-id="3e8af-127">В следующем запросе Entity SQL с помощью оператора EXCEPT возвращается коллекция отдельных значений из двух выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="3e8af-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="3e8af-128">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3e8af-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3e8af-129">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="3e8af-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3e8af-130">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3e8af-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3e8af-131">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3e8af-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## <a name="see-also"></a><span data-ttu-id="3e8af-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3e8af-132">See also</span></span>

- [<span data-ttu-id="3e8af-133">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3e8af-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
