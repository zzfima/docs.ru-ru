---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: b267e97860a2cb071b857224455f01b73115c72d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760679"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="396bc-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="396bc-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="396bc-103">Вложенное предложение LIMIT в предложении ORDER BY позволяет проводить физическое разбиение на страницы.</span><span class="sxs-lookup"><span data-stu-id="396bc-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="396bc-104">Ключевое слово LIMIT не может использоваться отдельно от предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="396bc-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="396bc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="396bc-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="396bc-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="396bc-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="396bc-107">Число элементов, которые будут выбраны.</span><span class="sxs-lookup"><span data-stu-id="396bc-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="396bc-108">Если в предложении ORDER BY имеется подчиненное выражение LIMIT, результаты запроса будут отсортированы в соответствии со спецификацией сортировки, а количество строк в наборе будет ограничено выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="396bc-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="396bc-109">Например, LIMIT 5 ограничит результирующий набор до пяти экземпляров строк.</span><span class="sxs-lookup"><span data-stu-id="396bc-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="396bc-110">Ключевое слово LIMIT является функциональным эквивалентом оператора TOP, однако для LIMIT необходимо присутствие предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="396bc-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="396bc-111">Предложения SKIP и LIMIT могут использоваться в предложении ORDER BY независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="396bc-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="396bc-112">Если в одном выражении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос Entity SQL является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="396bc-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="396bc-113">Его следует переписать, заменив выражение TOP выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="396bc-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="396bc-114">Пример</span><span class="sxs-lookup"><span data-stu-id="396bc-114">Example</span></span>  
 <span data-ttu-id="396bc-115">В следующем запросе Entity SQL оператор ORDER BY с предложением LIMIT задает порядок сортировки, используемый для объектов, возвращаемых инструкцией SELECT.</span><span class="sxs-lookup"><span data-stu-id="396bc-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="396bc-116">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="396bc-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="396bc-117">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="396bc-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="396bc-118">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="396bc-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="396bc-119">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="396bc-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="396bc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="396bc-120">See also</span></span>

- [<span data-ttu-id="396bc-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="396bc-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="396bc-122">[Практическое руководство. Постранично просмотреть результаты запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="396bc-122">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="396bc-123">Разбивка на страницы</span><span class="sxs-lookup"><span data-stu-id="396bc-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="396bc-124">TOP</span><span class="sxs-lookup"><span data-stu-id="396bc-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
