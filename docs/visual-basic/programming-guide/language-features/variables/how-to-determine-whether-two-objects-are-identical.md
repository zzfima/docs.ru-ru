---
title: Как выполнить Определить, являются ли два объекта идентичны (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 62d73b6c3d706d9990be7783f0f3461fc0783d9f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512974"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="62b04-102">Как выполнить Определить, являются ли два объекта идентичны (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62b04-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="62b04-103">В Visual Basic две ссылки на переменные, считаются идентичными, если их указатели совпадают, то есть, если обе переменные указывают на один и тот же экземпляр класса в памяти.</span><span class="sxs-lookup"><span data-stu-id="62b04-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="62b04-104">Например, в приложении Windows Forms, может потребоваться сделать сравнение с целью определения ли текущий экземпляр (`Me`) совпадает со значением конкретного экземпляра, такие как `Form2`.</span><span class="sxs-lookup"><span data-stu-id="62b04-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="62b04-105">Visual Basic предоставляет два оператора для сравнения указателей.</span><span class="sxs-lookup"><span data-stu-id="62b04-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="62b04-106">[Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) возвращает `True` Если объекты совпадают и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) возвращает `True` если они отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="62b04-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="62b04-107">Определение, если два объекта идентичны</span><span class="sxs-lookup"><span data-stu-id="62b04-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="62b04-108">Для определения идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="62b04-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="62b04-109">Настройка `Boolean` выражение для проверки двух объектов.</span><span class="sxs-lookup"><span data-stu-id="62b04-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="62b04-110">В проверяемом выражении используется `Is` оператора с двумя объектами в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="62b04-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="62b04-111">`Is` Возвращает `True` Если объекты указывают на один и тот же экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="62b04-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="62b04-112">Определение, если два объекта не совпадают</span><span class="sxs-lookup"><span data-stu-id="62b04-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="62b04-113">Иногда требуется выполнить действие, если два объекта не идентичны, и может быть неудобно для объединения `Not` и `Is`, например `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="62b04-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="62b04-114">В этом случае можно использовать `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="62b04-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="62b04-115">Чтобы определить, если два объекта не совпадают</span><span class="sxs-lookup"><span data-stu-id="62b04-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="62b04-116">Настройка `Boolean` выражение для проверки двух объектов.</span><span class="sxs-lookup"><span data-stu-id="62b04-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="62b04-117">В проверяемом выражении используется `IsNot` оператора с двумя объектами в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="62b04-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="62b04-118">`IsNot` Возвращает `True` Если объекты не указывают на один и тот же экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="62b04-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62b04-119">Пример</span><span class="sxs-lookup"><span data-stu-id="62b04-119">Example</span></span>  
 <span data-ttu-id="62b04-120">В следующем примере проверяется пары `Object` переменные, чтобы увидеть, если они указывают на один экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="62b04-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 <span data-ttu-id="62b04-121">В предыдущем примере отображаются следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="62b04-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="62b04-122">См. также</span><span class="sxs-lookup"><span data-stu-id="62b04-122">See also</span></span>
- [<span data-ttu-id="62b04-123">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="62b04-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="62b04-124">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="62b04-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="62b04-125">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="62b04-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="62b04-126">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="62b04-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="62b04-127">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="62b04-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="62b04-128">Практическое руководство. Определение связи между двумя объектами</span><span class="sxs-lookup"><span data-stu-id="62b04-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="62b04-129">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="62b04-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
