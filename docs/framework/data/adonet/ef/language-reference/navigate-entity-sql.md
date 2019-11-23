---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 09128a367a02e1f9b206a9cc068987166c76381b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319544"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="19bf6-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="19bf6-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="19bf6-103">Производит переход по связи, установленной между сущностями.</span><span class="sxs-lookup"><span data-stu-id="19bf6-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="19bf6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19bf6-104">Syntax</span></span>

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="19bf6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="19bf6-105">Arguments</span></span>

<span data-ttu-id="19bf6-106">`instance-expression` экземпляр сущности.</span><span class="sxs-lookup"><span data-stu-id="19bf6-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="19bf6-107">`relationship-type` имя типа связи, из CSDL-файла.</span><span class="sxs-lookup"><span data-stu-id="19bf6-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="19bf6-108">`relationship-type` определяется как \<пространства имен >. > имя типа отношения\<.</span><span class="sxs-lookup"><span data-stu-id="19bf6-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="19bf6-109">`to` конец связи.</span><span class="sxs-lookup"><span data-stu-id="19bf6-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="19bf6-110">`from` начала связи.</span><span class="sxs-lookup"><span data-stu-id="19bf6-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="19bf6-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="19bf6-111">Return Value</span></span>

<span data-ttu-id="19bf6-112">Если количество элементов в конечной составляющей связи равно 1, то будет возвращено значение `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="19bf6-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="19bf6-113">Если же количество элементов в конечной составляющей связи равно n, то будет возвращено значение `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="19bf6-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="19bf6-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="19bf6-114">Remarks</span></span>

<span data-ttu-id="19bf6-115">Связи — это конструкции первого класса в EDM (EDM).</span><span class="sxs-lookup"><span data-stu-id="19bf6-115">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="19bf6-116">Связи могут устанавливаться между двумя или несколькими типами сущностей, а пользователи могут переходить по связи от одного элемента (от одной сущности) к другому.</span><span class="sxs-lookup"><span data-stu-id="19bf6-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="19bf6-117">`from` и `to` являются необязательными при том условии, что нет неоднозначности в разрешении имен в пределах связи.</span><span class="sxs-lookup"><span data-stu-id="19bf6-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="19bf6-118">Оператор NAVIGATE является допустимым в пространствах O и C.</span><span class="sxs-lookup"><span data-stu-id="19bf6-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="19bf6-119">Конструкция перехода имеет следующую общую форму.</span><span class="sxs-lookup"><span data-stu-id="19bf6-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="19bf6-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="19bf6-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="19bf6-121">Например:</span><span class="sxs-lookup"><span data-stu-id="19bf6-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="19bf6-122">Здесь OrderCustomer является значением параметра `relationship`, а Customer и Order являются элементами связи `to-end` (customer) и `from-end` (order).</span><span class="sxs-lookup"><span data-stu-id="19bf6-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="19bf6-123">Если Ордеркустомер является отношением n:1, то тип результата выражения Navigate — ref\<> клиента.</span><span class="sxs-lookup"><span data-stu-id="19bf6-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="19bf6-124">Для этого выражение существует следующая упрощенная форма.</span><span class="sxs-lookup"><span data-stu-id="19bf6-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="19bf6-125">Аналогичным образом, в запросе следующей формы выражение Navigate будет создавать коллекцию <\<порядок ссылки > >.</span><span class="sxs-lookup"><span data-stu-id="19bf6-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="19bf6-126">Выражение экземпляра должно иметь тип сущности или ссылки.</span><span class="sxs-lookup"><span data-stu-id="19bf6-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="19bf6-127">Пример</span><span class="sxs-lookup"><span data-stu-id="19bf6-127">Example</span></span>

<span data-ttu-id="19bf6-128">В следующем запросе Entity SQL оператор NAVIGATE используется для перехода по связи, заданной между типами сущностей Address и SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="19bf6-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="19bf6-129">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="19bf6-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="19bf6-130">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="19bf6-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="19bf6-131">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="19bf6-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="19bf6-132">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="19bf6-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a><span data-ttu-id="19bf6-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="19bf6-133">See also</span></span>

- [<span data-ttu-id="19bf6-134">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="19bf6-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="19bf6-135">Руководство. Переход по связям с помощью оператора Navigate</span><span class="sxs-lookup"><span data-stu-id="19bf6-135">How to: Navigate Relationships with Navigate Operator</span></span>](navigate-entity-sql.md)
