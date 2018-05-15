---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: babee364d350ca84a8379f675acc4b5c87f98303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="90a69-102">Оператор IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90a69-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="90a69-103">Сравнивает две переменные объектной ссылки.</span><span class="sxs-lookup"><span data-stu-id="90a69-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90a69-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="90a69-105">Части</span><span class="sxs-lookup"><span data-stu-id="90a69-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="90a69-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="90a69-106">Required.</span></span> <span data-ttu-id="90a69-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="90a69-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="90a69-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="90a69-108">Required.</span></span> <span data-ttu-id="90a69-109">Любой `Object` переменной или выражения.</span><span class="sxs-lookup"><span data-stu-id="90a69-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="90a69-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="90a69-110">Required.</span></span> <span data-ttu-id="90a69-111">Любой `Object` переменной или выражения.</span><span class="sxs-lookup"><span data-stu-id="90a69-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90a69-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="90a69-112">Remarks</span></span>  
 <span data-ttu-id="90a69-113">`IsNot` Оператор определяет, если две объектные ссылки на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="90a69-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="90a69-114">Однако сравнение значений не выполняется.</span><span class="sxs-lookup"><span data-stu-id="90a69-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="90a69-115">Если `object1` и `object2` ссылаются на точное же экземпляр объекта, `result` — `False`; в противном случае, `result` — `True`.</span><span class="sxs-lookup"><span data-stu-id="90a69-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="90a69-116">`IsNot` шаблон противоположен `Is` оператор.</span><span class="sxs-lookup"><span data-stu-id="90a69-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="90a69-117">Преимущество `IsNot` — избегать неуклюжим синтаксису `Not` и `Is`, который может быть трудно читать.</span><span class="sxs-lookup"><span data-stu-id="90a69-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="90a69-118">Можно использовать `Is` и `IsNot` операторы для проверки объектов с ранним связыванием и поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="90a69-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90a69-119">`IsNot` Оператор не может использоваться для сравнения выражений, возвращенных `TypeOf` оператор.</span><span class="sxs-lookup"><span data-stu-id="90a69-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="90a69-120">Вместо этого необходимо использовать `Not` и `Is` операторы.</span><span class="sxs-lookup"><span data-stu-id="90a69-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90a69-121">Пример</span><span class="sxs-lookup"><span data-stu-id="90a69-121">Example</span></span>  
 <span data-ttu-id="90a69-122">В следующем примере кода используются `Is` оператор и `IsNot` оператор для выполнения того же сравнения.</span><span class="sxs-lookup"><span data-stu-id="90a69-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="90a69-123">См. также</span><span class="sxs-lookup"><span data-stu-id="90a69-123">See Also</span></span>  
 [<span data-ttu-id="90a69-124">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="90a69-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="90a69-125">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="90a69-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="90a69-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90a69-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="90a69-127">Практическое руководство. Проверка совпадения двух объектов</span><span class="sxs-lookup"><span data-stu-id="90a69-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
