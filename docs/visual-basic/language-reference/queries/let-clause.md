---
title: Предложение Let (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70e47517a62f58dcababd31c26277417b62eab66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="f57bd-102">Предложение Let (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f57bd-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="f57bd-103">Вычисляет значение и присваивает его новой переменной в запросе.</span><span class="sxs-lookup"><span data-stu-id="f57bd-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f57bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f57bd-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="f57bd-105">Части</span><span class="sxs-lookup"><span data-stu-id="f57bd-105">Parts</span></span>  
  
|<span data-ttu-id="f57bd-106">Термин</span><span class="sxs-lookup"><span data-stu-id="f57bd-106">Term</span></span>|<span data-ttu-id="f57bd-107">Определение</span><span class="sxs-lookup"><span data-stu-id="f57bd-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="f57bd-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f57bd-108">Required.</span></span> <span data-ttu-id="f57bd-109">Псевдоним, который может использоваться для ссылки на результаты предоставленного выражения.</span><span class="sxs-lookup"><span data-stu-id="f57bd-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="f57bd-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f57bd-110">Required.</span></span> <span data-ttu-id="f57bd-111">Выражение, оценивается и назначен переменной.</span><span class="sxs-lookup"><span data-stu-id="f57bd-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f57bd-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="f57bd-112">Remarks</span></span>  
 <span data-ttu-id="f57bd-113">`Let` Предложение позволяет вычислить значения для каждого результата запроса и ссылаться на них с помощью псевдонима.</span><span class="sxs-lookup"><span data-stu-id="f57bd-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="f57bd-114">Псевдоним может использоваться в других предложениях, таких как `Where` предложения.</span><span class="sxs-lookup"><span data-stu-id="f57bd-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="f57bd-115">`Let` Предложение позволяет создавать инструкции запроса, который является более удобным для чтения, поскольку можно указать псевдоним для условия выражения, включенного в запрос и заменять этот псевдоним при каждом условия выражения.</span><span class="sxs-lookup"><span data-stu-id="f57bd-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="f57bd-116">Можно включить любое количество `variable` и `expression` назначения в `Let` предложения.</span><span class="sxs-lookup"><span data-stu-id="f57bd-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="f57bd-117">Каждое назначение разделяются точкой с запятой (,).</span><span class="sxs-lookup"><span data-stu-id="f57bd-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f57bd-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f57bd-118">Example</span></span>  
 <span data-ttu-id="f57bd-119">Следующий пример кода использует `Let` предложение для вычисления 10% скидки на продукты.</span><span class="sxs-lookup"><span data-stu-id="f57bd-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f57bd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f57bd-120">See Also</span></span>  
 <span data-ttu-id="f57bd-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f57bd-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="f57bd-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="f57bd-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="f57bd-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="f57bd-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="f57bd-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="f57bd-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="f57bd-125">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="f57bd-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
