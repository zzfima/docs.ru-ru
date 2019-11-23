---
title: Предложение Let
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 63eaf97016db259870eb77199651ecbdc5f809c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350437"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="3ed61-102">Предложение Let (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ed61-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="3ed61-103">Computes a value and assigns it to a new variable within the query.</span><span class="sxs-lookup"><span data-stu-id="3ed61-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ed61-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ed61-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="3ed61-105">Части</span><span class="sxs-lookup"><span data-stu-id="3ed61-105">Parts</span></span>  
  
|<span data-ttu-id="3ed61-106">Термин</span><span class="sxs-lookup"><span data-stu-id="3ed61-106">Term</span></span>|<span data-ttu-id="3ed61-107">Определение</span><span class="sxs-lookup"><span data-stu-id="3ed61-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="3ed61-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3ed61-108">Required.</span></span> <span data-ttu-id="3ed61-109">An alias that can be used to reference the results of the supplied expression.</span><span class="sxs-lookup"><span data-stu-id="3ed61-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="3ed61-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="3ed61-110">Required.</span></span> <span data-ttu-id="3ed61-111">An expression that will be evaluated and assigned to the specified variable.</span><span class="sxs-lookup"><span data-stu-id="3ed61-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ed61-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="3ed61-112">Remarks</span></span>  
 <span data-ttu-id="3ed61-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span><span class="sxs-lookup"><span data-stu-id="3ed61-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="3ed61-114">The alias can be used in other clauses, such as the `Where` clause.</span><span class="sxs-lookup"><span data-stu-id="3ed61-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="3ed61-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span><span class="sxs-lookup"><span data-stu-id="3ed61-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="3ed61-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span><span class="sxs-lookup"><span data-stu-id="3ed61-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="3ed61-117">Separate each assignment with a comma (,).</span><span class="sxs-lookup"><span data-stu-id="3ed61-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ed61-118">Пример</span><span class="sxs-lookup"><span data-stu-id="3ed61-118">Example</span></span>  
 <span data-ttu-id="3ed61-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span><span class="sxs-lookup"><span data-stu-id="3ed61-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="3ed61-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3ed61-120">See also</span></span>

- <span data-ttu-id="3ed61-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ed61-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="3ed61-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="3ed61-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3ed61-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="3ed61-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="3ed61-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="3ed61-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="3ed61-125">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="3ed61-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
