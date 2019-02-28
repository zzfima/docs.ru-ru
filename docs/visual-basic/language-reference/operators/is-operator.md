---
title: Оператор Is (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: c4b23bb2d81d1f5272a5813123681da7406c3368
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980346"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="cc9d5-102">Оператор Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc9d5-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="cc9d5-103">Сравнивает две переменные объектной ссылки.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc9d5-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="cc9d5-105">Части</span><span class="sxs-lookup"><span data-stu-id="cc9d5-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="cc9d5-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-106">Required.</span></span> <span data-ttu-id="cc9d5-107">Любой `Boolean` значение.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="cc9d5-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-108">Required.</span></span> <span data-ttu-id="cc9d5-109">Любой `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="cc9d5-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-110">Required.</span></span> <span data-ttu-id="cc9d5-111">Любой `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc9d5-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc9d5-112">Remarks</span></span>  
 <span data-ttu-id="cc9d5-113">`Is` Оператор определяет, если два объекта ссылаются на тот же объект.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="cc9d5-114">Тем не менее он не выполняет сравнение значений.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="cc9d5-115">Если `object1` и `object2` указывают на точное же экземпляр объекта, `result` — `True`; Если нет, `result` является `False`.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="cc9d5-116">`Is` Можно также использовать с `TypeOf` ключевое слово, чтобы сделать `TypeOf`... `Is` выражение, которое проверяет, является ли совместим с типом данных переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc9d5-117">`Is` Ключевое слово также используется в [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cc9d5-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc9d5-118">Пример</span><span class="sxs-lookup"><span data-stu-id="cc9d5-118">Example</span></span>  
 <span data-ttu-id="cc9d5-119">В следующем примере используется `Is` оператор для сравнения пар ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="cc9d5-120">Результаты назначаются `Boolean` значение, представляющее ли два объекта идентичны.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="cc9d5-121">Как показано в предыдущем примере, можно использовать `Is` оба оператора с ранней привязкой и позднее связывание объектов.</span><span class="sxs-lookup"><span data-stu-id="cc9d5-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9d5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cc9d5-122">See also</span></span>
- [<span data-ttu-id="cc9d5-123">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="cc9d5-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="cc9d5-124">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="cc9d5-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="cc9d5-125">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc9d5-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="cc9d5-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc9d5-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="cc9d5-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="cc9d5-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="cc9d5-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="cc9d5-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
