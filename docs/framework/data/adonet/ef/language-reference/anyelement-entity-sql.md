---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 11d1dd4b09ff07519f3435d313de72c5b9a3edf4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761848"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="89307-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="89307-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="89307-103">Извлекает элемент из многозначной коллекции.</span><span class="sxs-lookup"><span data-stu-id="89307-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89307-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89307-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="89307-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="89307-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="89307-106">Любое допустимое выражение запроса, возвращающее коллекцию, из которой извлекается элемент.</span><span class="sxs-lookup"><span data-stu-id="89307-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89307-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="89307-107">Return Value</span></span>  
 <span data-ttu-id="89307-108">Единственный элемент коллекции или произвольный элемент, если в коллекции их несколько. Если коллекция пустая, возвращается значение `null`.</span><span class="sxs-lookup"><span data-stu-id="89307-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="89307-109">Если `collection` — это коллекция типа `Collection<T>`, затем `ANYELEMENT(collection)` допустимое выражение, возвращающее экземпляр типа `T`.</span><span class="sxs-lookup"><span data-stu-id="89307-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89307-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="89307-110">Remarks</span></span>  
 <span data-ttu-id="89307-111">Оператор ANYELEMENT извлекает произвольный элемент из многозначной коллекции.</span><span class="sxs-lookup"><span data-stu-id="89307-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="89307-112">Например, в следующем примере извлекается один элемент из набора `Customers`.</span><span class="sxs-lookup"><span data-stu-id="89307-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="89307-113">Пример</span><span class="sxs-lookup"><span data-stu-id="89307-113">Example</span></span>  
 <span data-ttu-id="89307-114">В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор ANYELEMENT используется для извлечения элемента из многозначной коллекции.</span><span class="sxs-lookup"><span data-stu-id="89307-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="89307-115">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="89307-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="89307-116">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="89307-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="89307-117">Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="89307-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="89307-118">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="89307-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="89307-119">См. также</span><span class="sxs-lookup"><span data-stu-id="89307-119">See Also</span></span>  
 [<span data-ttu-id="89307-120">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="89307-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="89307-121">Допускающие значения NULL структурированные типы</span><span class="sxs-lookup"><span data-stu-id="89307-121">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
