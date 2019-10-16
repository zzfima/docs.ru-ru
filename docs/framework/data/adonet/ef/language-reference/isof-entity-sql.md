---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: c4c4cbf74cb17cf43e79c42ff42d1e68122fd534
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319720"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="2bf66-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2bf66-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="2bf66-103">Определяет, относится ли тип выражения к указанному типу или одному из его подтипов.</span><span class="sxs-lookup"><span data-stu-id="2bf66-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bf66-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="2bf66-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2bf66-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2bf66-106">Любое допустимое выражение запроса для определения типа.</span><span class="sxs-lookup"><span data-stu-id="2bf66-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="2bf66-107">NOT</span><span class="sxs-lookup"><span data-stu-id="2bf66-107">NOT</span></span>  
 <span data-ttu-id="2bf66-108">Выполняет отрицание результата EDM.Boolean для IS OF.</span><span class="sxs-lookup"><span data-stu-id="2bf66-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="2bf66-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="2bf66-109">ONLY</span></span>  
 <span data-ttu-id="2bf66-110">Указывает, что оператор IS OF возвращает значение `true` только в том случае, если выражение `expression` относится к типу `type`, а не одному из его подтипов.</span><span class="sxs-lookup"><span data-stu-id="2bf66-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="2bf66-111">Тип, по которому проверяется выражение `expression`.</span><span class="sxs-lookup"><span data-stu-id="2bf66-111">The type to test `expression` against.</span></span> <span data-ttu-id="2bf66-112">Для типа должно быть указано пространство имен.</span><span class="sxs-lookup"><span data-stu-id="2bf66-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bf66-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2bf66-113">Return Value</span></span>  
 <span data-ttu-id="2bf66-114">Значение `true`, если выражение `expression` относится к типу T, который является либо базовым типом, либо производным типом от типа `type`. Значение null, если выражение `expression` во время выполнения имеет значение null. В противном случае - значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2bf66-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bf66-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="2bf66-115">Remarks</span></span>  
 <span data-ttu-id="2bf66-116">Выражения `expression IS NOT OF (type)` и `expression IS NOT OF (ONLY type)` являются синтаксически эквивалентными для `NOT (expression IS OF (type))` и `NOT (expression IS OF (ONLY type))` соответственно.</span><span class="sxs-lookup"><span data-stu-id="2bf66-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="2bf66-117">В следующей таблице показано, каким образом оператор `IS OF` работает с некоторыми стандартными и нестандартными конструкциями.</span><span class="sxs-lookup"><span data-stu-id="2bf66-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="2bf66-118">Все исключения формируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="2bf66-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="2bf66-119">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2bf66-119">Pattern</span></span>|<span data-ttu-id="2bf66-120">Поведение</span><span class="sxs-lookup"><span data-stu-id="2bf66-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="2bf66-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="2bf66-122">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="2bf66-122">Throws</span></span>|  
|<span data-ttu-id="2bf66-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="2bf66-124">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="2bf66-124">Throws</span></span>|  
|<span data-ttu-id="2bf66-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-125">null IS OF (RowType)</span></span>|<span data-ttu-id="2bf66-126">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="2bf66-126">Throws</span></span>|  
|<span data-ttu-id="2bf66-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="2bf66-128">Возвращает DBNull</span><span class="sxs-lookup"><span data-stu-id="2bf66-128">Returns DBNull</span></span>|  
|<span data-ttu-id="2bf66-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="2bf66-130">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="2bf66-130">Throws</span></span>|  
|<span data-ttu-id="2bf66-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="2bf66-132">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="2bf66-132">Throws</span></span>|  
|<span data-ttu-id="2bf66-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="2bf66-134">Возвращает значение true или false</span><span class="sxs-lookup"><span data-stu-id="2bf66-134">Returns true/false</span></span>|  
|<span data-ttu-id="2bf66-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="2bf66-136">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="2bf66-136">Throws</span></span>|  
|<span data-ttu-id="2bf66-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="2bf66-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="2bf66-138">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="2bf66-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2bf66-139">Пример</span><span class="sxs-lookup"><span data-stu-id="2bf66-139">Example</span></span>  
 <span data-ttu-id="2bf66-140">Следующий запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] использует оператор IS OF для определения типа выражения запроса, а затем использует оператор TREAT для преобразования объекта курса типа в коллекцию объектов типа OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="2bf66-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="2bf66-141">Запрос основан на [модели School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2bf66-141">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 <span data-ttu-id="2bf66-142">[! code-SQL [DP Ентитисервицес основные понятия # TREAT_ISOF] ~/samples/snippets/tsql/VS_Snippets_Data/dp ентитисервицес основные понятия/TSQL/ентитискл. SQL # TREAT_ISOF)]</span><span class="sxs-lookup"><span data-stu-id="2bf66-142">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf66-143">См. также</span><span class="sxs-lookup"><span data-stu-id="2bf66-143">See also</span></span>

- [<span data-ttu-id="2bf66-144">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2bf66-144">Entity SQL Reference</span></span>](entity-sql-reference.md)
