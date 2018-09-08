---
title: Предложение Group By (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 88707ed6c0e3e5a0ecf1f0812d31634bbdca3123
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183123"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="46b68-102">Предложение Group By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46b68-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="46b68-103">Группирует элементы результата запроса.</span><span class="sxs-lookup"><span data-stu-id="46b68-103">Groups the elements of a query result.</span></span> <span data-ttu-id="46b68-104">Может также использоваться для применения агрегатных функций к каждой группе.</span><span class="sxs-lookup"><span data-stu-id="46b68-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="46b68-105">Операция группирования основана на одном или нескольких ключах.</span><span class="sxs-lookup"><span data-stu-id="46b68-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b68-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46b68-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="46b68-107">Части</span><span class="sxs-lookup"><span data-stu-id="46b68-107">Parts</span></span>  
  
-   <span data-ttu-id="46b68-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="46b68-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="46b68-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="46b68-109">Optional.</span></span> <span data-ttu-id="46b68-110">Одно или несколько полей переменной или переменных запроса, которые явно определяют поля для включения в сгруппированный результат.</span><span class="sxs-lookup"><span data-stu-id="46b68-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="46b68-111">Если поля не указаны, в сгруппированный результат включаются все поля из переменной или переменных запроса.</span><span class="sxs-lookup"><span data-stu-id="46b68-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="46b68-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="46b68-112">Required.</span></span> <span data-ttu-id="46b68-113">Выражение, которое определяет ключ, используемый для определения групп элементов.</span><span class="sxs-lookup"><span data-stu-id="46b68-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="46b68-114">Вы можете указать несколько ключей, чтобы задать составной ключ.</span><span class="sxs-lookup"><span data-stu-id="46b68-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="46b68-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="46b68-115">Optional.</span></span> <span data-ttu-id="46b68-116">Один или несколько дополнительных ключей, которые объединяются с `keyExp1` для создания составного ключа.</span><span class="sxs-lookup"><span data-stu-id="46b68-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="46b68-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="46b68-117">Required.</span></span> <span data-ttu-id="46b68-118">Одно или несколько выражений, определяющих способ агрегирования групп.</span><span class="sxs-lookup"><span data-stu-id="46b68-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="46b68-119">Чтобы определить имя элемента для результатов группирования, используйте ключевое слово `Group` , которое может быть в одной из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="46b68-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="46b68-120">- или -</span><span class="sxs-lookup"><span data-stu-id="46b68-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="46b68-121">Вы также можете включать агрегатные функции для применения к группе.</span><span class="sxs-lookup"><span data-stu-id="46b68-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46b68-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="46b68-122">Remarks</span></span>  
 <span data-ttu-id="46b68-123">Чтобы разбить результат ы запроса на группы, можно использовать предложение `Group By` .</span><span class="sxs-lookup"><span data-stu-id="46b68-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="46b68-124">Группирование основывается на ключе или составном ключе, состоящем из нескольких ключей.</span><span class="sxs-lookup"><span data-stu-id="46b68-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="46b68-125">Элементы, связанные с соответствующими значениями ключа, включаются в одну и ту же группу.</span><span class="sxs-lookup"><span data-stu-id="46b68-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="46b68-126">Чтобы определить имя элемента, используемое для ссылки на группу, применяется параметр `aggregateList` предложения `Into` и ключевое слово `Group` .</span><span class="sxs-lookup"><span data-stu-id="46b68-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="46b68-127">Вы также можете включать в предложение `Into` агрегатные функции, чтобы вычислять значения для сгруппированных элементов.</span><span class="sxs-lookup"><span data-stu-id="46b68-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="46b68-128">Список стандартных агрегатных функций, см. в разделе [предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="46b68-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46b68-129">Пример</span><span class="sxs-lookup"><span data-stu-id="46b68-129">Example</span></span>  
 <span data-ttu-id="46b68-130">В следующем примере выполняется группирование списка клиентов на основе их расположения (страна) и вычисляется число клиентов в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="46b68-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="46b68-131">Результаты упорядочиваются по названию страны.</span><span class="sxs-lookup"><span data-stu-id="46b68-131">The results are ordered by country name.</span></span> <span data-ttu-id="46b68-132">Результаты группирования упорядочиваются по названию города.</span><span class="sxs-lookup"><span data-stu-id="46b68-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="46b68-133">См. также</span><span class="sxs-lookup"><span data-stu-id="46b68-133">See Also</span></span>  
 <span data-ttu-id="46b68-134">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46b68-134">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="46b68-135">Запросы</span><span class="sxs-lookup"><span data-stu-id="46b68-135">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="46b68-136">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="46b68-136">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="46b68-137">Предложение From</span><span class="sxs-lookup"><span data-stu-id="46b68-137">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="46b68-138">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="46b68-138">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="46b68-139">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="46b68-139">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="46b68-140">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="46b68-140">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
