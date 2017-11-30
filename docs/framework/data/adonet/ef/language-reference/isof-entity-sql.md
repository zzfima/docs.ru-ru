---
title: ISOF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 980256f4a1f2ef2055d46ead6c89b60650f4cdfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isof-entity-sql"></a><span data-ttu-id="51f82-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="51f82-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="51f82-103">Определяет, относится ли тип выражения к указанному типу или одному из его подтипов.</span><span class="sxs-lookup"><span data-stu-id="51f82-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51f82-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="51f82-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="51f82-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="51f82-106">Любое допустимое выражение запроса для определения типа.</span><span class="sxs-lookup"><span data-stu-id="51f82-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="51f82-107">NOT</span><span class="sxs-lookup"><span data-stu-id="51f82-107">NOT</span></span>  
 <span data-ttu-id="51f82-108">Выполняет отрицание результата EDM.Boolean для IS OF.</span><span class="sxs-lookup"><span data-stu-id="51f82-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="51f82-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="51f82-109">ONLY</span></span>  
 <span data-ttu-id="51f82-110">Указывает, что оператор IS OF возвращает значение `true` только в том случае, если выражение `expression` относится к типу `type`, а не одному из его подтипов.</span><span class="sxs-lookup"><span data-stu-id="51f82-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="51f82-111">Тип, по которому проверяется выражение `expression`.</span><span class="sxs-lookup"><span data-stu-id="51f82-111">The type to test `expression` against.</span></span> <span data-ttu-id="51f82-112">Для типа должно быть указано пространство имен.</span><span class="sxs-lookup"><span data-stu-id="51f82-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51f82-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51f82-113">Return Value</span></span>  
 <span data-ttu-id="51f82-114">Значение `true`, если выражение `expression` относится к типу T, который является либо базовым типом, либо производным типом от типа `type`. Значение null, если выражение `expression` во время выполнения имеет значение null. В противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="51f82-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51f82-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="51f82-115">Remarks</span></span>  
 <span data-ttu-id="51f82-116">Выражения `expression IS NOT OF (type)` и `expression IS NOT OF (ONLY type)` синтаксически эквивалентных `NOT (expression IS OF (type))` и `NOT (expression IS OF (ONLY type))`соответственно.</span><span class="sxs-lookup"><span data-stu-id="51f82-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="51f82-117">В следующей таблице показано, каким образом оператор `IS OF` работает с некоторыми стандартными и нестандартными конструкциями.</span><span class="sxs-lookup"><span data-stu-id="51f82-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="51f82-118">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="51f82-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="51f82-119">Шаблон</span><span class="sxs-lookup"><span data-stu-id="51f82-119">Pattern</span></span>|<span data-ttu-id="51f82-120">Поведение</span><span class="sxs-lookup"><span data-stu-id="51f82-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="51f82-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="51f82-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="51f82-122">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="51f82-122">Throws</span></span>|  
|<span data-ttu-id="51f82-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="51f82-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="51f82-124">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="51f82-124">Throws</span></span>|  
|<span data-ttu-id="51f82-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="51f82-125">null IS OF (RowType)</span></span>|<span data-ttu-id="51f82-126">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="51f82-126">Throws</span></span>|  
|<span data-ttu-id="51f82-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="51f82-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="51f82-128">Возвращает DBNull</span><span class="sxs-lookup"><span data-stu-id="51f82-128">Returns DBNull</span></span>|  
|<span data-ttu-id="51f82-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="51f82-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="51f82-130">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="51f82-130">Throws</span></span>|  
|<span data-ttu-id="51f82-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="51f82-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="51f82-132">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="51f82-132">Throws</span></span>|  
|<span data-ttu-id="51f82-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="51f82-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="51f82-134">Возвращает значение true или false</span><span class="sxs-lookup"><span data-stu-id="51f82-134">Returns true/false</span></span>|  
|<span data-ttu-id="51f82-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="51f82-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="51f82-136">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="51f82-136">Throws</span></span>|  
|<span data-ttu-id="51f82-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="51f82-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="51f82-138">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="51f82-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51f82-139">Пример</span><span class="sxs-lookup"><span data-stu-id="51f82-139">Example</span></span>  
 <span data-ttu-id="51f82-140">Следующие [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запроса оператор IS OF используется для определения типа выражения запроса, а затем оператор TREAT преобразует объект типа Course в коллекцию объектов типа OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="51f82-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="51f82-141">Запрос основан на [модели School](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="51f82-141">The query is based on the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="51f82-142">См. также</span><span class="sxs-lookup"><span data-stu-id="51f82-142">See Also</span></span>  
 [<span data-ttu-id="51f82-143">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="51f82-143">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
