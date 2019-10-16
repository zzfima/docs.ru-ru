---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 75140384823588b8f6785de00b0ab3cd17314a3f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319339"
---
# <a name="skip-entity-sql"></a><span data-ttu-id="0f68f-102">SKIP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0f68f-102">SKIP (Entity SQL)</span></span>

<span data-ttu-id="0f68f-103">Вложенное предложение SKIP в предложении ORDER BY позволяет проводить физическое разбиение на страницы.</span><span class="sxs-lookup"><span data-stu-id="0f68f-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="0f68f-104">Ключевое слово SKIP не может использоваться отдельно от предложения ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="0f68f-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f68f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f68f-105">Syntax</span></span>

```sql
[ SKIP n ]
```

## <a name="arguments"></a><span data-ttu-id="0f68f-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0f68f-106">Arguments</span></span>

`n` \
<span data-ttu-id="0f68f-107">Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="0f68f-107">The number of items to skip.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f68f-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="0f68f-108">Remarks</span></span>

<span data-ttu-id="0f68f-109">Если в предложении ORDER BY есть вложенное предложение SKIP, то результаты будут отсортированы в соответствии со спецификацией сортировки, а результирующий набор будет включать строку или строки, начиная со строки, следующей непосредственно за значением выражения SKIP.</span><span class="sxs-lookup"><span data-stu-id="0f68f-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="0f68f-110">Например, SKIP 5 пропустит первые пять строк и возвратит все, начиная с шестой.</span><span class="sxs-lookup"><span data-stu-id="0f68f-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>

> [!NOTE]
> <span data-ttu-id="0f68f-111">Если в одном предложении запроса присутствуют модификатор TOP и вложенное предложение SKIP, то запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="0f68f-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="0f68f-112">Его следует переписать, заменив выражение TOP выражением LIMIT.</span><span class="sxs-lookup"><span data-stu-id="0f68f-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>

> [!NOTE]
> <span data-ttu-id="0f68f-113">В SQL Server 2000 использование инструкции SKIP с предложением ORDER BY в неключевых столбцах может привести к возврату неверных результатов.</span><span class="sxs-lookup"><span data-stu-id="0f68f-113">In SQL Server 2000, using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="0f68f-114">Если неключевой столбец содержит повторяющиеся данные, то может быть пропущено больше указанного числа строк.</span><span class="sxs-lookup"><span data-stu-id="0f68f-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="0f68f-115">Это происходит из-за преобразования SKIP для SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="0f68f-115">This is due to how SKIP is translated for SQL Server 2000.</span></span> <span data-ttu-id="0f68f-116">Например, в следующем коде может быть пропущено более пяти строк, если столбец `E.NonKeyColumn` содержит повторяющиеся значения:</span><span class="sxs-lookup"><span data-stu-id="0f68f-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>
>
> ```sql
> SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L
> ```

<span data-ttu-id="0f68f-117">Запрос [!INCLUDE[esql](../../../../../../includes/esql-md.md)] в статье « [инструкции. Просмотр результатов запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) » использует оператор ORDER BY с ПАРАМЕТРом Skip, чтобы указать порядок сортировки, используемый для объектов, возвращаемых инструкцией SELECT.</span><span class="sxs-lookup"><span data-stu-id="0f68f-117">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f68f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0f68f-118">See also</span></span>

- [<span data-ttu-id="0f68f-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="0f68f-119">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="0f68f-120">[Пошаговое руководство. Просмотр результатов запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0f68f-120">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="0f68f-121">Разбивка на страницы</span><span class="sxs-lookup"><span data-stu-id="0f68f-121">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="0f68f-122">TOP</span><span class="sxs-lookup"><span data-stu-id="0f68f-122">TOP</span></span>](top-entity-sql.md)
