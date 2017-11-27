---
title: "Оператор Is (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b1f3f0fa1fd782550c08c816f47b7541399198e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="b2f82-102">Оператор Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2f82-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="b2f82-103">Сравнивает две переменные объектной ссылки.</span><span class="sxs-lookup"><span data-stu-id="b2f82-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2f82-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="b2f82-105">Части</span><span class="sxs-lookup"><span data-stu-id="b2f82-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b2f82-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2f82-106">Required.</span></span> <span data-ttu-id="b2f82-107">Любой `Boolean` значение.</span><span class="sxs-lookup"><span data-stu-id="b2f82-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="b2f82-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2f82-108">Required.</span></span> <span data-ttu-id="b2f82-109">Любой `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="b2f82-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="b2f82-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b2f82-110">Required.</span></span> <span data-ttu-id="b2f82-111">Любой `Object` имя.</span><span class="sxs-lookup"><span data-stu-id="b2f82-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2f82-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2f82-112">Remarks</span></span>  
 <span data-ttu-id="b2f82-113">`Is` Оператор определяет, если два объекта ссылаются на тот же объект.</span><span class="sxs-lookup"><span data-stu-id="b2f82-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="b2f82-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b2f82-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="b2f82-115">Если `object1` и `object2` ссылаются на точное же экземпляр объекта, `result` — `True`; в противном случае, `result` — `False`.</span><span class="sxs-lookup"><span data-stu-id="b2f82-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="b2f82-116">`Is`Можно также использовать с `TypeOf` ключевое слово, чтобы сделать `TypeOf`... `Is` выражения, которое проверяет, является ли переменная объекта совместим с типом данных.</span><span class="sxs-lookup"><span data-stu-id="b2f82-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2f82-117">`Is` Также используется ключевое слово в [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b2f82-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2f82-118">Пример</span><span class="sxs-lookup"><span data-stu-id="b2f82-118">Example</span></span>  
 <span data-ttu-id="b2f82-119">В следующем примере используется `Is` оператор для сравнения пар ссылок на объекты.</span><span class="sxs-lookup"><span data-stu-id="b2f82-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="b2f82-120">Результаты назначаются `Boolean` значение, представляющее ли два объекта совпадают.</span><span class="sxs-lookup"><span data-stu-id="b2f82-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="b2f82-121">Как показано в предыдущем примере, вы можете использовать `Is` оба оператора с ранней привязкой и позднее привязывание объектов.</span><span class="sxs-lookup"><span data-stu-id="b2f82-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f82-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b2f82-122">See Also</span></span>  
 [<span data-ttu-id="b2f82-123">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="b2f82-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="b2f82-124">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="b2f82-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="b2f82-125">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2f82-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="b2f82-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2f82-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b2f82-127">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="b2f82-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b2f82-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="b2f82-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
