---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 40a5afd7eb99dba7cae8fe14ed0a45213fda94a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149951"
---
# <a name="ref-entity-sql"></a><span data-ttu-id="2f9a7-102">REF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2f9a7-102">REF (Entity SQL)</span></span>
<span data-ttu-id="2f9a7-103">Возвращает ссылку на экземпляр сущности.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-103">Returns a reference to an entity instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f9a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f9a7-104">Syntax</span></span>  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a><span data-ttu-id="2f9a7-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2f9a7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2f9a7-106">Любое допустимое выражение, результатом которого является экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-106">Any valid expression that yields an instance of an entity type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f9a7-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f9a7-107">Return Value</span></span>  
 <span data-ttu-id="2f9a7-108">Ссылка на указанный экземпляр сущности.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-108">A reference to the specified entity instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f9a7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f9a7-109">Remarks</span></span>  
 <span data-ttu-id="2f9a7-110">Ссылка на сущность состоит из ключа сущности и имени набора сущности.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-110">An entity reference consists of the entity key and an entity set name.</span></span> <span data-ttu-id="2f9a7-111">На одном и том же типе сущности могут быть основаны разные наборы сущностей, поэтому какой-то конкретный ключ сущности может появляться в нескольких наборах сущностей.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-111">Because different entity sets can be based on the same entity type, a particular entity key can appear in multiple entity sets.</span></span> <span data-ttu-id="2f9a7-112">Но ссылка на сущность всегда является уникальной.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-112">However, an entity reference is always unique.</span></span> <span data-ttu-id="2f9a7-113">Если входное выражение представляет сохраняемую сущность, то будет возвращена ссылка на эту сущность.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-113">If the input expression represents a persisted entity, a reference to this entity will be returned.</span></span> <span data-ttu-id="2f9a7-114">Если входное выражение не является сохраняемой сущностью, то возвращается ссылка null.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-114">If the input expression is not a persisted entity, a null reference will be returned.</span></span>  
  
 <span data-ttu-id="2f9a7-115">Если доступ к свойству сущности производится через оператор получения свойства (.), то ссылка автоматически разыменовывается.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-115">If the property extraction operator (.) is used to access a property of an entity, the reference is automatically dereferenced.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f9a7-116">Пример</span><span class="sxs-lookup"><span data-stu-id="2f9a7-116">Example</span></span>  
 <span data-ttu-id="2f9a7-117">В следующем запросе Entity SQL используется оператор REF в целях получения ссылки для входного аргумента сущности.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-117">The following Entity SQL query uses the REF operator to return the reference for an input entity argument.</span></span> <span data-ttu-id="2f9a7-118">Тот же запрос разыменовывает ссылку, поскольку для доступа к свойству сущности Product используется оператор получения свойства (.).</span><span class="sxs-lookup"><span data-stu-id="2f9a7-118">The same query dereferences the reference because we are using a property extraction operation (.) to access a property of the Product entity.</span></span> <span data-ttu-id="2f9a7-119">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-119">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2f9a7-120">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="2f9a7-120">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2f9a7-121">Следуйте процедуре в [Как: Выполнить запрос, который возвращает результаты PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2f9a7-121">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="2f9a7-122">Передайте следующий запрос в качестве аргумента методу `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2f9a7-122">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a><span data-ttu-id="2f9a7-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2f9a7-123">See also</span></span>

- [<span data-ttu-id="2f9a7-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="2f9a7-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="2f9a7-125">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="2f9a7-125">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="2f9a7-126">Ключ</span><span class="sxs-lookup"><span data-stu-id="2f9a7-126">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="2f9a7-127">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2f9a7-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="2f9a7-128">Определения типов</span><span class="sxs-lookup"><span data-stu-id="2f9a7-128">Type Definitions</span></span>](type-definitions-entity-sql.md)
