---
title: Предложение Group By
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
ms.openlocfilehash: 87080254ad5d237a593f0c35e7c3fdaef3a8ad59
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350477"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="449fc-102">Предложение Group By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="449fc-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="449fc-103">Группирует элементы результата запроса.</span><span class="sxs-lookup"><span data-stu-id="449fc-103">Groups the elements of a query result.</span></span> <span data-ttu-id="449fc-104">Может также использоваться для применения агрегатных функций к каждой группе.</span><span class="sxs-lookup"><span data-stu-id="449fc-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="449fc-105">Операция группирования основана на одном или нескольких ключах.</span><span class="sxs-lookup"><span data-stu-id="449fc-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="449fc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="449fc-106">Syntax</span></span>  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="449fc-107">Части</span><span class="sxs-lookup"><span data-stu-id="449fc-107">Parts</span></span>  
  
- <span data-ttu-id="449fc-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="449fc-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="449fc-109">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="449fc-109">Optional.</span></span> <span data-ttu-id="449fc-110">Одно или несколько полей переменной или переменных запроса, которые явно определяют поля для включения в сгруппированный результат.</span><span class="sxs-lookup"><span data-stu-id="449fc-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="449fc-111">Если поля не указаны, в сгруппированный результат включаются все поля из переменной или переменных запроса.</span><span class="sxs-lookup"><span data-stu-id="449fc-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
- `keyExp1`  
  
     <span data-ttu-id="449fc-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="449fc-112">Required.</span></span> <span data-ttu-id="449fc-113">Выражение, которое определяет ключ, используемый для определения групп элементов.</span><span class="sxs-lookup"><span data-stu-id="449fc-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="449fc-114">Вы можете указать несколько ключей, чтобы задать составной ключ.</span><span class="sxs-lookup"><span data-stu-id="449fc-114">You can specify more than one key to specify a composite key.</span></span>  
  
- `keyExp2`  
  
     <span data-ttu-id="449fc-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="449fc-115">Optional.</span></span> <span data-ttu-id="449fc-116">Один или несколько дополнительных ключей, которые объединяются с `keyExp1` для создания составного ключа.</span><span class="sxs-lookup"><span data-stu-id="449fc-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
- `aggregateList`  
  
     <span data-ttu-id="449fc-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="449fc-117">Required.</span></span> <span data-ttu-id="449fc-118">Одно или несколько выражений, определяющих способ агрегирования групп.</span><span class="sxs-lookup"><span data-stu-id="449fc-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="449fc-119">Чтобы определить имя элемента для результатов группирования, используйте ключевое слово `Group` , которое может быть в одной из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="449fc-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```vb  
    Into Group  
    ```  
  
     <span data-ttu-id="449fc-120">\- или -</span><span class="sxs-lookup"><span data-stu-id="449fc-120">-or-</span></span>  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="449fc-121">Вы также можете включать агрегатные функции для применения к группе.</span><span class="sxs-lookup"><span data-stu-id="449fc-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="449fc-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="449fc-122">Remarks</span></span>  
 <span data-ttu-id="449fc-123">Чтобы разбить результат ы запроса на группы, можно использовать предложение `Group By` .</span><span class="sxs-lookup"><span data-stu-id="449fc-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="449fc-124">Группирование основывается на ключе или составном ключе, состоящем из нескольких ключей.</span><span class="sxs-lookup"><span data-stu-id="449fc-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="449fc-125">Элементы, связанные с соответствующими значениями ключа, включаются в одну и ту же группу.</span><span class="sxs-lookup"><span data-stu-id="449fc-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="449fc-126">Чтобы определить имя элемента, используемое для ссылки на группу, применяется параметр `aggregateList` предложения `Into` и ключевое слово `Group` .</span><span class="sxs-lookup"><span data-stu-id="449fc-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="449fc-127">Вы также можете включать в предложение `Into` агрегатные функции, чтобы вычислять значения для сгруппированных элементов.</span><span class="sxs-lookup"><span data-stu-id="449fc-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="449fc-128">Список стандартных агрегатных функций см. в разделе [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="449fc-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="449fc-129">Пример</span><span class="sxs-lookup"><span data-stu-id="449fc-129">Example</span></span>  
 <span data-ttu-id="449fc-130">Следующий пример кода группирует список клиентов по их расположению (стране или региону) и предоставляет количество клиентов в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="449fc-130">The following code example groups a list of customers based on their location (country/region) and provides a count of the customers in each group.</span></span> <span data-ttu-id="449fc-131">Результаты упорядочиваются по названию страны или региона.</span><span class="sxs-lookup"><span data-stu-id="449fc-131">The results are ordered by country/region name.</span></span> <span data-ttu-id="449fc-132">Результаты группирования упорядочиваются по названию города.</span><span class="sxs-lookup"><span data-stu-id="449fc-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="449fc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="449fc-133">See also</span></span>

- <span data-ttu-id="449fc-134">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="449fc-134">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="449fc-135">Запросы</span><span class="sxs-lookup"><span data-stu-id="449fc-135">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="449fc-136">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="449fc-136">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="449fc-137">Предложение From</span><span class="sxs-lookup"><span data-stu-id="449fc-137">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="449fc-138">Предложение Order By</span><span class="sxs-lookup"><span data-stu-id="449fc-138">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="449fc-139">Предложение Aggregate</span><span class="sxs-lookup"><span data-stu-id="449fc-139">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="449fc-140">Предложение Group Join</span><span class="sxs-lookup"><span data-stu-id="449fc-140">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
