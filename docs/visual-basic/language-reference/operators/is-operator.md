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
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601954"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="0569c-102">Оператор Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0569c-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="0569c-103">Сравнивает две переменные объектной ссылки.</span><span class="sxs-lookup"><span data-stu-id="0569c-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0569c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0569c-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="0569c-105">Части</span><span class="sxs-lookup"><span data-stu-id="0569c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="0569c-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0569c-106">Required.</span></span> <span data-ttu-id="0569c-107">Любой `Boolean` значение.</span><span class="sxs-lookup"><span data-stu-id="0569c-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="0569c-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0569c-108">Required.</span></span> <span data-ttu-id="0569c-109">Любой `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="0569c-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="0569c-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0569c-110">Required.</span></span> <span data-ttu-id="0569c-111">Любой `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="0569c-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0569c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="0569c-112">Remarks</span></span>  
 <span data-ttu-id="0569c-113">`Is` Оператор определяет, если два объекта ссылаются на тот же объект.</span><span class="sxs-lookup"><span data-stu-id="0569c-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="0569c-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0569c-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="0569c-115">Если `object1` и `object2` ссылаются на точное же экземпляр объекта, `result` — `True`; в противном случае, `result` — `False`.</span><span class="sxs-lookup"><span data-stu-id="0569c-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="0569c-116">`Is` Можно также использовать с `TypeOf` ключевое слово, чтобы сделать `TypeOf`... `Is` выражения, которое проверяет, является ли переменная объекта совместим с типом данных.</span><span class="sxs-lookup"><span data-stu-id="0569c-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0569c-117">`Is` Также используется ключевое слово в [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0569c-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0569c-118">Пример</span><span class="sxs-lookup"><span data-stu-id="0569c-118">Example</span></span>  
 <span data-ttu-id="0569c-119">В следующем примере используется `Is` оператор для сравнения пар ссылок на объекты.</span><span class="sxs-lookup"><span data-stu-id="0569c-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="0569c-120">Результаты назначаются `Boolean` значение, представляющее ли два объекта совпадают.</span><span class="sxs-lookup"><span data-stu-id="0569c-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="0569c-121">Как показано в предыдущем примере, вы можете использовать `Is` оба оператора с ранней привязкой и позднее привязывание объектов.</span><span class="sxs-lookup"><span data-stu-id="0569c-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0569c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0569c-122">See Also</span></span>  
 [<span data-ttu-id="0569c-123">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="0569c-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="0569c-124">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="0569c-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="0569c-125">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0569c-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="0569c-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0569c-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="0569c-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="0569c-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="0569c-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="0569c-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
