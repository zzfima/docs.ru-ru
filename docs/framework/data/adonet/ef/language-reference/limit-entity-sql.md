---
title: LIMIT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c890bf6950f94c04350902276193f5a43239f63f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="limit-entity-sql"></a><span data-ttu-id="971c0-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="971c0-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="971c0-103">Вложенное предложение LIMIT в предложении ORDER BY позволяет проводить физическое разбиение на страницы.</span><span class="sxs-lookup"><span data-stu-id="971c0-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="971c0-104">Ключевое слово LIMIT не может использоваться отдельно от предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="971c0-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="971c0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="971c0-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="971c0-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="971c0-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="971c0-107">Число элементов, которые будут выбраны.</span><span class="sxs-lookup"><span data-stu-id="971c0-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="971c0-108">Если в предложении ORDER BY имеется подчиненное выражение LIMIT, результаты запроса будут отсортированы в соответствии со спецификацией сортировки, а количество строк в наборе будет ограничено выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="971c0-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="971c0-109">Например, LIMIT 5 ограничит результирующий набор до пяти экземпляров строк.</span><span class="sxs-lookup"><span data-stu-id="971c0-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="971c0-110">Ключевое слово LIMIT является функциональным эквивалентом оператора TOP, однако для LIMIT необходимо присутствие предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="971c0-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="971c0-111">Предложения SKIP и LIMIT могут использоваться в предложении ORDER BY независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="971c0-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="971c0-112">Если в одном выражении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос Entity SQL является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="971c0-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="971c0-113">Его следует переписать, заменив выражение TOP выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="971c0-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="971c0-114">Пример</span><span class="sxs-lookup"><span data-stu-id="971c0-114">Example</span></span>  
 <span data-ttu-id="971c0-115">В следующем запросе Entity SQL оператор ORDER BY с предложением LIMIT задает порядок сортировки, используемый для объектов, возвращаемых инструкцией SELECT.</span><span class="sxs-lookup"><span data-stu-id="971c0-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="971c0-116">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="971c0-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="971c0-117">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="971c0-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="971c0-118">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="971c0-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="971c0-119">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="971c0-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="971c0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="971c0-120">See Also</span></span>  
 [<span data-ttu-id="971c0-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="971c0-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="971c0-122">Как: постранично просмотреть результаты запроса</span><span class="sxs-lookup"><span data-stu-id="971c0-122">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="971c0-123">Разбивка на страницы</span><span class="sxs-lookup"><span data-stu-id="971c0-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="971c0-124">ВВЕРХ</span><span class="sxs-lookup"><span data-stu-id="971c0-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
