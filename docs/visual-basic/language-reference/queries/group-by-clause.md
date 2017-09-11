---
title: "Предложение Group By (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement
- Group By clause
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a27e2f15e61456b2e7ac0ede81c66cdb4e8fd612
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="fed35-102">Предложение Group By (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fed35-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="fed35-103">Группирует элементы результата запроса.</span><span class="sxs-lookup"><span data-stu-id="fed35-103">Groups the elements of a query result.</span></span> <span data-ttu-id="fed35-104">Может также использоваться для применения агрегатных функций к каждой группе.</span><span class="sxs-lookup"><span data-stu-id="fed35-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="fed35-105">Операция группирования основана на одном или нескольких ключах.</span><span class="sxs-lookup"><span data-stu-id="fed35-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed35-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fed35-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="fed35-107">Части</span><span class="sxs-lookup"><span data-stu-id="fed35-107">Parts</span></span>  
  
-   <span data-ttu-id="fed35-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="fed35-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="fed35-109">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="fed35-109">Optional.</span></span> <span data-ttu-id="fed35-110">Одно или несколько полей переменной или переменных запроса, которые явно определяют поля для включения в сгруппированный результат.</span><span class="sxs-lookup"><span data-stu-id="fed35-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="fed35-111">Если поля не указаны, в сгруппированный результат включаются все поля из переменной или переменных запроса.</span><span class="sxs-lookup"><span data-stu-id="fed35-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="fed35-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fed35-112">Required.</span></span> <span data-ttu-id="fed35-113">Выражение, которое определяет ключ, используемый для определения групп элементов.</span><span class="sxs-lookup"><span data-stu-id="fed35-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="fed35-114">Вы можете указать несколько ключей, чтобы задать составной ключ.</span><span class="sxs-lookup"><span data-stu-id="fed35-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="fed35-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="fed35-115">Optional.</span></span> <span data-ttu-id="fed35-116">Один или несколько дополнительных ключей, которые объединяются с `keyExp1` для создания составного ключа.</span><span class="sxs-lookup"><span data-stu-id="fed35-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="fed35-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fed35-117">Required.</span></span> <span data-ttu-id="fed35-118">Одно или несколько выражений, определяющих способ агрегирования групп.</span><span class="sxs-lookup"><span data-stu-id="fed35-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="fed35-119">Чтобы определить имя элемента для результатов группирования, используйте ключевое слово `Group` , которое может быть в одной из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="fed35-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="fed35-120">-или-</span><span class="sxs-lookup"><span data-stu-id="fed35-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="fed35-121">Вы также можете включать агрегатные функции для применения к группе.</span><span class="sxs-lookup"><span data-stu-id="fed35-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fed35-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="fed35-122">Remarks</span></span>  
 <span data-ttu-id="fed35-123">Чтобы разбить результат ы запроса на группы, можно использовать предложение `Group By` .</span><span class="sxs-lookup"><span data-stu-id="fed35-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="fed35-124">Группирование основывается на ключе или составном ключе, состоящем из нескольких ключей.</span><span class="sxs-lookup"><span data-stu-id="fed35-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="fed35-125">Элементы, связанные с соответствующими значениями ключа, включаются в одну и ту же группу.</span><span class="sxs-lookup"><span data-stu-id="fed35-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="fed35-126">Чтобы определить имя элемента, используемое для ссылки на группу, применяется параметр `aggregateList` предложения `Into` и ключевое слово `Group` .</span><span class="sxs-lookup"><span data-stu-id="fed35-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="fed35-127">Вы также можете включать в предложение `Into` агрегатные функции, чтобы вычислять значения для сгруппированных элементов.</span><span class="sxs-lookup"><span data-stu-id="fed35-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="fed35-128">Список стандартных статистических функций, в разделе [предложения Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fed35-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fed35-129">Пример</span><span class="sxs-lookup"><span data-stu-id="fed35-129">Example</span></span>  
 <span data-ttu-id="fed35-130">В следующем примере выполняется группирование списка клиентов на основе их расположения (страна) и вычисляется число клиентов в каждой группе.</span><span class="sxs-lookup"><span data-stu-id="fed35-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="fed35-131">Результаты упорядочиваются по названию страны.</span><span class="sxs-lookup"><span data-stu-id="fed35-131">The results are ordered by country name.</span></span> <span data-ttu-id="fed35-132">Результаты группирования упорядочиваются по названию города.</span><span class="sxs-lookup"><span data-stu-id="fed35-132">The grouped results are ordered by city name.</span></span>  
  
 <span data-ttu-id="fed35-133">[!code-vb[VbSimpleQuerySamples&11;](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fed35-133">[!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed35-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fed35-134">See Also</span></span>  
 <span data-ttu-id="fed35-135">[Введение в LINQ в Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="fed35-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="fed35-136"> [Запросы](../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="fed35-136"> [Queries](../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="fed35-137"> [Предложение SELECT](../../../visual-basic/language-reference/queries/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="fed35-137"> [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md) </span></span>  
<span data-ttu-id="fed35-138"> [Предложение FROM](../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="fed35-138"> [From Clause](../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="fed35-139"> [Предложение Order By](../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="fed35-139"> [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="fed35-140"> [Aggregate-предложение](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="fed35-140"> [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="fed35-141"> [Предложение Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)</span><span class="sxs-lookup"><span data-stu-id="fed35-141"> [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)</span></span>
