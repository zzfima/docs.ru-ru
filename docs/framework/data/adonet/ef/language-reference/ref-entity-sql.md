---
title: REF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 226a14daa706f6cf0481b752fa03dc95db3eff81
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="ref-entity-sql"></a><span data-ttu-id="f1a4e-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f1a4e-102">REF (Entity SQL)</span></span>
<span data-ttu-id="f1a4e-103">Возвращает ссылку на экземпляр сущности.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a4e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1a4e-104">Syntax</span></span>  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a><span data-ttu-id="f1a4e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f1a4e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f1a4e-106">Любое допустимое выражение, результатом которого является экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1a4e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1a4e-107">Return Value</span></span>  
 <span data-ttu-id="f1a4e-108">Ссылка на указанный экземпляр сущности.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1a4e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1a4e-109">Remarks</span></span>  
 <span data-ttu-id="f1a4e-110">Ссылка на сущность состоит из ключа сущности и имени набора сущности.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="f1a4e-111">На одном и том же типе сущности могут быть основаны разные наборы сущностей, поэтому какой-то конкретный ключ сущности может появляться в нескольких наборах сущностей.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="f1a4e-112">Но ссылка на сущность всегда является уникальной.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="f1a4e-113">Если входное выражение представляет сохраняемую сущность, то будет возвращена ссылка на эту сущность.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="f1a4e-114">Если входное выражение не является сохраняемой сущностью, то возвращается ссылка null.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="f1a4e-115">Если доступ к свойству сущности производится через оператор получения свойства (.), то ссылка автоматически разыменовывается.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1a4e-116">Пример</span><span class="sxs-lookup"><span data-stu-id="f1a4e-116">Example</span></span>  
 <span data-ttu-id="f1a4e-117">В следующем запросе Entity SQL используется оператор REF в целях получения ссылки для входного аргумента сущности.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="f1a4e-118">Тот же запрос разыменовывает ссылку, поскольку для доступа к свойству сущности Product используется оператор получения свойства (.).</span><span class="sxs-lookup"><span data-stu-id="f1a4e-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="f1a4e-119">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f1a4e-120">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f1a4e-120">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="f1a4e-121">Выполните процедуру, описанную в [как: выполнение запроса, возвращает результаты PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f1a4e-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="f1a4e-122">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f1a4e-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="f1a4e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a4e-123">See Also</span></span>  
 [<span data-ttu-id="f1a4e-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="f1a4e-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="f1a4e-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="f1a4e-125">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="f1a4e-126">KEY</span><span class="sxs-lookup"><span data-stu-id="f1a4e-126">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="f1a4e-127">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f1a4e-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="f1a4e-128">Определения типов</span><span class="sxs-lookup"><span data-stu-id="f1a4e-128">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
