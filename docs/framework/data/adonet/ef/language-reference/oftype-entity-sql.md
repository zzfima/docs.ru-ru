---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: c90950e11cbfca7a49b505c1654d08be504990e1
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46507322"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="5f792-102">OFTYPE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5f792-102">OFTYPE (Entity SQL)</span></span>
<span data-ttu-id="5f792-103">Возвращает коллекцию объектов из выражения запроса, которое относится к заданному типу.</span><span class="sxs-lookup"><span data-stu-id="5f792-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f792-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f792-104">Syntax</span></span>  
  
```  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f792-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5f792-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5f792-106">Любое допустимое выражение запроса, возвращающее коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="5f792-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="5f792-107">Тип, по которому проверяется каждый объект, возвращаемый `expression` .</span><span class="sxs-lookup"><span data-stu-id="5f792-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="5f792-108">Для типа должно быть указано пространство имен.</span><span class="sxs-lookup"><span data-stu-id="5f792-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f792-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5f792-109">Return Value</span></span>  
 <span data-ttu-id="5f792-110">Коллекция объектов, которые имеют тип `test_type`, базовый тип или тип, производный от `test_type`.</span><span class="sxs-lookup"><span data-stu-id="5f792-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="5f792-111">Если задан параметр ONLY, возвращаются только экземпляры `test_type` или пустая коллекция.</span><span class="sxs-lookup"><span data-stu-id="5f792-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f792-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f792-112">Remarks</span></span>  
 <span data-ttu-id="5f792-113">Выражение `OFTYPE` задает выражение с определением типа, которое применяется для проверки типа по отношению к каждому элементу коллекции.</span><span class="sxs-lookup"><span data-stu-id="5f792-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="5f792-114">Выражение `OFTYPE` позволяет получить новую коллекцию указанного типа, содержащую только те элементы, которые были эквивалентны либо этому типу, либо его подтипу.</span><span class="sxs-lookup"><span data-stu-id="5f792-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="5f792-115">Выражение `OFTYPE` представляет собой сокращение следующего выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="5f792-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="5f792-116">Например, если предположить, что тип Manager представляет собой подтип Employee, то следующее выражение позволяет извлечь из коллекции сотрудников данные только менеджеров:</span><span class="sxs-lookup"><span data-stu-id="5f792-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="5f792-117">Можно также выполнить приведение коллекции с помощью фильтра типов:</span><span class="sxs-lookup"><span data-stu-id="5f792-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="5f792-118">Все руководители являются менеджерами компании, поэтому полученная в результате коллекция по-прежнему содержит данные всех руководителей, несмотря на то что теперь по своему типу она рассматривается как коллекция менеджеров.</span><span class="sxs-lookup"><span data-stu-id="5f792-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="5f792-119">В следующей таблице показано поведение оператора `OFTYPE` по отношению к некоторым шаблонам.</span><span class="sxs-lookup"><span data-stu-id="5f792-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="5f792-120">Все исключения активизируются на стороне клиента перед вызовом поставщика.</span><span class="sxs-lookup"><span data-stu-id="5f792-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="5f792-121">Шаблон</span><span class="sxs-lookup"><span data-stu-id="5f792-121">Pattern</span></span>|<span data-ttu-id="5f792-122">Поведение</span><span class="sxs-lookup"><span data-stu-id="5f792-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="5f792-123">OFTYPE(Collection(EntityType), EntityType)</span><span class="sxs-lookup"><span data-stu-id="5f792-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="5f792-124">Collection(EntityType)</span><span class="sxs-lookup"><span data-stu-id="5f792-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="5f792-125">OFTYPE(Collection(ComplexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="5f792-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="5f792-126">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="5f792-126">Throws</span></span>|  
|<span data-ttu-id="5f792-127">OFTYPE(Collection(RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="5f792-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="5f792-128">Активизирует исключение</span><span class="sxs-lookup"><span data-stu-id="5f792-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5f792-129">Пример</span><span class="sxs-lookup"><span data-stu-id="5f792-129">Example</span></span>  
 <span data-ttu-id="5f792-130">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор OFTYPE возвращает коллекцию объектов OnsiteCourse из коллекции объектов Course.</span><span class="sxs-lookup"><span data-stu-id="5f792-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="5f792-131">Запрос основан на [модели School](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="5f792-131">The query is based on the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="5f792-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5f792-132">See Also</span></span>  
 [<span data-ttu-id="5f792-133">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5f792-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
