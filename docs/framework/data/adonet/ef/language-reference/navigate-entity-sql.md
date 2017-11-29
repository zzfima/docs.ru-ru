---
title: NAVIGATE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c82149fb5d76ac7b95198ce2b29550eade54b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="e8aca-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e8aca-102">NAVIGATE (Entity SQL)</span></span>
<span data-ttu-id="e8aca-103">Производит переход по связи, установленной между сущностями.</span><span class="sxs-lookup"><span data-stu-id="e8aca-103">Navigates over the relationship established between entities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8aca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8aca-104">Syntax</span></span>  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a><span data-ttu-id="e8aca-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e8aca-105">Arguments</span></span>  
 `instance-expresssion`  
 <span data-ttu-id="e8aca-106">Экземпляр сущности.</span><span class="sxs-lookup"><span data-stu-id="e8aca-106">An instance of an entity.</span></span>  
  
 `relationship-type`  
 <span data-ttu-id="e8aca-107">Имя типа связи из CSDL-файла.</span><span class="sxs-lookup"><span data-stu-id="e8aca-107">The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="e8aca-108">`relationship-type` Квалифицируется как \<пространство имен >.\< имя_типа_связи >.</span><span class="sxs-lookup"><span data-stu-id="e8aca-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>  
  
 `to`  
 <span data-ttu-id="e8aca-109">Элемент связи.</span><span class="sxs-lookup"><span data-stu-id="e8aca-109">The end of the relationship.</span></span>  
  
 `from`  
 <span data-ttu-id="e8aca-110">Начало связи.</span><span class="sxs-lookup"><span data-stu-id="e8aca-110">The beginning of the relationship.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8aca-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e8aca-111">Return Value</span></span>  
 <span data-ttu-id="e8aca-112">Если количество элементов в конечной составляющей связи равно 1, то будет возвращено значение `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="e8aca-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="e8aca-113">Если же количество элементов в конечной составляющей связи равно n, то будет возвращено значение `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="e8aca-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8aca-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8aca-114">Remarks</span></span>  
 <span data-ttu-id="e8aca-115">Связи являются конструкция первого класса в модели [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8aca-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="e8aca-116">Связи могут устанавливаться между двумя или несколькими типами сущностей, а пользователи могут переходить по связи от одного элемента (от одной сущности) к другому.</span><span class="sxs-lookup"><span data-stu-id="e8aca-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="e8aca-117">`from` и `to` являются необязательными при том условии, что нет неоднозначности в разрешении имен в пределах связи.</span><span class="sxs-lookup"><span data-stu-id="e8aca-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>  
  
 <span data-ttu-id="e8aca-118">Оператор NAVIGATE является допустимым в пространствах O и C.</span><span class="sxs-lookup"><span data-stu-id="e8aca-118">NAVIGATE is valid in O and C space.</span></span>  
  
 <span data-ttu-id="e8aca-119">Конструкция перехода имеет следующую общую форму.</span><span class="sxs-lookup"><span data-stu-id="e8aca-119">The general form of a navigation construct is the following:</span></span>  
  
 <span data-ttu-id="e8aca-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="e8aca-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>  
  
 <span data-ttu-id="e8aca-121">Например:</span><span class="sxs-lookup"><span data-stu-id="e8aca-121">For example:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="e8aca-122">Здесь OrderCustomer является значением параметра `relationship`, а Customer и Order являются элементами связи `to-end` (customer) и `from-end` (order).</span><span class="sxs-lookup"><span data-stu-id="e8aca-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="e8aca-123">Если OrderCustomer был отношения n: 1, то типом результата выражения перехода будет Ref\<клиента >.</span><span class="sxs-lookup"><span data-stu-id="e8aca-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>  
  
 <span data-ttu-id="e8aca-124">Для этого выражение существует следующая упрощенная форма.</span><span class="sxs-lookup"><span data-stu-id="e8aca-124">The simpler form of this expression is the following:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="e8aca-125">Аналогичным образом в запросе следующей формы выражение перехода вернет значение Collection < Ref\<порядок >>.</span><span class="sxs-lookup"><span data-stu-id="e8aca-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 <span data-ttu-id="e8aca-126">Выражение экземпляра должно иметь тип сущности или ссылки.</span><span class="sxs-lookup"><span data-stu-id="e8aca-126">The instance-expression must be an entity/ref type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8aca-127">Пример</span><span class="sxs-lookup"><span data-stu-id="e8aca-127">Example</span></span>  
 <span data-ttu-id="e8aca-128">В следующем запросе Entity SQL оператор NAVIGATE используется для перехода по связи, заданной между типами сущностей Address и SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="e8aca-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="e8aca-129">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e8aca-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e8aca-130">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="e8aca-130">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e8aca-131">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e8aca-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e8aca-132">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e8aca-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a><span data-ttu-id="e8aca-133">См. также</span><span class="sxs-lookup"><span data-stu-id="e8aca-133">See Also</span></span>  
 [<span data-ttu-id="e8aca-134">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e8aca-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="e8aca-135">Как: перейдите связи с помощью оператора Navigate</span><span class="sxs-lookup"><span data-stu-id="e8aca-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
