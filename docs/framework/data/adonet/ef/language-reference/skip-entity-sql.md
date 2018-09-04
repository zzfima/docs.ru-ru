---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 321f6c5ae62ce21249ae4c1081b8e98427bc3df2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500746"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="4afdd-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4afdd-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="4afdd-103">Вложенное предложение SKIP в предложении ORDER BY позволяет проводить физическое разбиение на страницы.</span><span class="sxs-lookup"><span data-stu-id="4afdd-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="4afdd-104">Ключевое слово SKIP не может использоваться отдельно от предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="4afdd-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4afdd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4afdd-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4afdd-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4afdd-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="4afdd-107">Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="4afdd-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4afdd-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4afdd-108">Remarks</span></span>  
 <span data-ttu-id="4afdd-109">Если в предложении ORDER BY есть вложенное предложение SKIP, то результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP.</span><span class="sxs-lookup"><span data-stu-id="4afdd-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="4afdd-110">Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.</span><span class="sxs-lookup"><span data-stu-id="4afdd-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4afdd-111">Если в одном предложении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="4afdd-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="4afdd-112">Его следует переписать, заменив выражение TOP выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="4afdd-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4afdd-113">В [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]использование предложения SKIP вместе с ORDER BY для неключевых столбцов может привести к возврату неверных результатов.</span><span class="sxs-lookup"><span data-stu-id="4afdd-113">In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="4afdd-114">Если неключевой столбец содержит повторяющиеся данные, то может быть пропущено больше указанного числа строк.</span><span class="sxs-lookup"><span data-stu-id="4afdd-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="4afdd-115">Причина этого заключается в способе преобразования предложения SKIP для выполнения в [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4afdd-115">This is due to how SKIP is translated for [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="4afdd-116">Например, в следующем коде может быть пропущено более пяти строк, если столбец `E.NonKeyColumn` содержит повторяющиеся значения:</span><span class="sxs-lookup"><span data-stu-id="4afdd-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="4afdd-117">Запрос  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в [этом](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) примере использует для задания порядка сортировки объектов, возвращаемых инструкцией SELECT, оператор ORDER BY с предложением SKIP.</span><span class="sxs-lookup"><span data-stu-id="4afdd-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [this](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) example uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afdd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4afdd-118">See Also</span></span>  
 [<span data-ttu-id="4afdd-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="4afdd-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="4afdd-120">Практическое: постранично просмотреть результаты запроса</span><span class="sxs-lookup"><span data-stu-id="4afdd-120">How to: Page Through Query Results</span></span>](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="4afdd-121">Разбивка на страницы</span><span class="sxs-lookup"><span data-stu-id="4afdd-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="4afdd-122">TOP</span><span class="sxs-lookup"><span data-stu-id="4afdd-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
