---
title: Практическое руководство. Определение идентичности двух объектов
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348601"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="51026-102">Практическое руководство. Определение идентичности двух объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51026-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="51026-103">В Visual Basic две ссылки на переменные считаются идентичными, если их указатели одинаковы, то есть если обе переменные указывают на один и тот же экземпляр класса в памяти.</span><span class="sxs-lookup"><span data-stu-id="51026-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="51026-104">Например, в Windows Forms приложении может потребоваться выполнить сравнение, чтобы определить, совпадает ли текущий экземпляр (`Me`) с определенным экземпляром, например `Form2`.</span><span class="sxs-lookup"><span data-stu-id="51026-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="51026-105">Visual Basic предоставляет два оператора для сравнения указателей.</span><span class="sxs-lookup"><span data-stu-id="51026-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="51026-106">[Оператор is](../../../../visual-basic/language-reference/operators/is-operator.md) возвращает `True`, если объекты идентичны, а [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) возвращает `True`, если это не так.</span><span class="sxs-lookup"><span data-stu-id="51026-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="51026-107">Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="51026-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="51026-108">Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="51026-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="51026-109">Настройте `Boolean` выражение для проверки двух объектов.</span><span class="sxs-lookup"><span data-stu-id="51026-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="51026-110">В тестовом выражении используйте оператор `Is` с двумя объектами в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="51026-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="51026-111">`Is` возвращает `True`, если объекты указывают на один и тот же экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="51026-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="51026-112">Определение того, что два объекта не идентичны</span><span class="sxs-lookup"><span data-stu-id="51026-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="51026-113">Иногда требуется выполнить действие, если два объекта не идентичны, и может быть неудобно объединять `Not` и `Is`, например `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="51026-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="51026-114">В этом случае можно использовать оператор `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="51026-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="51026-115">Определение того, что два объекта не идентичны</span><span class="sxs-lookup"><span data-stu-id="51026-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="51026-116">Настройте `Boolean` выражение для проверки двух объектов.</span><span class="sxs-lookup"><span data-stu-id="51026-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="51026-117">В тестовом выражении используйте оператор `IsNot` с двумя объектами в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="51026-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="51026-118">`IsNot` возвращает `True`, если объекты не указывают на один и тот же экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="51026-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51026-119">Пример</span><span class="sxs-lookup"><span data-stu-id="51026-119">Example</span></span>  
 <span data-ttu-id="51026-120">В следующем примере проверяются пары `Object` переменных, чтобы определить, указывают ли они на один и тот же экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="51026-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="51026-121">В предыдущем примере отображаются следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="51026-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="51026-122">См. также</span><span class="sxs-lookup"><span data-stu-id="51026-122">See also</span></span>

- [<span data-ttu-id="51026-123">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="51026-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="51026-124">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="51026-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="51026-125">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="51026-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="51026-126">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="51026-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="51026-127">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="51026-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="51026-128">Практическое руководство. Определение наличия связи между двумя объектами</span><span class="sxs-lookup"><span data-stu-id="51026-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="51026-129">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="51026-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
