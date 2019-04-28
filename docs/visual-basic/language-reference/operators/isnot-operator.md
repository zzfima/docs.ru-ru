---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: e07a775eec003a3e488f6909181aed3f742b4b91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768356"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="d7184-102">Оператор IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7184-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="d7184-103">Сравнивает две переменные объектной ссылки.</span><span class="sxs-lookup"><span data-stu-id="d7184-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7184-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7184-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="d7184-105">Части</span><span class="sxs-lookup"><span data-stu-id="d7184-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d7184-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d7184-106">Required.</span></span> <span data-ttu-id="d7184-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d7184-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="d7184-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d7184-108">Required.</span></span> <span data-ttu-id="d7184-109">Любой `Object` переменной или выражения.</span><span class="sxs-lookup"><span data-stu-id="d7184-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="d7184-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d7184-110">Required.</span></span> <span data-ttu-id="d7184-111">Любой `Object` переменной или выражения.</span><span class="sxs-lookup"><span data-stu-id="d7184-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7184-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7184-112">Remarks</span></span>  
 <span data-ttu-id="d7184-113">`IsNot` Оператор определяет, если два объекта ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="d7184-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="d7184-114">Тем не менее он не выполняет сравнение значений.</span><span class="sxs-lookup"><span data-stu-id="d7184-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="d7184-115">Если `object1` и `object2` указывают на точное же экземпляр объекта, `result` — `False`; Если нет, `result` является `True`.</span><span class="sxs-lookup"><span data-stu-id="d7184-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="d7184-116">`IsNot` является противоположностью `Is` оператор.</span><span class="sxs-lookup"><span data-stu-id="d7184-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="d7184-117">Преимущество `IsNot` — избегать неуклюжим синтаксису `Not` и `Is`, который может быть трудно читать.</span><span class="sxs-lookup"><span data-stu-id="d7184-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="d7184-118">Можно использовать `Is` и `IsNot` операторы для проверки объектов с ранним и поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="d7184-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7184-119">`IsNot` Оператор не может использоваться для сравнения выражений, возвращенных `TypeOf` оператор.</span><span class="sxs-lookup"><span data-stu-id="d7184-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="d7184-120">Вместо этого необходимо использовать `Not` и `Is` операторы.</span><span class="sxs-lookup"><span data-stu-id="d7184-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7184-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d7184-121">Example</span></span>  
 <span data-ttu-id="d7184-122">В следующем примере кода используются как `Is` оператор и `IsNot` оператор для выполнения того же сравнения.</span><span class="sxs-lookup"><span data-stu-id="d7184-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="d7184-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d7184-123">See also</span></span>

- [<span data-ttu-id="d7184-124">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="d7184-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="d7184-125">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="d7184-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="d7184-126">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7184-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d7184-127">Практическое руководство. Проверка совпадения двух объектов</span><span class="sxs-lookup"><span data-stu-id="d7184-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
