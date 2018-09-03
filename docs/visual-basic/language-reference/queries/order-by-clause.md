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
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482601"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="1fcc5-102">Предложение Order By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fcc5-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="1fcc5-103">Указывает порядок сортировки для результата запроса.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fcc5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fcc5-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="1fcc5-105">Части</span><span class="sxs-lookup"><span data-stu-id="1fcc5-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="1fcc5-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-106">Required.</span></span> <span data-ttu-id="1fcc5-107">Одно или несколько полей из текущего результата запроса, определяющие порядок возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="1fcc5-108">Имена полей должны быть разделены запятыми (,).</span><span class="sxs-lookup"><span data-stu-id="1fcc5-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="1fcc5-109">Можно определить каждое поле как отсортированный в порядке возрастания или убывания, используя `Ascending` или `Descending` ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="1fcc5-110">Если не `Ascending` или `Descending` указывается ключевое слово, порядок сортировки по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="1fcc5-111">Поля порядка сортировки получают приоритет слева направо.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fcc5-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="1fcc5-112">Remarks</span></span>  
 <span data-ttu-id="1fcc5-113">Можно использовать `Order By` предложение для сортировки результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="1fcc5-114">`Order By` Предложение можно сортировать только результат на основании переменная диапазона для текущей области.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="1fcc5-115">Например `Select` предложение вводит новую область в выражении запроса с помощью новых переменных итераций для данной области.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="1fcc5-116">Переменные, определенные до диапазона `Select` предложение в запросе не доступны после `Select` предложение.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="1fcc5-117">Таким образом Если есть необходимость упорядочить результаты по полю, которое недоступно в `Select` предложение, необходимо поместить `Order By` предложение перед `Select` предложение.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="1fcc5-118">Один пример при пришлось бы сделать это — необходимо выполнить сортировку по полям, которые не будут возвращены как часть результата запроса.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="1fcc5-119">По возрастанию и убыванию для поля определяется с использованием реализации <xref:System.IComparable> интерфейса для типа данных поля.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="1fcc5-120">Если тип данных не реализует <xref:System.IComparable> интерфейс, порядок сортировки учитывается.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fcc5-121">Пример</span><span class="sxs-lookup"><span data-stu-id="1fcc5-121">Example</span></span>  
 <span data-ttu-id="1fcc5-122">В следующем запросе используется выражение `From` предложение для объявления переменной диапазона `book` для `books` коллекции.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="1fcc5-123">`Order By` Предложение сортирует результаты запроса по цене по возрастанию (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1fcc5-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="1fcc5-124">Книги с такой же цене сортируются по названию в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="1fcc5-125">`Select` Предложение выбирает `Title` и `Price` свойствами, что значения, возвращаемые запросом.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="1fcc5-126">Пример</span><span class="sxs-lookup"><span data-stu-id="1fcc5-126">Example</span></span>  
 <span data-ttu-id="1fcc5-127">В следующем запросе используется выражение `Order By` предложение для сортировки результатов запроса по цене в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="1fcc5-128">Книги с такой же цене сортируются по названию в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="1fcc5-129">Пример</span><span class="sxs-lookup"><span data-stu-id="1fcc5-129">Example</span></span>  
 <span data-ttu-id="1fcc5-130">В следующем запросе используется выражение `Select` предложение, чтобы выбрать название книги, цена, дата публикации и создавать.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="1fcc5-131">Затем заполняет `Title`, `Price`, `PublishDate`, и `Author` поля переменной диапазона для новой области.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="1fcc5-132">`Order By` Предложение упорядочивает новую переменную диапазона, имя автора, название и цена.</span><span class="sxs-lookup"><span data-stu-id="1fcc5-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="1fcc5-133">Каждый столбец сортируется в порядке по умолчанию (по возрастанию).</span><span class="sxs-lookup"><span data-stu-id="1fcc5-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1fcc5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1fcc5-134">See Also</span></span>  
 <span data-ttu-id="1fcc5-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fcc5-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="1fcc5-136">Запросы</span><span class="sxs-lookup"><span data-stu-id="1fcc5-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="1fcc5-137">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="1fcc5-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="1fcc5-138">Предложение From</span><span class="sxs-lookup"><span data-stu-id="1fcc5-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
