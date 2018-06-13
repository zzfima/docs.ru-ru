---
title: Предложение Order By (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 7c60156ee81618530b42d5f61dbcac6f59c4f675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604124"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="373c0-102">Предложение Order By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="373c0-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="373c0-103">Указывает порядок сортировки для результата запроса.</span><span class="sxs-lookup"><span data-stu-id="373c0-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="373c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="373c0-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="373c0-105">Части</span><span class="sxs-lookup"><span data-stu-id="373c0-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="373c0-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="373c0-106">Required.</span></span> <span data-ttu-id="373c0-107">Одно или несколько полей из текущего результата запроса, определяющие порядок возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="373c0-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="373c0-108">Имена полей должны быть разделены запятыми (,).</span><span class="sxs-lookup"><span data-stu-id="373c0-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="373c0-109">Можно определить каждое поле в возрастающем или убывающем порядке с помощью `Ascending` или `Descending` ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="373c0-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="373c0-110">Если не `Ascending` или `Descending` указано ключевое слово, порядок сортировки по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="373c0-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="373c0-111">Поля порядка сортировки получают приоритет слева направо.</span><span class="sxs-lookup"><span data-stu-id="373c0-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="373c0-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="373c0-112">Remarks</span></span>  
 <span data-ttu-id="373c0-113">Можно использовать `Order By` предложение для сортировки результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="373c0-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="373c0-114">`Order By` Предложения можно сортировать только результата, основанного на переменную диапазона для текущей области.</span><span class="sxs-lookup"><span data-stu-id="373c0-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="373c0-115">Например `Select` предложение вводит новую область в выражении запроса с новыми переменными итерации для этой области.</span><span class="sxs-lookup"><span data-stu-id="373c0-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="373c0-116">Переменные, определенные до диапазона `Select` предложения в запросе недоступны после `Select` предложения.</span><span class="sxs-lookup"><span data-stu-id="373c0-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="373c0-117">Таким образом Если необходимо выполнить сортировку результатов по полю, которое недоступно в `Select` предложение, необходимо поместить `Order By` предложение перед `Select` предложения.</span><span class="sxs-lookup"><span data-stu-id="373c0-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="373c0-118">Один пример при пришлось бы сделать это: необходимо выполнить сортировку по полям, которые не возвращаются как часть результата запроса.</span><span class="sxs-lookup"><span data-stu-id="373c0-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="373c0-119">По возрастанию и убыванию для поля определяется реализация <xref:System.IComparable> интерфейса для типа данных поля.</span><span class="sxs-lookup"><span data-stu-id="373c0-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="373c0-120">Если тип данных не реализует <xref:System.IComparable> интерфейс, порядок сортировки учитывается.</span><span class="sxs-lookup"><span data-stu-id="373c0-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="373c0-121">Пример</span><span class="sxs-lookup"><span data-stu-id="373c0-121">Example</span></span>  
 <span data-ttu-id="373c0-122">В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `book` для `books` коллекции.</span><span class="sxs-lookup"><span data-stu-id="373c0-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="373c0-123">`Order By` Предложение сортирует результаты запроса по цене в возрастающем порядке (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="373c0-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="373c0-124">Книги с той же ценой сортируются по названию в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="373c0-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="373c0-125">`Select` Предложение выбирает `Title` и `Price` свойств в виде значений, возвращенных запросом.</span><span class="sxs-lookup"><span data-stu-id="373c0-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="373c0-126">Пример</span><span class="sxs-lookup"><span data-stu-id="373c0-126">Example</span></span>  
 <span data-ttu-id="373c0-127">В следующем запросе используется выражение `Order By` предложение для сортировки результатов запроса по цене в убывающем порядке.</span><span class="sxs-lookup"><span data-stu-id="373c0-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="373c0-128">Книги с той же ценой сортируются по названию в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="373c0-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="373c0-129">Пример</span><span class="sxs-lookup"><span data-stu-id="373c0-129">Example</span></span>  
 <span data-ttu-id="373c0-130">В следующем запросе используется выражение `Select` предложение выберите название книги, price, дата публикации и создания.</span><span class="sxs-lookup"><span data-stu-id="373c0-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="373c0-131">Затем заполняет `Title`, `Price`, `PublishDate`, и `Author` поля переменной диапазона для новой области.</span><span class="sxs-lookup"><span data-stu-id="373c0-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="373c0-132">`Order By` Предложение упорядочивает новую переменную диапазона, имя автора, название книги и price.</span><span class="sxs-lookup"><span data-stu-id="373c0-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="373c0-133">Каждый столбец сортируется в порядке по умолчанию (по возрастанию).</span><span class="sxs-lookup"><span data-stu-id="373c0-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="373c0-134">См. также</span><span class="sxs-lookup"><span data-stu-id="373c0-134">See Also</span></span>  
 <span data-ttu-id="373c0-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="373c0-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="373c0-136">Запросы</span><span class="sxs-lookup"><span data-stu-id="373c0-136">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="373c0-137">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="373c0-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="373c0-138">Предложение From</span><span class="sxs-lookup"><span data-stu-id="373c0-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
