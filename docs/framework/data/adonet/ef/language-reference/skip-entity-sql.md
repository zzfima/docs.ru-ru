---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 6ddbdd41a00b3934649b24ca96a5a07e5cbf0d34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911137"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="26c72-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="26c72-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="26c72-103">Вложенное предложение SKIP в предложении ORDER BY позволяет проводить физическое разбиение на страницы.</span><span class="sxs-lookup"><span data-stu-id="26c72-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="26c72-104">Ключевое слово SKIP не может использоваться отдельно от предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="26c72-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c72-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26c72-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="26c72-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="26c72-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="26c72-107">Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="26c72-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26c72-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="26c72-108">Remarks</span></span>  
 <span data-ttu-id="26c72-109">Если в предложении ORDER BY есть вложенное предложение SKIP, то результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP.</span><span class="sxs-lookup"><span data-stu-id="26c72-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="26c72-110">Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.</span><span class="sxs-lookup"><span data-stu-id="26c72-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26c72-111">Если в одном предложении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="26c72-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="26c72-112">Его следует переписать, заменив выражение TOP выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="26c72-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26c72-113">В SQL Server 2000 использование инструкции SKIP с предложением ORDER BY в неключевых столбцах может привести к возврату неверных результатов.</span><span class="sxs-lookup"><span data-stu-id="26c72-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="26c72-114">Если неключевой столбец содержит повторяющиеся данные, то может быть пропущено больше указанного числа строк.</span><span class="sxs-lookup"><span data-stu-id="26c72-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="26c72-115">Это происходит из-за преобразования SKIP для SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="26c72-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="26c72-116">Например, в следующем коде может быть пропущено более пяти строк, если столбец `E.NonKeyColumn` содержит повторяющиеся значения:</span><span class="sxs-lookup"><span data-stu-id="26c72-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="26c72-117">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] Запрос в[процедуре: На странице в результатах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) запроса для указания порядка сортировки объектов, возвращаемых инструкцией SELECT, используется оператор ORDER BY с параметром SKIP.</span><span class="sxs-lookup"><span data-stu-id="26c72-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c72-118">См. также</span><span class="sxs-lookup"><span data-stu-id="26c72-118">See also</span></span>

- [<span data-ttu-id="26c72-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="26c72-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- <span data-ttu-id="26c72-120">[Практическое руководство. Страница с результатами запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="26c72-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="26c72-121">Разбивка на страницы</span><span class="sxs-lookup"><span data-stu-id="26c72-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [<span data-ttu-id="26c72-122">TOP</span><span class="sxs-lookup"><span data-stu-id="26c72-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
