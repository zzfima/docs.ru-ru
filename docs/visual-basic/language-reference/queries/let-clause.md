---
title: Предложение Let (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: ff298f001a2d865446436e8099a2fbbef593a00a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828717"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="706d5-102">Предложение Let (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="706d5-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="706d5-103">Вычисляет значение и присваивает его новой переменной в запросе.</span><span class="sxs-lookup"><span data-stu-id="706d5-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="706d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="706d5-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="706d5-105">Части</span><span class="sxs-lookup"><span data-stu-id="706d5-105">Parts</span></span>  
  
|<span data-ttu-id="706d5-106">Термин</span><span class="sxs-lookup"><span data-stu-id="706d5-106">Term</span></span>|<span data-ttu-id="706d5-107">Определение</span><span class="sxs-lookup"><span data-stu-id="706d5-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="706d5-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="706d5-108">Required.</span></span> <span data-ttu-id="706d5-109">Псевдоним, который может использоваться для ссылки на результаты предоставленного выражения.</span><span class="sxs-lookup"><span data-stu-id="706d5-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="706d5-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="706d5-110">Required.</span></span> <span data-ttu-id="706d5-111">Выражение, будут вычисляются и присваиваются переменной.</span><span class="sxs-lookup"><span data-stu-id="706d5-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="706d5-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="706d5-112">Remarks</span></span>  
 <span data-ttu-id="706d5-113">`Let` Предложение позволяет вычислить значения для каждого результат запроса и ссылаться на них с помощью псевдонима.</span><span class="sxs-lookup"><span data-stu-id="706d5-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="706d5-114">Псевдоним может использоваться в других предложениях, таких как `Where` предложение.</span><span class="sxs-lookup"><span data-stu-id="706d5-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="706d5-115">`Let` Предложение позволяет создать оператор запроса, который является более удобным для чтения, поскольку можно указать псевдоним для условия выражения, включенного в запрос и заменять этот псевдоним каждый раз, используется предложение выражения.</span><span class="sxs-lookup"><span data-stu-id="706d5-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="706d5-116">Можно включить любое число `variable` и `expression` назначения в `Let` предложение.</span><span class="sxs-lookup"><span data-stu-id="706d5-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="706d5-117">После каждого назначения следует разделяйте запятыми (,).</span><span class="sxs-lookup"><span data-stu-id="706d5-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="706d5-118">Пример</span><span class="sxs-lookup"><span data-stu-id="706d5-118">Example</span></span>  
 <span data-ttu-id="706d5-119">В следующем примере кода используется `Let` предложение для вычисления скидку 10% на продукты.</span><span class="sxs-lookup"><span data-stu-id="706d5-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="706d5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="706d5-120">See also</span></span>

- <span data-ttu-id="706d5-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="706d5-121">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="706d5-122">Запросы</span><span class="sxs-lookup"><span data-stu-id="706d5-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="706d5-123">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="706d5-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="706d5-124">Предложение From</span><span class="sxs-lookup"><span data-stu-id="706d5-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="706d5-125">Предложения Where</span><span class="sxs-lookup"><span data-stu-id="706d5-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
